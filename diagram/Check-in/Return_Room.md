@startuml
|       Main \nCheck-in page|
start
:เลือก master;

|Master-info page|
:เลือก ห้อง;

|Detail page|
:คลิกปุ่ม "คืนห้อง";

|dlg Retrun Room page|
:กรอกหมายเหตุ;
:ระบุจำนวนเงินค่าห้อง;
:คลิกปุ่ม "ยืนยัน";

|Master-info page|
:Done/
stop

@enduml