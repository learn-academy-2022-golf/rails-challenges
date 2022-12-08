Created new Rails App
rails new rolodex_challenge -d postgresql -T
desktop cd rolodex_challenge
➜  rolodex_challenge git:(main) ✗ rails db:create
➜  rolodex_challenge git:(main) ✗ rails s

rails generate model Person first_name:string last_name:string phone:string

rails db:migrate

rails c

Person.create first_name:"Fred", last_name:"Flintstone", phone:"867-5309"

Person.create first_name:"Wilma", last_name:"Flintstone", phone:"867-5308"

Person.create first_name:"Pebbles", last_name:"Flintstone", phone:"867-5307"

Person.create first_name:"BamBam", last_name:"Rubble", phone:"867-6309"

Person.create first_name:"Barney", last_name:"Rubble", phone:"867-7309"

Person.create first_name:"Betty", last_name:"Rubble", phone:"867-8309"

Person.all

Person.where last_name:"Rubble"

new = Person.find 6
new.update phone:"000-0000"

Person.find 6

new = Person.find 3 
new.first_name

Person.where last_name:"Rubble"
new = Person.where last_name:"Rubble"

new.update phone:"000-0000"

**below 3 lines of code did not work to remove "Rubble" family members
**Person.where last_name:"Rubble" == false
**new = Person.where last_name:"Rubble" == false
**new.all

new = Person.where "last_name != 'Rubble'"
new.all

new.destroy_all
Person.all

