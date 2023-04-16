# Контекст решения
<!-- Окружение системы (роли, участники, внешние системы) и связи системы с ним. Диаграмма контекста C4 и текстовое описание. 
Подробнее: https://confluence.mts.ru/pages/viewpage.action?pageId=375783261
-->

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

Person(participant, "Участник конференции", "Посетитель конференции, просматривающий доклады")
Person(speaker, "Докладчик", "Докладчик конференции, который выступает с докладами перед участниками")
Person(expert, "Эксперт программного комитета", "Эксперт, который утверждает доклады для конференции")

System(helloconf_platform, "Платформа онлайн-конференции", "Позволяет зарегистрироваться на конференцию, просматривать расписание докладов и онлайн-стримы с выступлениями из залов")
System_Ext(email_system, "E-mail сервис", "Система, отвечающая за почтовые рассылки")


Rel(participant, helloconf_platform, "Использует", "Web")
Rel(speaker, helloconf_platform, "Использует", "Web")
Rel(expert, helloconf_platform, "Использует", "Web")
Rel(helloconf_platform, email_system, "Использует для нотификаций", "SMTP")
Rel(email_system, speaker, "Отправляет email")
Rel(email_system, participant, "Отправляет email")
@enduml
```
