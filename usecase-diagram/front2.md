@startuml

:Front: as user
(Login)
(จอง)
(ลงทะเบียน)
(เลือกห้อง)
(Check-in)
(Check-out)
(Master Detail) as (master)
(ห้องผู้บริหาร)
(ห้องซ่อม)
(Guest in House) as (GIH)
(รร.4)
(Cashier Report)
(ใบกำกับภาษี)
(ใบเสร็จ)
(Extra)
(Over Bill) as (OB)
(คิดเงิน)
(คืนห้อง)

left to right direction

user -up-> (ใบเสร็จ)
user -up-> (Cashier Report)
user -up-> (รร.4)
user -up-> (GIH)
user -up-> (ห้องซ่อม)
user -up-> (ห้องผู้บริหาร)
user -up-> (ลงทะเบียน)
user -up-> (Login)

user --> (จอง)
user --> (Check-in)
user --> (master)
user --> (Check-out)
user --> (Extra)
user --> (ใบกำกับภาษี)

(จอง) .-right-> (เลือกห้อง)
(Check-in) .left-> (เลือกห้อง)

(master) <-right-. (คืนห้อง)

(ใบกำกับภาษี) <-. (OB)

(จอง) .-> (คิดเงิน)
(Check-in) .-> (คิดเงิน)
(master) .-> (คิดเงิน)
(Check-out) .-> (คิดเงิน)
(ใบกำกับภาษี) .-> (คิดเงิน)

(master) <-left-. (Extra)
(Check-out) <-right. (Extra)

@enduml