Challenge: Rolodex
As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

Set Up

Create a new Rails app named 'rolodex_challenge'.
Create the database. The output in the terminal should look like this:
Created database 'rolodex_development'
Created database 'rolodex_test'
Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
Run a migration to set up the database.
Open up Rails console.
Actions

Add five family members into the Person table in the Rails console.
Retrieve all the items in the database.
Add yourself to the Person table.
Retrieve all the entries that have the same last_name as you.
Update the phone number of the last entry in the database.
Retrieve the first_name of the third Person in the database.
Stretch Challenges

Update all the family members with the same last_name as you, to have the same phone number as you.
Remove all family members that do not have your last_name.

Last login: Mon Dec  5 10:19:37 on ttys001
➜  rolodex_challenge git:(main) ✗ cd ..
➜  rails-practice-app cd rolodex_challenge 
➜  rolodex_challenge git:(main) ✗ rails generate model Person first_name:string last_name:string phone:string
      invoke  active_record
      create    db/migrate/20221205220115_create_people.rb
      create    app/models/person.rb
➜  rolodex_challenge git:(main) ✗ rails db:migrate
== 20221205220115 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.1294s
== 20221205220115 CreatePeople: migrated (0.1306s) ============================

➜  rolodex_challenge git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Person.create first_name: "Zeke", last_name: "Ip", phone:"123-234-4567"
  TRANSACTION (22.7ms)  BEGIN
  Person Create (4.6ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Zeke"], ["last_name", "Ip"], ["phone", "123-234-4567"], ["created_at", "2022-12-05 22:07:31.163759"], ["updated_at", "2022-12-05 22:07:31.163759"]]                 
  TRANSACTION (3.8ms)  COMMIT                                                                   
 =>                                                                                             
#<Person:0x00007f94d55cb950                                                                     
 id: 1,                                                                                         
 first_name: "Zeke",                                                                            
 last_name: "Ip",                                                                               
 phone: "123-234-4567",                                                                         
 created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,                                    
 updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>                                    
3.0.0 :002 > Person.create first_name: "Bettina", last_name: "Franz-Ip", phone: "234-456-6779"
  TRANSACTION (11.1ms)  BEGIN
  Person Create (0.9ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Bettina"], ["last_name", "Franz-Ip"], ["phone", "234-456-6779"], ["created_at", "2022-12-05 22:08:35.171875"], ["updated_at", "2022-12-05 22:08:35.171875"]]                 
  TRANSACTION (1.2ms)  COMMIT                                                                            
 =>                                                                                                      
#<Person:0x00007f94d7a5e448                                                                              
 id: 2,                                                                                                  
 first_name: "Bettina",                                                                                  
 last_name: "Franz-Ip",                                                                                  
 phone: "234-456-6779",                                                                                  
 created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00,                                             
 updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>                                             
3.0.0 :003 > Person.create first_name: "Arista", last_name: "Ip", phone: "234-456-6770"
  TRANSACTION (21.2ms)  BEGIN
  Person Create (0.9ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Arista"], ["last_name", "Ip"], ["phone", "234-456-6770"], ["created_at", "2022-12-05 22:09:26.518545"], ["updated_at", "2022-12-05 22:09:26.518545"]]
  TRANSACTION (1.0ms)  COMMIT
 => 
#<Person:0x00007f94d1dc84b8
 id: 3,
 first_name: "Arista",
 last_name: "Ip",
 phone: "234-456-6770",
 created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00> 
3.0.0 :004 > Person.create first_name: "Zach", last_name: "Ip", phone: "234-478-6770"
  TRANSACTION (0.4ms)  BEGIN
  Person Create (0.7ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Zach"], ["last_name", "Ip"], ["phone", "234-478-6770"], ["created_at", "2022-12-05 22:09:50.152642"], ["updated_at", "2022-12-05 22:09:50.152642"]]
  TRANSACTION (0.6ms)  COMMIT
 => 
#<Person:0x00007f94d8967278
 id: 4,
 first_name: "Zach",
 last_name: "Ip",
 phone: "234-478-6770",
 created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00> 
3.0.0 :005 > Person.create first_name: "Tony", last_name: "Gidlund", phone: "619-478-6770"
  TRANSACTION (0.5ms)  BEGIN
  Person Create (0.4ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Tony"], ["last_name", "Gidlund"], ["phone", "619-478-6770"], ["created_at", "2022-12-05 22:10:13.246215"], ["updated_at", "2022-12-05 22:10:13.246215"]]
  TRANSACTION (1.0ms)  COMMIT
 => 
#<Person:0x00007f94d5563828
 id: 5,
 first_name: "Tony",
 last_name: "Gidlund",
 phone: "619-478-6770",
 created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00> 
3.0.0 :006 > Person.all
  Person Load (1.0ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x00007f94d8a5cd40                                  
  id: 1,                                                      
  first_name: "Zeke",                                         
  last_name: "Ip",                                            
  phone: "123-234-4567",                                      
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,
 #<Person:0x00007f94d8a5cc00                                  
  id: 2,                                                      
  first_name: "Bettina",                                      
  last_name: "Franz-Ip",                                      
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d8a5cb38
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "234-456-6770",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d8a5ca70
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d8a5c9a8
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>] 
3.0.0 :007 > Person.create first_name: "Renita", last_name: "Gidlund", phone: "619-555-6770"
  TRANSACTION (0.9ms)  BEGIN
  Person Create (0.5ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Renita"], ["last_name", "Gidlund"], ["phone", "619-555-6770"], ["created_at", "2022-12-05 22:10:58.385300"], ["updated_at", "2022-12-05 22:10:58.385300"]]
  TRANSACTION (0.9ms)  COMMIT
 =>                     
#<Person:0x00007f94d8917bd8
 id: 6,                 
 first_name: "Renita",  
 last_name: "Gidlund",  
 phone: "619-555-6770",
 created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00> 
3.0.0 :008 > Person.where last_name:Gidlund
(irb):8:in `<main>': uninitialized constant Gidlund (NameError)
3.0.0 :009 > Person.where last_name:"Gidlund"
  Person Load (1.0ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Gidlund"]]
 =>                                                           
[#<Person:0x00007f94d7b90938                                  
  id: 5,                                                      
  first_name: "Tony",                                         
  last_name: "Gidlund",                                       
  phone: "619-478-6770",                                      
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d7b90870                                  
  id: 6,                                                      
  first_name: "Renita",                                       
  last_name: "Gidlund",                                       
  phone: "619-555-6770",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00>] 
3.0.0 :010 > last_person = Person.last
  Person Load (0.4ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" DESC LIMIT $1  [["LIMIT", 1]]
 =>                                                                         
#<Person:0x00007f94d2f988f0                                                 
...                                                                         
3.0.0 :011 > last_person
 => 
#<Person:0x00007f94d2f988f0                                                 
 id: 6,                                                                     
 first_name: "Renita",                                                      
 last_name: "Gidlund",                                                      
 phone: "619-555-6770",                                                     
 created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,                
 updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00>                
3.0.0 :012 > last_person
 => 
#<Person:0x00007f94d2f988f0 
 id: 6,                     
 first_name: "Renita",      
 last_name: "Gidlund",      
 phone: "619-555-6770",     
 created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00> 
3.0.0 :013 > last_person.phone = "123-456-7890"
 => "123-456-7890" 
3.0.0 :014 > last_person
 => 
#<Person:0x00007f94d2f988f0                                                
 id: 6,                                                                    
 first_name: "Renita",                                                     
 last_name: "Gidlund",                                                     
 phone: "123-456-7890",                                                    
 created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,               
 updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00>               
3.0.0 :015 > Person.all
  Person Load (0.8ms)  SELECT "people".* FROM "people"
 =>                                                                        
[#<Person:0x00007f94d88f6f78                                               
  id: 1,                                                                   
  first_name: "Zeke",                                         
  last_name: "Ip",                                            
  phone: "123-234-4567",                                      
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,
 #<Person:0x00007f94d88f6eb0                                  
  id: 2,                                                      
  first_name: "Bettina",                                      
  last_name: "Franz-Ip",                                      
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d88f6de8
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "234-456-6770",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d88f6d20
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d88f6c58
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d88f6b90
  id: 6,
  first_name: "Renita",
  last_name: "Gidlund",
  phone: "619-555-6770",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00>] 
3.0.0 :016 > last_person.save
  TRANSACTION (21.9ms)  BEGIN
  Person Update (1.1ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "123-456-7890"], ["updated_at", "2022-12-05 22:16:23.649073"], ["id", 6]]
  TRANSACTION (0.7ms)  COMMIT                                      
 => true                                                           
3.0.0 :017 > Person.all
  Person Load (20.6ms)  SELECT "people".* FROM "people"
 =>                                                                
[#<Person:0x00007f94d7965f78                                       
  id: 1,                                                           
  first_name: "Zeke",                                              
  last_name: "Ip",                                                 
  phone: "123-234-4567",                                           
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,      
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,     
 #<Person:0x00007f94d7965de8                                  
  id: 2,                                                      
  first_name: "Bettina",                                      
  last_name: "Franz-Ip",                                      
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d7965c58
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "234-456-6770",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d7965ac8
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d7965938
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d79657a8
  id: 6,
  first_name: "Renita",
  last_name: "Gidlund",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:16:23.649073000 UTC +00:00>] 
3.0.0 :018 > last_person.update last_name:"Ip"
  TRANSACTION (22.5ms)  BEGIN
  Person Update (0.6ms)  UPDATE "people" SET "last_name" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["last_name", "Ip"], ["updated_at", "2022-12-05 22:17:22.596477"], ["id", 6]]  
  TRANSACTION (0.9ms)  COMMIT                                      
 => true                                                           
3.0.0 :019 > Person.all
  Person Load (0.5ms)  SELECT "people".* FROM "people"
 =>                                                                
[#<Person:0x00007f94d8a27078                                       
  id: 1,                                                           
  first_name: "Zeke",                                              
  last_name: "Ip",                                                 
  phone: "123-234-4567",                                           
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,      
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,     
 #<Person:0x00007f94d8a26fb0                                  
  id: 2,                                                      
  first_name: "Bettina",                                      
  last_name: "Franz-Ip",                                      
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d8a26e98
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "234-456-6770",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d8a26d08
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d8a26c40
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d8a26b50
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:17:22.596477000 UTC +00:00>] 
3.0.0 :020 > Person.find 3
  Person Load (0.4ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 =>                                                           
#<Person:0x00007f94d56716e8                                   
 id: 3,                                                       
 first_name: "Arista",                                        
 last_name: "Ip",                                             
 phone: "234-456-6770",                                       
 created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,  
 updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>  
3.0.0 :021 > Person.find(3).first_name
  Person Load (10.7ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 => "Arista"                                                                         
3.0.0 :022 > Person.where last_name: "Ip"
  Person Load (0.8ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Ip"]]
 =>                                                                                  
[#<Person:0x00007f94d83c9c58                                                         
  id: 1,                                                                             
  first_name: "Zeke",                                                                
  last_name: "Ip",                                                                   
  phone: "123-234-4567",                                                             
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,                        
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,                       
 #<Person:0x00007f94d83c9b18                                                         
  id: 3,                                                                             
  first_name: "Arista",                                                              
  last_name: "Ip",                                            
  phone: "234-456-6770",                                      
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d83c9960
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d83c9898
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:17:22.596477000 UTC +00:00>] 
3.0.0 :023 > ip_array = Person.where last_name: "Ip"
  Person Load (24.4ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Ip"]]
 =>                                                                      
[#<Person:0x00007f94d1afa010                                             
...                                                                      
3.0.0 :024 > ip_array
 => 
[#<Person:0x00007f94d1afa010                                             
  id: 1,                                                                 
  first_name: "Zeke",                                                    
  last_name: "Ip",                                                       
  phone: "123-234-4567",                                                 
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,            
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,           
 #<Person:0x00007f94d1af8b20                                             
  id: 3,                                                                 
  first_name: "Arista",                                      
  last_name: "Ip",                                           
  phone: "234-456-6770",                                     
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d1af82d8                                 
  id: 4,                                                     
  first_name: "Zach",                                        
  last_name: "Ip",                                           
  phone: "234-478-6770",                                     
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d1af35a8
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:17:22.596477000 UTC +00:00>] 
3.0.0 :025 > ip_array.map {|object| object.phone= "122-233-3444"}
 => ["122-233-3444", "122-233-3444", "122-233-3444", "122-233-3444"] 
3.0.0 :026 > Person.all
  Person Load (0.7ms)  SELECT "people".* FROM "people"
 =>                                                                                                 
[#<Person:0x00007f94d2ff21e8                                                                        
  id: 1,                                                                                            
  first_name: "Zeke",                                                                               
  last_name: "Ip",                                                                                  
  phone: "123-234-4567",                                                                            
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,                                       
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,                                      
 #<Person:0x00007f94d2ff2120                                                                        
  id: 2,                                                                                            
  first_name: "Bettina",                                                                            
  last_name: "Franz-Ip",                                                                            
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d2ff2058
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "234-456-6770",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d2ff1f90
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "234-478-6770",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d2ff1ec8
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d2ff1e00
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:17:22.596477000 UTC +00:00>] 
3.0.0 :027 > ip_array.save
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation/delegation.rb:110:in `method_missing': undefined method `save' for #<ActiveRecord::Relation [#<Person id: 1, first_name: "Zeke", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:07:31.163759000 +0000", updated_at: "2022-12-05 22:07:31.163759000 +0000">, #<Person id: 3, first_name: "Arista", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:09:26.518545000 +0000", updated_at: "2022-12-05 22:09:26.518545000 +0000">, #<Person id: 4, first_name: "Zach", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:09:50.152642000 +0000", updated_at: "2022-12-05 22:09:50.152642000 +0000">, #<Person id: 6, first_name: "Renita", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:10:58.385300000 +0000", updated_at: "2022-12-05 22:17:22.596477000 +0000">]> (NoMethodError)
3.0.0 :028 > ip_array
 => 
[#<Person:0x00007f94d1afa010                            
  id: 1,                                                
  first_name: "Zeke",                                   
  last_name: "Ip",                                      
  phone: "122-233-3444",                                
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00>,
 #<Person:0x00007f94d1af8b20               
  id: 3,                                   
  first_name: "Arista",                    
  last_name: "Ip",                         
  phone: "122-233-3444",                   
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00>,
 #<Person:0x00007f94d1af82d8
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00>,
 #<Person:0x00007f94d1af35a8
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:17:22.596477000 UTC +00:00>] 
3.0.0 :029 > ip_array.map! {|object| object.phone= "122-233-3444"}
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation/delegation.rb:110:in `method_missing': undefined method `map!' for #<ActiveRecord::Relation [#<Person id: 1, first_name: "Zeke", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:07:31.163759000 +0000", updated_at: "2022-12-05 22:07:31.163759000 +0000">, #<Person id: 3, first_name: "Arista", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:09:26.518545000 +0000", updated_at: "2022-12-05 22:09:26.518545000 +0000">, #<Person id: 4, first_name: "Zach", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:09:50.152642000 +0000", updated_at: "2022-12-05 22:09:50.152642000 +0000">, #<Person id: 6, first_name: "Renita", last_name: "Ip", phone: "122-233-3444", created_at: "2022-12-05 22:10:58.385300000 +0000", updated_at: "2022-12-05 22:17:22.596477000 +0000">]> (NoMethodError)
Did you mean?  map
3.0.0 :030 > ip_array.map {|object| object.update phone: "122-233-3444"}
  TRANSACTION (0.2ms)  BEGIN
  Person Update (0.4ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "122-233-3444"], ["updated_at", "2022-12-05 22:27:54.648887"], ["id", 1]]                    
  TRANSACTION (0.8ms)  COMMIT                                                          
  TRANSACTION (0.2ms)  BEGIN                                                           
  Person Update (0.4ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "122-233-3444"], ["updated_at", "2022-12-05 22:27:54.652826"], ["id", 3]]                    
  TRANSACTION (0.5ms)  COMMIT                                                          
  TRANSACTION (0.2ms)  BEGIN                                                           
  Person Update (0.4ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "122-233-3444"], ["updated_at", "2022-12-05 22:27:54.655748"], ["id", 4]]                    
  TRANSACTION (0.5ms)  COMMIT                                                          
  TRANSACTION (0.3ms)  BEGIN                                                           
  Person Update (0.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "122-233-3444"], ["updated_at", "2022-12-05 22:27:54.659885"], ["id", 6]]                    
  TRANSACTION (0.7ms)  COMMIT
 => [true, true, true, true] 
3.0.0 :031 > Person.all
  Person Load (0.6ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x00007f94d886c788                                  
  id: 2,                                                      
  first_name: "Bettina",                                      
  last_name: "Franz-Ip",                                      
  phone: "234-456-6779",                                      
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,
 #<Person:0x00007f94d886c6c0                                  
  id: 5,                                                      
  first_name: "Tony",                                         
  last_name: "Gidlund",                                       
  phone: "619-478-6770",                                      
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>,
 #<Person:0x00007f94d886c5f8
  id: 1,
  first_name: "Zeke",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.648887000 UTC +00:00>,
 #<Person:0x00007f94d886c530
  id: 3,
  first_name: "Arista",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.652826000 UTC +00:00>,
 #<Person:0x00007f94d886c440
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.655748000 UTC +00:00>,
 #<Person:0x00007f94d886c378
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.659885000 UTC +00:00>] 
3.0.0 :032 > Person.all.select {|object| object.last_name != "Ip"}
  Person Load (13.2ms)  SELECT "people".* FROM "people"
 =>                                                                                                      
[#<Person:0x00007f94d780e5d0                                                                             
  id: 2,                                                                                                 
  first_name: "Bettina",                                                                                 
  last_name: "Franz-Ip",                                                                                 
  phone: "234-456-6779",                                                                                 
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00,                                            
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,                                           
 #<Person:0x00007f94d780e490                                                                             
  id: 5,                                                                                                 
  first_name: "Tony",                                                                                    
  last_name: "Gidlund",                                                                                  
  phone: "619-478-6770",                                                                                 
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,                                            
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>] 
3.0.0 :033 > Person.all.select {|object| object.last_name != "Ip"}.destroy
  Person Load (0.5ms)  SELECT "people".* FROM "people"
(irb):33:in `<main>': undefined method `destroy' for [#<Person id: 2, first_name: "Bettina", last_name: "Franz-Ip", phone: "234-456-6779", created_at: "2022-12-05 22:08:35.171875000 +0000", updated_at: "2022-12-05 22:08:35.171875000 +0000">, #<Person id: 5, first_name: "Tony", last_name: "Gidlund", phone: "619-478-6770", created_at: "2022-12-05 22:10:13.246215000 +0000", updated_at: "2022-12-05 22:10:13.246215000 +0000">]:Array (NoMethodError)            
3.0.0 :034 > Person.all.select {|object| object.last_name != "Ip"}.map {|object| object.destroy}
  Person Load (0.5ms)  SELECT "people".* FROM "people"
  TRANSACTION (0.6ms)  BEGIN                                                                                            
  Person Destroy (1.0ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 2]]                                    
  TRANSACTION (0.9ms)  COMMIT                                                                                           
  TRANSACTION (0.3ms)  BEGIN                                                                                            
  Person Destroy (1.3ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 5]]                                    
  TRANSACTION (0.6ms)  COMMIT                                                                                           
 =>                                                                                                                     
