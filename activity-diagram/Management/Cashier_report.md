@startuml
start

title Cashier report

if (มีการจัดการรายรับอื่นๆหรือไม่?) then (ใช่)

if (เพิ่มรายการ หรือ ลบรายการ) then (เพิ่ม)
:กรอกข้อมูล;
else(ลบ)
:ลบรายการ;
endif
:บันทึก;

else (ไม่ใช่)
note right
พิมพ์กะปัจจุบัน=ปิดกะ
end note
endif
:พิมพ์;


stop
@enduml