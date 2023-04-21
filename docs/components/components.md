# Компонентная архитектура
<!-- Состав и взаимосвязи компонентов системы между собой и внешними системами с указанием протоколов, ключевые технологии, используемые для реализации компонентов.
Диаграмма контейнеров C4 и текстовое описание. 
Подробнее: https://confluence.mts.ru/pages/viewpage.action?pageId=375783368
-->
## Контейнерная диаграмма

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

AddElementTag("microService", $shape=EightSidedShape(), $bgColor="CornflowerBlue", $fontColor="white", $legendText="microservice")
AddElementTag("storage", $shape=RoundedBoxShape(), $bgColor="lightSkyBlue", $fontColor="white")

Person(participant, "Участник конференции", "Посетитель конфереции")
Person(speaker, "Докладчик", "Выступающий перед аудиторией")
Person(expert, "Эксперт", "Сотрудник программного комитета")
Person(admin, "Администратор", "Административный персонал")

System_Boundary(hello_conf_system, "HelloConf") {
   Container(frontend, "Клиентское веб-приложение", "html, JavaScript, Angular", "Веб-портал helloconf")

   Container(load_balancer, "API Gateway", "Nginx")

   Container(conference_mngmt_service, "Сервис управления конференцией", "C#, .NET Core, ASP.NET Core", "Сервис управления конференцией", $tags = "microService")
   Container(report_mngmt_service, "Сервис управления докладами", "C#, .NET Core, ASP.NET Core", "Сервис управления докладами", $tags = "microService")
   Container(schedule_mngmt_service, "Сервис управления расписанием", "C#, .NET Core, ASP.NET Core", "Сервис управления расписанием", $tags = "microService")
   Container(schedule_replication_service, "Сервис репликации расписаний", "C#, .NET Core, ASP.NET Core", "Сервис управления расписанием", $tags = "microService")

   Container(feedback_mngmt_service, "Сервис оценки докладов", "C#, .NET Core, ASP.NET Core", "Сервис управления оценками", $tags = "microService")
   Container(feedback_aggregation_service, "Сервис агрегации оценок", "C#, .NET Core, ASP.NET Core", "Сервис агрегации оценок", $tags = "microService")

   Container(online_streaming_service, "Сервис онлайн стриминга", "C#, .NET Core, ASP.NET Core", "Сервис онлайн-стриминга", $tags = "microService")
   Container(notification_service, "Сервис нотификаций", "C#, .NET Core, ASP.NET Core", "Сервис нотификаций", $tags = "microService")
   Container(message_broker, "Брокер сообщений", "Kafka", "Транспорт для бизнес-событий")

   ContainerDb(conference_db, "База данных конференции", "PostgreSQL", "Хранение участников, спикеров, залов", $tags = "storage")
   ContainerDb(report_db, "База данных докладов", "PostgreSQL", "Хранение докладов, презентаций и статусов рассмотрения", $tags = "storage")
   ContainerDb(schedule_db, "База данных расписаний", "PostgreSQL", "Хранение расписания конференции", $tags = "storage")
   ContainerDb(feedback_db, "База данных оценок", "ClickHouse", "Хранение оценок докладов", $tags = "storage")
   ContainerDb(schedule_cache, "Кэш расписаний", "Redis", "In-memory кэш расписаний", $tags = "storage")
   ContainerDb(video_storage, "Хранилище видео контента", "Ceph", "Хранилище видео контента (записи конференции)", $tags = "storage")
}

System_Ext(email_system, "Почтовый сервис", "Система рассылок EMail.")  

Lay_D(message_broker, feedback_aggregation_service)
Lay_D(schedule_db, schedule_replication_service)
Lay_D(message_broker, notification_service)

Rel(participant, frontend, "", "")
Rel(speaker, frontend, "", "")
Rel(expert, frontend, "", "")
Rel(admin, frontend, "", "")

Rel(frontend, load_balancer, "TODO", "HTTPS")
Rel(load_balancer, conference_mngmt_service, "TODO", "HTTP")
Rel(load_balancer, report_mngmt_service, "TODO", "HTTP")
Rel(load_balancer, schedule_mngmt_service, "TODO", "HTTP")
Rel(load_balancer, feedback_mngmt_service, "TODO", "HTTP")

