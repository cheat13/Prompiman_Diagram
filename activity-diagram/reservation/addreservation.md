@startuml
title จองห้องพักล่วงหน้า
start
:เพิ่มการจองหน้าพักล่วงหน้า;

partition ref {
	:เลือกห้องพักที่ว่าง;
} 
-> [ถ้าข้อมูลไม่ครบกดไปต่อไม่ได้]; 
partition ref {
	:คิดเงิน;
}
note right
เงินสำรองจ่ายสามารถเป็น 0 ได้ 
end note
stop
@enduml



