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
}

System_Ext(email_system, "E-mail сервис", "Система, отвечающая за почтовые рассылки")

Rel(admin, conference_mgmnt, "Управляет конференцией")
Rel(admin, schedule_mgmnt, "Создает расписание конференции")
Rel(participant, online_streaming, "Использует")
Rel(participant, feedback_mgmnt, "Оставляет оценку")
Rel(speaker, report_mgmnt, "Подает доклад")
Rel(expert, report_mgmnt, "Оценивает доклад")
Rel(report_mgmnt, email_system, "Использует для нотификаций")
Rel(email_system, speaker, "Отправляет email")
Rel(email_system, participant, "Отправляет email")
@enduml
```
