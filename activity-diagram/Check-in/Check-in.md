@startuml
start

:กรอกข้อมูลผู้เข้าพัก;
note right: เลือกข้อมูลจากการสมัครสมาชิก

:ตั้งชื่อ group;
note right: default เป็น ชื่อ-สกุล ผู้พัก

if (มีการจอง?) then (ใช่)
    :เลือกข้อมูลจาก\n"ข้อมูลการจอง";
else (ไม่)
    :กรอกวันที่เข้า-ออก;
    note right
        Fix วันที่"เข้า"
        เป็นวันเวลาปัจจุบัน
    endnote

    :เลือกห้องพัก;
    note right
        - ต้องกรอกวันที่เข้า-ออกก่อน
        จึงสามารถเลือกห้องได้
        - เลือกได้เฉพาะห้องที่ว่าง
        ตามช่วงเวลาที่กรอกมา
    endnote

endif
  
if (มีชื่อ group นี้ในระบบ?) then (มี)
    if (เจ้าของชื่อ group คือ\nmaster ที่กำลัง Check-in?) then (ใช่)
        if (ระบบแจ้ง\n"ต้องการเพิ่มห้องใน\n group เดิมหรือไม่?") then (ใช่)
        :เพิ่มห้องใน group เดิม;
        else (ไม่)
            :ให้เปลี่ยนชื่อ group;
            detach
        endif
    else (ไม่)
        :ให้เปลี่ยนชื่อ group;
        detach
    endif
else (ไม่มี)
    :สร้าง master ใหม่;    
endif

stop
@enduml