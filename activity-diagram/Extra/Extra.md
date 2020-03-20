@startuml
start
 -> เฉพาะห้องที่มีการ checkin;
  :ค่าใช้จ่ายเพิ่มเติม;
  -> เลือกประเภท เพิ่มเติม;
fork
	:มินิบาร์;
  fork again
	:ซักรีด;
  fork again
	:ค่าปรับอุปกรณ์ห้องพัก;
  end fork

  :กรอกและบันทึกข้อมูล ; 
stop;

@enduml