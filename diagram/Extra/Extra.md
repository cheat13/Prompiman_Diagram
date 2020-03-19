@startuml
start
 -> เฉพาะห้องที่มีการ checkin;
  :เพิ่มรายการเอ็กซ์ตร้าที่ ลค. กิน ;
  if(ลค. กิน extra) then (yes)
while(กรอกข้อมูลเอ็กซ์ตร้า) is (yes)
  if (ตรวจสอบข้อมูลที่กรอกครบถ้วนและสมบูรณ์) then (yes)
    : บันทึกข้อมูลเอ็กซ์ตร้า;
stop
  else(no)
  :แจ้งเตือนข้อผิดพลาด;
    endif;
endwhile(no)

else (no)
  :ไม่ทำอะไร;

endif
stop;

@enduml