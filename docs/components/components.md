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

   Container(load_balancer, "API Gateway", "Nginx", "Точка входа в систему. Балансировщик нагрузки.")

   Container(conference_mngmt_service, "Сервис управления конференцией", "C#, .NET Core, ASP.NET Core", "Общий сервис управления конференцией", $tags = "microService")
   Container(report_mngmt_service, "Сервис управления докладами", "C#, .NET Core, ASP.NET Core", "Предоставляет функционал по работе с докладами (создание, рассмотрение)", $tags = "microService")
   Container(report_status_notification_service, "Сервис нотификаций о статусе доклада", "C#, .NET Core, ASP.NET Core", "Асинхронно отправляет уведомления об изменении статуса рассмотрения доклада", $tags = "microService")
   Container(report_replication_service, "Сервис репликации докладов", "C#, .NET Core, ASP.NET Core", "Асинхронно реплицирует утвержденные доклады для снижения нагрузки на БД", $tags = "microService")

   Container(schedule_mngmt_service, "Сервис управления расписанием", "C#, .NET Core, ASP.NET Core", "Предоставляет функционал по работе с программой конференции (формирование расписания)", $tags = "microService")
   Container(schedule_replication_service, "Сервис репликации расписаний", "C#, .NET Core, ASP.NET Core", "Асинхронно реплицирует расписания для снижения нагрузки на БД", $tags = "microService")

   Container(feedback_mngmt_service, "Сервис оценки докладов", "C#, .NET Core, ASP.NET Core", "Предоставляет функционал для оценки докладов участниками конференции", $tags = "microService")
   Container(feedback_aggregation_service, "Сервис агрегации оценок", "C#, .NET Core, ASP.NET Core", "Агрегирует и обновляет оценки докладов", $tags = "microService")

   Container(online_streaming_service, "Сервис онлайн стриминга", "C#, .NET Core, ASP.NET Core", "Предоставляет функционал просмотра онлайн-потока и записей конференции", $tags = "microService")
   Container(notification_service, "Сервис нотификаций", "C#, .NET Core, ASP.NET Core", "Предоставляет общий функционал по отправке EMail уведомлений", $tags = "microService")
   Container(message_broker, "Брокер сообщений", "Kafka", "Транспорт для бизнес-событий")

   ContainerDb(conference_db, "База данных конференции", "PostgreSQL", "Хранение участников, спикеров, залов", $tags = "storage")
   ContainerDb(report_db, "База данных докладов", "PostgreSQL", "Хранение докладов, презентаций и статусов рассмотрения", $tags = "storage")
   ContainerDb(schedule_db, "База данных расписаний", "PostgreSQL", "Хранение расписания конференции", $tags = "storage")
   ContainerDb(feedback_db, "База данных оценок", "ClickHouse", "Хранение оценок докладов", $tags = "storage")
   ContainerDb(cache, "Кэш докладов и расписаний", "Redis", "In-memory кэш", $tags = "storage")
   ContainerDb(video_storage, "Хранилище видео контента", "Ceph", "Хранилище видео контента (записей конференции)", $tags = "storage")
}

System_Ext(email_system, "Почтовый сервис", "Внешний почтовый сервер")  

Lay_R(participant, speaker)
Lay_D(speaker, email_system)
Lay_D(message_broker, feedback_aggregation_service)
Lay_D(schedule_db, schedule_replication_service)
Lay_D(message_broker, notification_service)
Lay_D(report_db, report_replication_service)

Rel(participant, frontend, "Просмотр выступления", "WebRTC")
Rel(participant, frontend, "Оценка доклада", "HTTPS")
Rel(speaker, frontend, "Подача доклада", "HTTPS")
Rel(expert, frontend, "Рецензирование доклада", "HTTPS")
Rel(admin, frontend, "Формирование расписания конференции", "HTTPS")

Rel(frontend, load_balancer, "Пользовательский запрос", "HTTPS")

Rel(load_balancer, conference_mngmt_service, "Управление докладчиками/экпертами (CRUD), управление залами (CRUD)", "HTTP")
Rel(load_balancer, report_mngmt_service, "Управление докладами (CRUD)", "HTTP")
Rel(load_balancer, schedule_mngmt_service, "Управление программой конференции (CRUD)", "HTTP")
Rel(load_balancer, feedback_mngmt_service, "Оценка доклада", "HTTP")
Rel(load_balancer, online_streaming_service, "Просмотр онлайн стрима", "HTTP")

