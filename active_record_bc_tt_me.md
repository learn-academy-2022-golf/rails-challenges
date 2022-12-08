# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# NOTES

Add five family members into the Person table in the Rails console (terminal cut off so we couldn't retrieve everything but yess)

", "Dwayne"], ["last_name", "Carta"], ["phone", "9873334543"], ["created_at", "2022-12-05 22:14:49.122457"], ["updated_at", "2022-12-05 22:14:49.122457"]]
TRANSACTION (2.0ms)  COMMIT                                                                      
=>                                                                                                
#<Person:0x00007fa5e18844e0                                                                        
id: 4,                                                                                            
first_name: "Dwayne",                                                                             
last_name: "Carta",                                                                               
phone: "9873334543",                                                                              
created_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00,                                       
updated_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00>                                       
3.0.0 :006 > Person.create first_name:"Daniel", last_name:"Trubey", phone:"1234567890"
TRANSACTION (1.6ms)  BEGIN
Person Create (1.4ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Daniel"], ["last_name", "Trubey"], ["phone", "1234567890"], ["created_at", "2022-12-05 22:15:28.411672"], ["updated_at", "2022-12-05 22:15:28.411672"]]
TRANSACTION (0.9ms)  COMMIT                                                                       
=>                                                                                                 
#<Person:0x00007fa5e0855b50                                                                         
id: 5,                                                                                             
first_name: "Daniel",                                                                              
last_name: "Trubey",                                                                               
phone: "1234567890",                                                                               
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,                                        
updated_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00>



Retrieve all the items in the database

3.0.0 :008 > Person.all
Person Load (3.5ms)  SELECT "people".* FROM "people"
=>                                                           
[#<Person:0x00007fa5e2b2fae0                                  
id: 1,                                                      
first_name: "Blake",                                        
last_name: "Carta",                                         
phone: "2874583225",                                        
created_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00, 
updated_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00>,
#<Person:0x00007fa5e2b2f9a0                                  
id: 2,                                                      
first_name: "Tabi",                                         
last_name: "Trubey",                                        
phone: "9874320841",                                        
created_at: Mon, 05 Dec 2022 22:13:16.918559000 UTC +00:00, 
updated_at: Mon, 05 Dec 2022 22:13:16.918559000 UTC +00:00>,
#<Person:0x00007fa5e2b2f8d8
id: 3,
first_name: "Manny",
last_name: "Espinoza",
phone: "2384984572",
created_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00>,
#<Person:0x00007fa5e2b2f810
id: 4,
first_name: "Dwayne",
last_name: "Carta",
phone: "9873334543",
created_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00>,
#<Person:0x00007fa5e2b2f720
id: 5,
first_name: "Daniel",
last_name: "Trubey",
phone: "1234567890",
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00>] 



Retrieve all the entries that have the same last_name as you

3.0.0 :009 > Person.where last_name:"Carta"
Person Load (0.2ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Carta"]]
=>                                                           
[#<Person:0x00007fa5e0988bf8                                  
id: 1,                                                      
first_name: "Blake",                                        
last_name: "Carta",                                         
phone: "2874583225",                                        
created_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00, 
updated_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00>,
#<Person:0x00007fa5e0988ae0                                  
id: 4,                                                      
first_name: "Dwayne",                                       
last_name: "Carta",                                         
phone: "9873334543",                                        
created_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00, 
updated_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00>] 



Update the phone number of the last entry in the database

3.0.0 :013 > last_phone.phone = "0987654321"
=> "0987654321" 
3.0.0 :014 > last_phone
=> 
#<Person:0x00007fa5e290fe40                                       
id: 5,                                                           
first_name: "Daniel",                                            
last_name: "Trubey",                                             
phone: "0987654321",                                             
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,      
updated_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00>      
3.0.0 :015 > Person.all
Person Load (0.7ms)  SELECT "people".* FROM "people"
=>                                                               
updated_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00>,
#<Person:0x00007fa5e3124d88                                  
id: 2,                                                      
first_name: "Daniel",
last_name: "Trubey",
phone: "1234567890",
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00>] 
3.0.0 :016 > last_phone
=> 
#<Person:0x00007fa5e290fe40 
id: 5,                     
first_name: "Daniel",      
last_name: "Trubey",       
phone: "0987654321",       
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00> 
3.0.0 :017 > last_phone.save
TRANSACTION (3.5ms)  BEGIN
Person Update (9.8ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "0987654321"], ["updated_at", "2022-12-05 22:26:10.941301"], ["id", 5]]                                                 
TRANSACTION (2.0ms)  COMMIT                                     
=> true



Retrieve the first_name of the third Person in the database

3.0.0 :019 > Person.find 3
Person Load (0.4ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
=>                                                           
#<Person:0x00007fa5e07a0c78                                   
id: 3,                                                       
first_name: "Manny",                                         
last_name: "Espinoza",                                       
phone: "2384984572",                                         
created_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00,  
updated_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00>  
3.0.0 :021 > third_first_name = Person.find 3
Person Load (0.3ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
=>                                                                                     
#<Person:0x00007fa5e1df28a0                                                             
...                                                                                     
3.0.0 :022 > third_first_name.first_name
=> "Manny"



Update all the family members with the same last_name as you, to have the same phone number as you
# Created my_fam variable and assigned to it all instances where last_name="Trubey"

3.0.0 :027 > my_fam.update phone:"4546768989"
TRANSACTION (0.3ms)  BEGIN
Person Update (1.9ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "4546768989"], ["updated_at", "2022-12-05 22:39:52.581592"], ["id", 2]]
TRANSACTION (8.8ms)  COMMIT                              
TRANSACTION (1.9ms)  BEGIN                               
Person Update (1.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "4546768989"], ["updated_at", "2022-12-05 22:39:52.595190"], ["id", 5]]
TRANSACTION (2.1ms)  COMMIT                              
=>                                                        
[#<Person:0x00007fa5e1f9a4f0                               
id: 2,                                                   
first_name: "Tabi",                                      
last_name: "Trubey",                                     
phone: "4546768989",                                     
created_at: Mon, 05 Dec 2022 22:13:16.918559000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:39:52.581592000 UTC +00:00>,
#<Person:0x00007fa5e1f9a428                               
id: 5,
first_name: "Daniel",
last_name: "Trubey",
phone: "4546768989",
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:39:52.595190000 UTC +00:00>] 
3.0.0 :028 > my_fam.save
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation/delegation.rb:110:in `method_missing': undefined method `save' for #<ActiveRecord::Relation [#<Person id: 2, first_name: "Tabi", last_name: "Trubey", phone: "4546768989", created_at: "2022-12-05 22:13:16.918559000 +0000", updated_at: "2022-12-05 22:39:52.581592000 +0000">, #<Person id: 5, first_name: "Daniel", last_name: "Trubey", phone: "4546768989", created_at: "2022-12-05 22:15:28.411672000 +0000", updated_at: "2022-12-05 22:39:52.595190000 +0000">]> (NoMethodError)
3.0.0 :029 > my_fam
=> 
[#<Person:0x00007fa5e1f9a4f0                          
id: 2,                                              
first_name: "Tabi",                                 
last_name: "Trubey",                                
phone: "4546768989",                                
created_at: Mon, 05 Dec 2022 22:13:16.918559000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:39:52.581592000 UTC +00:00>,
#<Person:0x00007fa5e1f9a428                          
id: 5,                                              
first_name: "Daniel",                               
last_name: "Trubey",
phone: "4546768989",
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:39:52.595190000 UTC +00:00>]



Remove all family members that do not have your last_name

3.0.0 :035 > not_trubey = Person.where "last_name != 'Trubey'"
Person Load (10.0ms)  SELECT "people".* FROM "people" WHERE (last_name != 'Trubey')
=>                     
[#<Person:0x00007fa5e1f185e0
...  

3.0.0 :043 > not_trubey
=> 
[#<Person:0x00007fa5e1f185e0
id: 1,                
first_name: "Blake",  
last_name: "Carta",   
phone: "2874583225",  
created_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:11:22.984991000 UTC +00:00>,
#<Person:0x00007fa5e1f18518
id: 3,
first_name: "Manny",
last_name: "Espinoza",
phone: "2384984572",
created_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:13:48.553091000 UTC +00:00>,
#<Person:0x00007fa5e1f18450
id: 4,
first_name: "Dwayne",
last_name: "Carta",
phone: "9873334543",
created_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00,
updated_at: Mon, 05 Dec 2022 22:14:49.122457000 UTC +00:00>]

3.0.0 :049 > Person.where("last_name != 'Trubey'").delete_all
Person Delete All (2.4ms)  DELETE FROM "people" WHERE (last_name != 'Trubey')
=> 3  

3.0.0 :050 > Person.all
Person Load (2.5ms)  SELECT "people".* FROM "people"
=>                                                                                                           
[#<Person:0x00007fa5e0ed9d78                                                                                 
id: 2,                                                                                                     
first_name: "Tabi",                                                                                        
last_name: "Trubey",                                                                                       
phone: "4546768989",                                                                                       
created_at: Mon, 05 Dec 2022 22:13:16.918559000 UTC +00:00,                                                
updated_at: Mon, 05 Dec 2022 22:39:52.581592000 UTC +00:00>,                                               
#<Person:0x00007fa5e0ed9cb0                                                                                 
id: 5,                                                                                                    
first_name: "Daniel",                                                                                     
last_name: "Trubey",                                        
phone: "4546768989",                                        
created_at: Mon, 05 Dec 2022 22:15:28.411672000 UTC +00:00, 
updated_at: Mon, 05 Dec 2022 22:39:52.595190000 UTC +00:00>] 