Rel(conference_mngmt_service, conference_db, "TODO", "TCP/SQL")
Rel(report_mngmt_service, report_db, "TODO", "TCP/SQL")
Rel(schedule_mngmt_service, schedule_db, "TODO", "TCP/SQL")
Rel(schedule_mngmt_service, schedule_cache, "TODO", "TCP/SQL")
Rel(feedback_mngmt_service, message_broker, "TODO", "TCP/Kafka protocol")

Rel(schedule_replication_service, schedule_db, "TODO", "TCP/SQL")
Rel(schedule_replication_service, schedule_cache, "TODO", "TCP")

Rel(load_balancer, online_streaming_service, "TODO", "HTTP")
Rel(online_streaming_service, video_storage, "TODO", "HTTP")

Rel(feedback_mngmt_service, feedback_db, "Читает данные из", "TCP/SQL")

Rel(feedback_aggregation_service, message_broker, "", "")
Rel(feedback_aggregation_service, feedback_db, "", "")

Rel(notification_service, message_broker, "", "")
Rel(notification_service, email_system, "", "")

SHOW_LEGEND()
@enduml
```

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

AddElementTag("microService", $shape=EightSidedShape(), $bgColor="CornflowerBlue", $fontColor="white", $legendText="microservice")
AddElementTag("storage", $shape=RoundedBoxShape(), $bgColor="lightSkyBlue", $fontColor="white")

Person(participant, "Участник конференции", "Посетитель конфереции")
Person(speaker, "Докладчик", "Выступающий перед аудиторией")
Person(expert, "Эксперт", "Сотрудник программного комитета")
Person(adminStaff, "Администратор", "Административный персонал")

System_Boundary(helloConf, "HelloConf") {
   Container(frontend, "Клиентское веб-приложение", "html, JavaScript, Angular", "Веб-портал helloconf")

   Container(ordering_service, "Product Ordering Service", "Golang, nginx", "Сервис управления заказом", $tags = "microService")

   Container(conference_mngmt_service, "Conference management service", "Java, Spring Boot", "Сервис управления продуктовым предложением", $tags = "microService")      
   ContainerDb(offering_db, "Product Catalog", "PostgreSQL", "Хранение продуктовых предложений", $tags = "storage")
   
   Container(ordering_service, "Product Ordering Service", "Golang, nginx", "Сервис управления заказом", $tags = "microService")      
   ContainerDb(ordering_db, "Order Inventory", "MySQL", "Хранение заказов", $tags = "storage")
    
   Container(message_bus, "Message Bus", "RabbitMQ", "Транспорт для бизнес-событий")
   Container(audit_service, "Audit Service", "C#/.NET", "Сервис аудита", $tags = "microService")      
   Container(audit_store, "Audit Store", "Event Store", "Хранение произошедших события для аудита", $tags = "storage")
}

System_Ext(logistics_system, "msLogistix", "Система управления доставкой товаров.")  

Lay_R(offering_service, ordering_service)
Lay_R(offering_service, logistics_system)
Lay_D(offering_service, audit_service)

Rel(customer, app, "Оформление заказа", "HTTPS")
Rel(app, offering_service, "Выбор продуктов для корзины(Продукт):корзина", "JSON, HTTPS")

Rel(offering_service, message_bus, "Отправка заказа(Корзина)", "AMPQ")
Rel(offering_service, offering_db, "Сохранение продуктового предложения(Продуктовая спецификация)", "JDBC, SQL")

Rel(ordering_service, message_bus, "Получение заказа: Корзина", "AMPQ")
Rel_U(audit_service, message_bus, "Получение события аудита(Событие)", "AMPQ")

Rel(ordering_service, ordering_db, "Сохранение заказа(Заказ)", "SQL")
Rel(audit_service, audit_store, "Сохранение события(Событие)")
Rel(ordering_service, logistics_system, "Доставка(Наряд на доставку):Трекинг", "JSON, HTTP")  

SHOW_LEGEND()
@enduml
```

## Список компонентов
| Компонент             | Роль/назначение                  |
|:----------------------|:---------------------------------|
| *Название компонента* | *Описание назначения компонента* |