Rel(conference_mngmt_service, conference_db, "Хранение информации о конференции", "TCP/SQL")
Rel(report_mngmt_service, report_db, "Хранение информации о докладе", "TCP/SQL")
Rel(report_mngmt_service, cache, "Получение утвержденных докладов", "TCP/Redis QL")
Rel(report_db, report_status_notification_service, "Получение информации об изменении статуса доклада", "TCP/SQL")
Rel(report_replication_service, report_db, "Получение утвержденных докладов", "TCP/SQL")
Rel(report_status_notification_service, message_broker, "Формирования уведомления для пользователя", "TCP/Kafka protocol")
Rel(report_replication_service, cache, "Утвержденные доклады", "TCP/Kafka protocol")

Rel(schedule_mngmt_service, schedule_db, "Хранение информации о расписании", "TCP/SQL")
Rel(schedule_mngmt_service, cache, "Чтение расписания", "TCP/Redis QL")
Rel(feedback_mngmt_service, message_broker, "Событие об оценке доклада", "TCP/Kafka protocol")

Rel(schedule_replication_service, schedule_db, "Получение события об изменении расписания", "TCP/SQL")
Rel(schedule_replication_service, cache, "Обновление расписания", "TCP")

Rel(online_streaming_service, video_storage, "Получение видео-потока", "HTTP")

Rel(feedback_mngmt_service, feedback_db, "Читает данные из", "TCP/SQL")
Rel(feedback_aggregation_service, message_broker, "Получение запросов на отправку нотификаций", "TCP/Kafka protocol")
Rel(feedback_aggregation_service, feedback_db, "Обновление оценки докладов", "TCP")

Rel(notification_service, message_broker, "Чтение событий о нотификациях", "TCP/Kafka protocol")
Rel(notification_service, email_system, "Отправка нотификаций", "SMTP")

Rel(email_system, speaker, "Уведомление о статусе рассмотрения доклада", "SMTP")

SHOW_LEGEND()
@enduml
```

## Список компонентов
| Компонент                            | Роль/назначение                                                                                                                                  |
| :----------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| Участник конференции                 | Человек, участвующий в конференции                                                                                                               |
| Эксперт                              | Член программного комитета, отбирающий доклады для конференции                                                                                   |
| Докладчик                            | Человек, выступающий перед аудиторией с докладом                                                                                                 |
| Администратор                        | Администратор системы, управляет конференцией и формирует расписание                                                                             |
| Клиентское веб-приложение            | Интерфейс пользователя для взаимодействия с системой                                                                                             |
| API Gateway                          | Единая точка доступа к API системы, предоставляет функционал балансировки и другой сквозной функционал                                           |
| Сервис управления конференцией       | Предоставляет функционал по управлению конференцией (участники, залы, ...)                                                                       |
| Сервис управления расписанием        | Предоставляет функционал по управлению программой конференции (добавлене докладов в расписание, ...)                                             |
| Сервис управления докладами          | Предоставляет функционал по управлению докладами (регистрация доклада, рассмотрение и утверждение доклада)                                       |
| Сервис онлайн стриминга              | Предоставляет функционал по онлайн стримингу видеопотока конференции                                                                             |
| Сервис оценки докладов               | Предоставляет функционал для оценки докладов участниками конференции                                                                             |
| Сервис репликации расписаний         | Асинхронно реплицирует расписание в кэш для ускорения доступа на чтение                                                                          |
| Сервис нотификаций о статусе доклада | Асинхронно формирует нотификации об изменении статуса рассмотрения доклада                                                                       |
| Сервис агрегации оценок              | Асинхронно агрегирует и обновляет оценки докладов                                                                                                |
| Сервис нотификации                   | Предоставляет общий функционал по отправке уведомлений пользователям                                                                             |
| Брокер сообщений                     | Брокер сообщений, позволяет распределить по времени нагрузку на некоторые подсистемы приложения за счет асинхронной обработки сообщений          |
| Почтовый сервис                      | Внешняя почтовая система, используемая для отправки EMail сообщений                                                                              |
| База данных конференции              | База данных для микросервиса управления конференцией                                                                                             |
| База данных раписаний                | База данных для микросервиса управления расписаниями                                                                                             |
| База данных докладов                 | База данных для микросервиса управления докладами                                                                                                |
| База данных оценок                   | База данных для хранения оценок докладов                                                                                                         |
| Кэш докладов и расписаний            | Кэш докладов и расписаний, используемый для разгрузки основных баз данных (для проведения конференции нужно будет выводить доклады и расписания) |
| Хранилище видео контента             | Хранилище видео контента с записями выступлений                                                                                                  |
