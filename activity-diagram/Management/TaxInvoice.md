@startuml
start

title ใบกำกับภาษี 

split
 :เพิ่มใบกำกับภาษี;
if(มีการใช้บริการโรงแรม) then(ใช่)
:เพิ่มรายการ;

split
 :แบบปกติ;
split again
 :แบบ Overbill;
end split

else(ไม่ใช่)
:เพิ่มรายการแบบ Overbill;
endif

:บันทึกข้อมูล;

split again
 :ยืนยันใบกำกับภาษี;
if(ต้องการแก้ไขข้อมูล) then(ใช่)
:แก้ไขและบันทึก;

else(ไม่ใช่)
:ยืนยันข้อมูลที่แสดง;
:ทำการคิด-จ่ายเงิน;
:ยืนยันการบันทึกข้อมูล;

endif 

split again
 :ยกเลิกใบกำกับภาษี; 
 :ยืนยันการยกเลิก;
 
end split
stop
@enduml