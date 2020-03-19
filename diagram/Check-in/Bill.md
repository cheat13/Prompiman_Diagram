@startuml
|       Main \nCheck-in page|
start
:เลือก master;

|Master-info page|
:เลือก ห้อง;

|Detail page|
:เลือกรายการที่จะจ่าย;
:คลิกปุ่ม "ถัดไป";

|Bill page|
:เลือกประเภทการจ่ายเงิน;
:ระบุจำนวนเงินที่รับ;
:คลิกปุ่ม "ยืนยัน";

|Master-info page|
:Done/
stop

@enduml