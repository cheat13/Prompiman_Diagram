@startuml
start

title Cashier report

if (มีการจัดการรายรับอื่นๆหรือไม่?) then (ใช่)

if (เพิ่มรายการ หรือ ลบรายการ) then (เพิ่ม)
:กรอกข้อมูลและบันทึก;
else(ลบ)
:ลบรายการ;
endif

else (ไม่ใช่)
:พิมพ์;
note right
พิมพ์กะปัจจุบัน=ปิดกะ
end note
endif


stop
@enduml