[#<Person:0x00007f94d7cda8c0                                                                                            
  id: 2,                                                                                                                
  first_name: "Bettina",                                                                                                
  last_name: "Franz-Ip",                                                                                                
  phone: "234-456-6779",                                                                                                
  created_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00,                                                           
  updated_at: Mon, 05 Dec 2022 22:08:35.171875000 UTC +00:00>,                                                          
 #<Person:0x00007f94d7cda7f8
  id: 5,
  first_name: "Tony",
  last_name: "Gidlund",
  phone: "619-478-6770",
  created_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:10:13.246215000 UTC +00:00>] 
3.0.0 :035 > Person.all
  Person Load (0.6ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x00007f94d2f62f20                                  
  id: 1,                                                      
  first_name: "Zeke",                                         
  last_name: "Ip",                                            
  phone: "122-233-3444",                                      
  created_at: Mon, 05 Dec 2022 22:07:31.163759000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:27:54.648887000 UTC +00:00>,
 #<Person:0x00007f94d2f62e58                                  
  id: 3,                                                      
  first_name: "Arista",                                       
  last_name: "Ip",                                            
  phone: "122-233-3444",                                      
  created_at: Mon, 05 Dec 2022 22:09:26.518545000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:27:54.652826000 UTC +00:00>,
 #<Person:0x00007f94d2f62d90
  id: 4,
  first_name: "Zach",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:09:50.152642000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.655748000 UTC +00:00>,
 #<Person:0x00007f94d2f62cc8
  id: 6,
  first_name: "Renita",
  last_name: "Ip",
  phone: "122-233-3444",
  created_at: Mon, 05 Dec 2022 22:10:58.385300000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:54.659885000 UTC +00:00>] 
3.0.0 :036 > 
