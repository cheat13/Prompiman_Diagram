@startuml
title ปิด_Master
start

:ค้นหา master จากชื่อกลุ่ม;
:เลือก ปิด master;
note right
    ไม่สามารถปิด master ได้
    หากยังมีห้องที่มีสถานะ "เข้าพัก"
endnote

if (มีค่าใช้จ่าย/ยอดเงินคงค้าง?) then (มี)
    :คิดเงิน|
    note left
        เลือกรายการจ่ายทั้งหมด
    endnote
else (ไม่มี)
endif

:บันทึกการปิด master;

stop
@enduml