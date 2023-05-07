# Диаграмма ограниченных контекстов

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

Person(participant, "Участник конференции", "Посетитель конференции, просматривающий доклады")
Person(speaker, "Докладчик", "Докладчик конференции, который выступает с докладами перед участниками")
Person(expert, "Эксперт программного комитета", "Эксперт, который утверждает доклады для конференции")
Person(admin, "Администратор", "Управляет конференцией, составляет расписание")

System_Boundary(helloconf_platform, "Конференция HelloConf") {
    System(conference_mgmnt, "Управление конференцией", "Подсистема управления конференцией")
    System(report_mgmnt, "Управление докладами", "Подсистема управления докладами")
    System(schedule_mgmnt, "Управление расписанием", "Подсистема управления расписанием")
    System(feedback_mgmnt, "Управление оценками", "Подсистема сборка оценок")
    System(online_streaming, "Онлайн трансляция", "Подсистема онлайн трансляции конференции")
    System(frontend_bff, "Frontend & BFF")
    System(message_mngmnt, "Инфраструктура обмена сообщениями")
    System(notification_mngmnt, "Инфраструктура уведомлений")
}

System_Ext(email_system, "E-mail сервис", "Система, отвечающая за почтовые рассылки")

Rel(admin, frontend_bff, "Управляет конференцией")
Rel(admin, frontend_bff, "Создает расписание конференции")
Rel(participant, frontend_bff, "Использует")
Rel(participant, frontend_bff, "Оставляет оценку")
Rel(speaker, frontend_bff, "Подает доклад")
Rel(expert, frontend_bff, "Оценивает доклад")
Rel(email_system, speaker, "Отправляет email")
Rel(email_system, participant, "Отправляет email")
Rel(frontend_bff, conference_mgmnt, "Shared kernel")
Rel(frontend_bff, schedule_mgmnt, "Shared kernel")
Rel(frontend_bff, online_streaming, "Shared kernel")
Rel(frontend_bff, feedback_mgmnt, "Shared kernel")
Rel(frontend_bff, report_mgmnt, "Shared kernel")
Rel(report_mgmnt, notification_mngmnt, "Open Host Service")
Rel(report_mgmnt, message_mngmnt, "Open Host Service")
Rel(feedback_mgmnt, message_mngmnt, "Open Host Service")
Rel(notification_mngmnt, message_mngmnt, "Open Host Service")
Rel(notification_mngmnt, email_system, "Использует для нотификаций")
@enduml
```
