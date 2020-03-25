@startuml

left to right direction
:Customer: as user
:Front: as front
:Clerkแม่บ้าน :as clerk
(Check-out) as c
(Check-out ไม่ใช่ห้องสุดท้ายของgroup) as c1
(Check-out ห้องสุดท้ายของgroup) as c2
(คิดเงินลูกค้าจะ Check-out) as checkbill
(แจ้งค่าใช้จ่ายเพิ่มเติม) as ex
(แจ้งค่าใช้จ่ายเพิ่มเติมมินิบาร์) as ex1
(แจ้งค่าใช้จ่ายเพิ่มเติมซักรีด) as ex2
(แจ้งค่าใช้จ่ายเพิ่มเติมของชำรุด) as ex3
(เรียกดูค่าใช้จ่ายเพิ่มเติมทั้งหมด) as exDetail

user --> c
c <.- c1
c <.- c2

user --> exDetail
exDetail --> ex
 user .-> checkbill  
front --> checkbill
clerk --> ex 
ex1 -.> ex
ex2 -.> ex
ex3 -.> ex
@enduml