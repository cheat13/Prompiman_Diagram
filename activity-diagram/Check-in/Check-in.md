@startuml
start

:กรอกข้อมูลผู้พัก;
note right
    - ชื่อ-สกุล/เบอร์โทร 
    (ได้หลังจากการสมัครสมาชิก)
    - ชื่อ group
    (default เป็น ชื่อ-สกุล ผู้พัก)
end note

if (มีการจอง?) then (ใช่)
    :เลือกข้อมูลจาก\n"ข้อมูลการจอง";
else (ไม่)
    :กรอกข้อมูลห้องพัก;
    note right
        - วันที่เข้า 
        (Fix เป็นวันเวลาปัจจุบัน)
        - วันที่ออก 
        - ห้องพัก
        (ที่ว่างตามช่วงเวลาที่ระบุ)
    end note
endif

if (มีชื่อ group นี้ในระบบ?) then (ใช่)
    if (เจ้าของชื่อ group คือ\nmaster ที่กำลัง Check-in?) then (ใช่)
        :เพิ่มห้องใน group;
    else (ไม่)
        :ให้เปลี่ยนชื่อ group;
        detach
    endif
else (ไม่)
    :สร้างใบ register ใหม่;    
endif

stop
@enduml