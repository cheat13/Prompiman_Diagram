@startuml
start

title ขอใบกำกับภาษี-เคสพักรร.

:ดึงข้อมูลผู้เข้าพัก;
 note left
 รายชื่อต้นๆคือคนที่แจ้งว่าต้องการใบกำกับภาษี (แจ้งตอน checkin)
 endnote


if(ต้องการเพิ่มหรือแก้ไขข้อมูลใช่หรือไม่)then(ใช่)
:กรอกข้อมูล;
:บันทึกข้อมูล;
else(ไม่ใช่)
endif

:สร้างบิลใหม่;
 note left
 1.มีการบันทึกเลขที่ใบกำกับภาษี (Running No.)
 2.ขึ้นสถานะรอการยืนยันข้อมูล
 endnote

partition ref {
:สถานะ : รอการยืนยันข้อมูล;
}

stop
@enduml
