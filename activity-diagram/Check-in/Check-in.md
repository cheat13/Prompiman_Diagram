@startuml
title Check-in\n(ลงทะเบียนเข้าพัก)
start

:ตรวจสอบข้อมูลลูกค้าในระบบ;

if (เคยลงทะเบียนแล้ว?) then (ไม่ใช่)
    partition ref {
        :ลงทะเบียนสมาชิก;
    }
else (ใช่)
endif

if (ลูกค้าเป็นชาวต่างชาติ?) then (ใช่)
    :ขอถ่ายรูป passport+visa
    ส่งไลน์ ตม.;
else (ไม่ใช่)
endif

:กรอกข้อมูลผู้เข้าพัก;
note right 
    เลือกข้อมูลที่ได้หลัง
    จากการสมัครสมาชิก
endnote

:ตั้งชื่อกลุ่ม;
note right: (default: ชื่อ-สกุล ผู้พัก)

if (มีการจอง?) then (ใช่)
    :เลือกข้อมูลจาก\n"ข้อมูลการจอง";
else (ไม่)
    :กรอกวันที่เข้า-ออก;
    note right
        Fix วันที่"เข้า"
        เป็นวันเวลาปัจจุบัน
    endnote

    partition ref {
        :เลือกห้องพักที่ว่าง;
        note right
            - (disabled) ต้องกรอก
            วันที่เข้า-ออก ก่อน
            จึงสามารถเลือกห้องได้
            - เลือกได้เฉพาะห้องที่ว่าง
            ตามช่วงเวลาที่กรอกมา
        endnote
    }

endif

:ระบุว่ามีการจ่ายค่ามัดจำ;
note right: (default: เลือก)
:ระบุว่ามีการขอใบกำกับภาษี;
note right: (default: ไม่เลือก)

(B)
if (มีชื่อกลุ่มนี้ในระบบ?) then (มี)
    if (เจ้าของชื่อกลุ่มคือ\nmaster ที่กำลัง Check-in?) then (ใช่)
        :         ระบบแจ้ง\n"ต้องการเพิ่มห้องใน\nกลุ่มเดิมหรือไม่?;
        if (เพิ่มห้องในกลุ่มเดิม?") then (ใช่)
        :tag ว่าเป็นการ\nเพิ่มห้องในกลุ่มเดิม;
        else (ไม่)
            (A)
            detach
        endif
    else (ไม่)
        (A)
        detach
    endif
else (ไม่มี)
    :tag ว่าเป็นการ\nสร้าง master ใหม่;    
endif

:เลือกรายการที่จะจ่าย;
note right
    สามารถเลือกจ่ายบางรายการ
    หรือทั้งหมดได้
    (default: เลือกทั้งหมด)
endnote

partition ref {
    :คิดเงิน;
}

:บันทึกข้อมูลการ Check-in;
note right
    - จัดการห้องที่ถูก Check-in 
      ให้กลายเป็นห้องที่มีการเข้าพัก
endnote
stop

(A)
:            ระบบแจ้ง\n"กรุณาเปลี่ยนชื่อกลุ่ม";
:เปลี่ยนชื่อกลุ่ม;
(B)

@enduml