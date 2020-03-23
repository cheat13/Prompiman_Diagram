@startuml
start
 -> เฉพาะห้องที่มีการ checkin;
  :เลือก checkout ห้องที่ต้องการ;
  if(มีค่าใช้จ่ายเพิมเติมหรือไม่) then (yes)
    : ค่าใช้จ่ายเพิมเติม;
  else(no)
    endif
    : ทำการเลือกคิดเงิน และจ่ายเงิน;
stop;

@enduml