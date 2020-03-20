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
(ห้องที่ใช้ไม่ได้)
(เอกสาร)

left to right direction

user -right-> (ห้องที่ใช้ไม่ได้)
user -up-> (ลงทะเบียน)
user -up-> (Login)

(ห้องที่ใช้ไม่ได้) <-up. (ห้องซ่อม)
(ห้องที่ใช้ไม่ได้) <-up. (ห้องผู้บริหาร)

user --> (จอง)
user --> (Check-in)
user --> (master)
user --> (Check-out)
user --> (Extra)
user -left-> (เอกสาร)

(เอกสาร) .up-> (ใบเสร็จ)
(เอกสาร) .up-> (Cashier Report)
(เอกสาร) .up-> (รร.4)
(เอกสาร) .up-> (GIH)
(เอกสาร) .left-> (ใบกำกับภาษี)

(จอง) .-right-> (เลือกห้อง)
(Check-in) .left-> (เลือกห้อง)

(master) <-right-. (คืนห้อง)

(ใบกำกับภาษี) <-left. (OB)

(จอง) .-> (คิดเงิน)
(Check-in) .-> (คิดเงิน)
(master) .-> (คิดเงิน)
(Check-out) .-> (คิดเงิน)
(ใบกำกับภาษี) .-> (คิดเงิน)

(master) <-left-. (Extra)
(Check-out) <-right. (Extra)

@enduml