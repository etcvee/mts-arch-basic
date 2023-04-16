# Модель предметной области
<!-- Логическая модель, содержащая бизнес-сущности предметной области, атрибуты и связи между ними. 
Подробнее: https://confluence.mts.ru/pages/viewpage.action?pageId=375782602

Используется диаграмма классов UML. Документация: https://plantuml.com/class-diagram 
-->

```plantuml
@startuml

namespace ConferenceManagement {
    class Participant {
        Id: Integer
        FirstName : String
        LastName : String
        Patronymic : String
        Mobile: String
        EMail: String
        Company: String
        Bio: String
    }

    class Speaker {
    }

    class Expert {
    }

    note bottom of Expert: Для типизации\n+ м.б. специфичные атрибуты
    note bottom of Speaker: Для типизации\n+ м.б. специфичные атрибуты

    class Room {
        Id: Integer
        Name: String
        Description: String
    }

    Participant <|-- Speaker
    Participant <|-- Expert
}

namespace ReportManagement {
    class SpeakerRef {
        Id: Integer
    }

    class ExpertRef {
        Id: Integer
    }

    class Report {
        Id: Integer
        Name: String
        Description: String
        Speaker: SpeakerRef
        Reviewer: ExpertRef
        Status: ReportStatus
        Feedback: ReviewFeedback
        Presentation: Presentation
    }

    class Presentation {
        Id: Integer
        File: Files[]
    }

    class File {
        Id: Integer
        Name: String
        Content: Binary
        CreatedAt: DateTime
    }

    class ReviewFeedback {
        Id: Integer
        Date: DateTime
        Comment: String
    }

    enum ReportStatus {
        Pending
        Reviewing
        Approved
        Rejected
        Withdrawn
    }

    Report *-- SpeakerRef
    Report *-- ExpertRef
    Report *-- ReportStatus
    Report *-- ReviewFeedback
    Report *-- Presentation

    Presentation *-- File

    SpeakerRef ..> ConferenceManagement.Speaker : ref
    ExpertRef ..> ConferenceManagement.Expert : ref
}

namespace OnlineStreaming {
    class Stream {
        Id: Integer
        Room: RoomRef
        WatchUrl: Url
        Administrators: UserRef[]
        Watchers: UserRef[]
    }

    class RoomRef {
        Id: Integer
    }

    class UserRef {
        Id: Integer
    }

    class Url {
        Value: String
    }

    Stream *-- RoomRef
    Stream *-- UserRef
    Stream *-- Url

    UserRef ..> ConferenceManagement.Participant : ref
    RoomRef ..> ConferenceManagement.Room : ref
}

namespace FeedbackManagement {
    class Feedback {
        Id: Integer
        User: UserRef
        Entries: FeedbackEntry[]
    }

    class FeedbackEntry {
        Id: Integer
        Report: ReportRef
        Rate: Rate
        Comment: String
    }

    class Rate {
        Value: Integer   
    }

    class ReportRef {
        Id: Integer
    }

    class UserRef {
        Id: Integer
    }

    Feedback *-- FeedbackEntry
    FeedbackEntry *-- ReportRef
    FeedbackEntry *-- UserRef
    FeedbackEntry *-- Rate
    
    UserRef ..> ConferenceManagement.Participant : ref
    ReportRef ..> ReportManagement.Report : ref
}

namespace ScheduleManagement {
    class Schedule {
        Id: Integer
        Date: Date
        TimeSlots: TimeSlot[]
    }

    class TimeSlot {
        Id: String
        StartTime: Time
        EndTime: Time
        Room: RoomRef
        Report: ReportRef
    }

    class RoomRef {
        Id: Integer
    }

    class ReportRef {
        Id: Integer
    }

    Schedule *-- TimeSlot
    TimeSlot *-- RoomRef
    TimeSlot *-- ReportRef

    ReportRef ..> ReportManagement.Report : ref
    RoomRef ..> ConferenceManagement.Room : ref
}
@enduml
```