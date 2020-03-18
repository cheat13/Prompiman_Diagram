@startuml
|       Main \nCheck-in page|
start
:คลิกปุ่ม "+" 
(Check-in);

|Check-in page|
:เลือก master;
:ตั้งชื่อ group;
repeat
if (เลือกจากการจอง?) then (ใช่)
    :เลือกข้อมูลจาก\n"ข้อมูลการจอง";
else (ไม่)
    :ระบุเวลาเข้า-ออก;
    :คลิกปุ่ม "ค้นหาห้อง";

    |Rooms page|
    :เลือกห้อง;
    :คลิกปุ่ม "ยืนยัน";
endif

|Check-in page|
:คลิกปุ่ม "ถัดไป";
if (มี group?) then (ใช่)
    if (มี master?) then (ใช่)
        :เพิ่มห้อง/
    else (ไม่)
        :ให้เปลี่ยนชื่อ group;
        detach
    endif
else (ไม่)
    :สร้าง register ใหม่/
endif

|Detail page|
:เลือกรายการที่จะจ่าย;
:คลิกปุ่ม "ถัดไป";

|Bill page|
:เลือกประเภทการจ่ายเงิน;
:ระบุจำนวนเงินที่รับ;
:คลิกปุ่ม "ยืนยัน";

|Master-info page|
:Done/
repeat while (คลิกปุ่ม "เพิ่มห้องพัก"?) is (ใช่)
->ไม่;
stop

@enduml