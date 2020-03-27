@startuml
title checkout
start
    : เลือกห้อง checkout ;
    note right   
    เลือกได้เฉพาะห้องที่มีการ checkin
    end note  
  if(มีค่าใช้จ่ายเพิมเติมที่ตกค้างยังไม่แจ้งหรือไม่) then (yes)
    : แจ้งค่าใช้จ่ายเพิ่มเติม|
  else(no)
    endif
    : คิดเงิน| 
    note right
     หากลูกค้าไม่จ่ายให้ กรอกเงินที่จ่ายเป็น 0
    end note  
    : บันทึกข้อมูลและเช็กเอ้าท์ห้องนั้นๆ;
    note right
      ถ้าห้องที่เลือกเป็นห้องสุดท้ายของ master นั้นๆ
      *เสร็จสิ้นกระบวนการจะไปหน้า master-detail เพื่อไปเป็นกระบวนการปิด master นั้นๆ
    end note  

 
stop;


@enduml