@startuml
title ปิด_Master
start

:ค้นหา master จากชื่อกลุ่ม;
note right
    หรือมาจากการ Check-out/คืนห้อง 
    ที่เป็นห้องสุดท้ายของ master
endnote

:เลือก ปิด master;
note right
    ไม่สามารถปิด master ได้
    หากยังมีห้องที่มีสถานะ "เข้าพัก"
endnote

if (มีค่าใช้จ่าย/ยอดเงินคงค้าง?) then (มี)
    if (ต้องการชำระเงิน?) then (ใช่)
        partition ref {
            :คิดเงิน;
            note left
                ชำระยอดคงค้างทั้งหมด
            endnote
        }
    else (ไม่)
        :ยังไม่สามารถปิด master ได้;
        end
    endif
else (ไม่มี)
endif

:บันทึกการปิด master;

stop
@enduml