3.0.0 :040 > Person.all
  Person Load (0.8ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000011a1e9018                                  
  id: 6,                                                      
  first_name: "Betty",                                        
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>,
 #<Person:0x000000011a1e8f00                                  
  id: 4,                                                      
  first_name: "BamBam",                                       
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000011a1e8de8
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>] 
3.0.0 :041 > 
************************************************************************
************************************************************************
********Below is everything we did in the terminal**********************
************************************************************************
************************************************************************
➜  rolodex_challenge git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Person.create first_name:"Fred", last_name:"Flintstone", phone:"867-5309
"
  TRANSACTION (0.1ms)  BEGIN
  Person Create (3.8ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Fred"], ["last_name", "Flintstone"], ["phone", "867-5309"], ["created_at", "2022-12-05 22:27:33.176082"], ["updated_at", "2022-12-05 22:27:33.176082"]]
  TRANSACTION (1.3ms)  COMMIT
 => 
#<Person:0x000000011a10bf60
 id: 1,
 first_name: "Fred",
 last_name: "Flintstone",
 phone: "867-5309",
 created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00> 
3.0.0 :002 > Person.create first_name:"Wilma", last_name:"Flintstone", phone:"867-530
8"
  TRANSACTION (0.5ms)  BEGIN
  Person Create (1.0ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Wilma"], ["last_name", "Flintstone"], ["phone", "867-5308"], ["created_at", "2022-12-05 22:28:17.983773"], ["updated_at", "2022-12-05 22:28:17.983773"]]
  TRANSACTION (0.4ms)  COMMIT
 => 
#<Person:0x000000011a3496b0
 id: 2,
 first_name: "Wilma",
 last_name: "Flintstone",
 phone: "867-5308",
 created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00> 
3.0.0 :003 > Person.create first_name:"Pebbles", last_name:"Flintstone", phone:"867-5
307"
  TRANSACTION (0.5ms)  BEGIN
  Person Create (0.8ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Pebbles"], ["last_name", "Flintstone"], ["phone", "867-5307"], ["created_at", "2022-12-05 22:29:07.432597"], ["updated_at", "2022-12-05 22:29:07.432597"]]              
  TRANSACTION (0.9ms)  COMMIT                                                        
 =>                                                                                  
#<Person:0x000000011a0d2440                                                          
 id: 3,                                                                              
 first_name: "Pebbles",                                                              
 last_name: "Flintstone",                                                            
 phone: "867-5307",                                                                  
 created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,                         
 updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>                         
3.0.0 :004 > Person.create first_name:"BamBam", last_name:"Rubble", phone:"867-6309"
  TRANSACTION (0.6ms)  BEGIN
  Person Create (0.8ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "BamBam"], ["last_name", "Rubble"], ["phone", "867-6309"], ["created_at", "2022-12-05 22:29:20.453669"], ["updated_at", "2022-12-05 22:29:20.453669"]]
  TRANSACTION (0.3ms)  COMMIT
 => 
#<Person:0x000000013ef61f00
 id: 4,
 first_name: "BamBam",
 last_name: "Rubble",
 phone: "867-6309",
 created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00> 
3.0.0 :005 > Person.create first_name:"Barney", last_name:"Rubble", phone:"867-7309"
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.4ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Barney"], ["last_name", "Rubble"], ["phone", "867-7309"], ["created_at", "2022-12-05 22:29:28.655967"], ["updated_at", "2022-12-05 22:29:28.655967"]]
  TRANSACTION (0.6ms)  COMMIT
 => 
#<Person:0x000000013f0caec8
 id: 5,
 first_name: "Barney",
 last_name: "Rubble",
 phone: "867-7309",
 created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00> 
3.0.0 :006 > Person.create first_name:"Betty", last_name:"Rubble", phone:"867-8309"
  TRANSACTION (11.7ms)  BEGIN
  Person Create (1.4ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Betty"], ["last_name", "Rubble"], ["phone", "867-8309"], ["created_at", "2022-12-05 22:29:36.798899"], ["updated_at", "2022-12-05 22:29:36.798899"]]
  TRANSACTION (0.4ms)  COMMIT
 => 
#<Person:0x000000013f2d9d18
 id: 6,
 first_name: "Betty",
 last_name: "Rubble",
 phone: "867-8309",
 created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00> 
3.0.0 :007 > Person.all
  Person Load (1.5ms)  SELECT "people".* FROM "people"
 =>                                                  
[#<Person:0x000000011a51b7b8                         
  id: 1,
  first_name: "Fred",
  last_name: "Flintstone",
  phone: "867-5309",
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000011a51b678
  id: 2,
  first_name: "Wilma",
  last_name: "Flintstone",
  phone: "867-5308",
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000011a51b5b0
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>,
 #<Person:0x000000011a51b4e8
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "867-6309",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00>,
 #<Person:0x000000011a51b420
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "867-7309",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00>,
 #<Person:0x000000011a51b358
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "867-8309",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00>] 
3.0.0 :008 > Person.where last_name:"Rubble"
  Person Load (0.5ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Rubble"]]
 => 
[#<Person:0x000000011a799120
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "867-6309",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00>,
 #<Person:0x000000011a799058
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "867-7309",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00>,
 #<Person:0x000000011a798f90
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "867-8309",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00>] 
3.0.0 :009 > new = Person.find 6
  Person Load (0.6ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 6], ["LIMIT", 1]]
 => 
#<Person:0x000000011e8b81d8
... 
3.0.0 :010"> new.update phone:"000-0000
3.0.0 :011"> new.update phone:"000-0000"
3.0.0 :012"> Person.find 6
3.0.0 :013"> Person.all
3.0.0 :014"> "
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/irb-1.5.1/lib/irb/workspace.rb:119:in `eval': (irb):11: syntax error, unexpected integer literal, expecting end-of-input (SyntaxError)                                                    
new.update phone:"000-0000"                                   
                  ^~~                                         
3.0.0 :015 > Person.all
  Person Load (1.0ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000011a698668                                  
  id: 1,                                                      
  first_name: "Fred",                                         
  last_name: "Flintstone",                                    
  phone: "867-5309",                                          
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000011a6985a0                                  
  id: 2,                                                      
  first_name: "Wilma",                                        
  last_name: "Flintstone",                                    
  phone: "867-5308",                                          
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000011a6984d8
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>,
 #<Person:0x000000011a698410
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "867-6309",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00>,
 #<Person:0x000000011a698348
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "867-7309",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00>,
 #<Person:0x000000011a698280
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "867-8309",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00>] 
3.0.0 :016 > new = Person.find 6
  Person Load (1.2ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 6], ["LIMIT", 1]]
 => 
#<Person:0x000000011e99a0d8
... 
3.0.0 :017 > new.update phone:"000-0000"
  TRANSACTION (0.5ms)  BEGIN
  Person Update (3.0ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "000-0000"], ["updated_at", "2022-12-05 22:36:53.200976"], ["id", 6]]
  TRANSACTION (0.7ms)  COMMIT
 => true 
3.0.0 :018 > Person.find 6
  Person Load (18.1ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 6], ["LIMIT", 1]]
 => 
#<Person:0x000000010fcc9380
 id: 6,
 first_name: "Betty",
 last_name: "Rubble",
 phone: "000-0000",
 created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00> 
3.0.0 :019 > Person.find 3 first_name
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/irb-1.5.1/lib/irb/workspace.rb:119:in `eval': (irb):19: syntax error, unexpected local variable or method, expecting end-of-input (SyntaxError)
Person.find 3 first_name
              ^~~~~~~~~~
3.0.0 :020 > new = Person.find 3 
  Person Load (1.3ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 => 
#<Person:0x000000011a1aaca0
... 
3.0.0 :021 > new.first_name
 => "Pebbles" 
3.0.0 :022 > Person.where last_name:"Rubble"
  Person Load (1.0ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Rubble"]]                    
 =>                                             
[#<Person:0x000000011a3934e0                    
  id: 4,                                        
  first_name: "BamBam",                         
  last_name: "Rubble",                          
  phone: "867-6309",                            
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00>,
 #<Person:0x000000011a393418                    
  id: 5,                                        
  first_name: "Barney",                         
  last_name: "Rubble",
  phone: "867-7309",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00>,
 #<Person:0x000000011a393350
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>] 
3.0.0 :023 > new = Person.where last_name:"Rubble"
  Person Load (1.0ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Rubble"]]
 => 
[#<Person:0x000000013f1db970
... 
3.0.0 :024 > new.update phone:"000-0000"
  TRANSACTION (0.6ms)  BEGIN
  Person Update (0.8ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "000-0000"], ["updated_at", "2022-12-05 22:44:10.521409"], ["id", 4]]
  TRANSACTION (0.7ms)  COMMIT
  TRANSACTION (0.1ms)  BEGIN
  Person Update (0.4ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "000-0000"], ["updated_at", "2022-12-05 22:44:10.529025"], ["id", 5]]
  TRANSACTION (0.2ms)  COMMIT
 => 
[#<Person:0x000000013f1db970
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000013f1db8a8
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>,
 #<Person:0x000000013f1db7e0
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>] 
3.0.0 :025 > Person.where last_name:"Rubble" == false
  Person Load (19.2ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "f"]]
 => [] 
3.0.0 :026 > new = Person.where last_name:"Rubble" == false
  Person Load (1.3ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "f"]]
 => [] 
3.0.0 :027 > new.all
  Person Load (1.2ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "f"]]
 => [] 
3.0.0 :028 > Person.all
  Person Load (1.0ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000013f12b408                                  
  id: 1,                                                      
  first_name: "Fred",                                         
  last_name: "Flintstone",                                    
  phone: "867-5309",                                          
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000013f12b340                                  
  id: 2,                                                      
  first_name: "Wilma",                                        
  last_name: "Flintstone",                                    
  phone: "867-5308",                                          
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000013f12b278
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>,
 #<Person:0x000000013f12b1b0
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>,
 #<Person:0x000000013f12b0e8
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000013f12b020
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>] 
3.0.0 :029 > new = Person.where last_name != "Rubble"
(irb):29:in `<main>': undefined local variable or method `last_name' for main:Object (NameError)
3.0.0 :030 > new = Person.where last_name: != "Rubble"
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/irb-1.5.1/lib/irb/workspace.rb:119:in `eval': (irb):30: syntax error, unexpected != (SyntaxError)
...ew = Person.where last_name: != "Rubble"
...                             ^~
3.0.0 :031 > new = Person.where "last_name != 'Rubble'"
  Person Load (16.1ms)  SELECT "people".* FROM "people" WHERE (last_name != 'Rubble')
 => 
[#<Person:0x000000011a78bcc8
... 
3.0.0 :032 > new.all
  Person Load (0.5ms)  SELECT "people".* FROM "people" WHERE (last_name != 'Rubble')
 =>                                                
[#<Person:0x000000010feb7818                       
  id: 1,                                           
  first_name: "Fred",                              
  last_name: "Flintstone",                         
  phone: "867-5309",                               
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000010feb7750                       
  id: 2,                                           
  first_name: "Wilma",                             
  last_name: "Flintstone",                         
  phone: "867-5308",                               
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000010feb7688
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>] 
3.0.0 :033 > new.delete
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:473:in `delete': wrong number of arguments (given 0, expected 1) (ArgumentError)
3.0.0 :034 > Person.all
  Person Load (0.9ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000011a4baa30                                  
  id: 1,                                                      
  first_name: "Fred",                                         
  last_name: "Flintstone",                                    
  phone: "867-5309",                                          
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000011a4ba968                                  
  id: 2,                                                      
  first_name: "Wilma",                                        
  last_name: "Flintstone",                                    
  phone: "867-5308",                                          
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000011a4ba8a0
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>,
 #<Person:0x000000011a4ba7d8
  id: 6,
  first_name: "Betty",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>,
 #<Person:0x000000011a4ba710
  id: 4,
  first_name: "BamBam",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000011a4ba648
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>] 
3.0.0 :035 > new.delete.all
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:473:in `delete': wrong number of arguments (given 0, expected 1) (ArgumentError)                                                    
3.0.0 :036 > new.delete all
(irb):36:in `<main>': undefined local variable or method `all' for main:Object (NameError)                                                       
3.0.0 :037 > new.destroy
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:447:in `destroy': wrong number of arguments (given 0, expected 1) (ArgumentError)                                                   
3.0.0 :038 > new.destroy_all
  TRANSACTION (0.7ms)  BEGIN
  Person Destroy (0.6ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 1]]
  TRANSACTION (0.5ms)  COMMIT                               
  TRANSACTION (0.1ms)  BEGIN                                
  Person Destroy (1.1ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 2]]
  TRANSACTION (0.3ms)  COMMIT                               
  TRANSACTION (0.1ms)  BEGIN                                
  Person Destroy (0.3ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 3]]
  TRANSACTION (0.2ms)  COMMIT                      
 =>                                                
[#<Person:0x000000011a78bcc8                       
  id: 1,                                           
  first_name: "Fred",                              
  last_name: "Flintstone",                         
  phone: "867-5309",                               
  created_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:27:33.176082000 UTC +00:00>,
 #<Person:0x000000011a78bc00
  id: 2,
  first_name: "Wilma",
  last_name: "Flintstone",
  phone: "867-5308",
  created_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:28:17.983773000 UTC +00:00>,
 #<Person:0x000000011a78bb38
  id: 3,
  first_name: "Pebbles",
  last_name: "Flintstone",
  phone: "867-5307",
  created_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:29:07.432597000 UTC +00:00>] 
3.0.0 :039 > Person.all
  Person Load (1.1ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000013f2eabe0                                  
  id: 6,                                                      
  first_name: "Betty",                                        
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>,
 #<Person:0x000000013f2eab18                                  
  id: 4,                                                      
  first_name: "BamBam",                                       
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000013f2eaa50
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>] 
3.0.0 :040 > Person.all
  Person Load (0.8ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000011a1e9018                                  
  id: 6,                                                      
  first_name: "Betty",                                        
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:36.798899000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:36:53.200976000 UTC +00:00>,
 #<Person:0x000000011a1e8f00                                  
  id: 4,                                                      
  first_name: "BamBam",                                       
  last_name: "Rubble",                                        
  phone: "000-0000",                                          
  created_at: Mon, 05 Dec 2022 22:29:20.453669000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:44:10.521409000 UTC +00:00>,
 #<Person:0x000000011a1e8de8
  id: 5,
  first_name: "Barney",
  last_name: "Rubble",
  phone: "000-0000",
  created_at: Mon, 05 Dec 2022 22:29:28.655967000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:44:10.529025000 UTC +00:00>] 
3.0.0 :041 > exit
             exit           
             exit!          
