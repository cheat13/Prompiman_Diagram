@startuml

|Extra page|
start
  :เลือกชั้น;
while (เลือกชั้น?) is (no)
  :เลือกใหม่;
endwhile (yes)
  :เลือกหมายเลขห้อง;

  while (เลือกห้อง?) is (no)
  :button "เพิ่มเอ็กซ์ตร้า" disable;
  :เลือกใหม่;
endwhile (yes)
fork
  |Extra page|
  :แสดงประวัติ Extra ห้องนั้น;
  :click list extra ;
  |dlg DetailExtra page|
  :show detail extra;
  : click button "ปิด";

  |Extra page|
  fork again
  :button "เพิ่มเอ็กซ์ตร้า" enable;
  :click button "เพิ่มเอ็กซ์ตร้า";
  |dlg AddExtra page|
  :แสดงฟอร์มกรอกข้อมูล Extra;
  :กรอกข้อมูล;
while (กรอกข้อมูลครบ?) is (no)
  :กลับไปกรอกให้ครบ;
endwhile (yes)
  : button "บันทึก" enable;
fork
  :click button "บันทึก" ;
  :บันทึกข้อมูลลง DB และแสดงที่หน้า Extra;
fork again
  : click button "ยกเลิก" ;
  : ยกเลิกข้อมูลทั้งหมด;
 end fork
 end fork

  |Extra page|
stop

@enduml