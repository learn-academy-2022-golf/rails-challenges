learnacademy@LEARNs-MacBook-Air rolodex_app % rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Person.create first_name:"Shannon", last_name:"Young", phone:"470-560-8639"
  TRANSACTION (8.4ms)  BEGIN
  Person Create (5.5ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Shannon"], ["last_name", "Young"], ["phone", "470-560-8639"], ["created_at", "2022-12-06 00:06:55.344248"], ["updated_at", "2022-12-06 00:06:55.344248"]]                         
  TRANSACTION (4.1ms)  COMMIT                                                                       
 =>                                                                                                 
#<Person:0x00007fa2b71b5330                                                                         
 id: 1,                                                                                             
 first_name: "Shannon",                                                                             
 last_name: "Young",                                                                                
 phone: "470-560-8639",                                                                             
 created_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00,                                        
 updated_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00>                                        
3.0.0 :002 > Person.create first_name"Vita", last_name:"Carter", phone:"404-630-0613"
(irb):2:in `<main>': undefined method `first_name' for main:Object (NoMethodError)
3.0.0 :003 > Person.create first_name:"Vita", last_name:"Carter", phone:"404-630-0613"
  TRANSACTION (0.3ms)  BEGIN
  Person Create (0.6ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Vita"], ["last_name", "Carter"], ["phone", "404-630-0613"], ["created_at", "2022-12-06 00:08:33.393259"], ["updated_at", "2022-12-06 00:08:33.393259"]]                         
  TRANSACTION (1.0ms)  COMMIT                                                                     
 =>                                                                                               
#<Person:0x00007fa2b78a1db0                                                                       
 id: 2,                                                                                           
 first_name: "Vita",                                                                              
 last_name: "Carter",                                                                             
 phone: "404-630-0613",                                                                           
 created_at: Tue, 06 Dec 2022 00:08:33.393259000 UTC +00:00,                                      
 updated_at: Tue, 06 Dec 2022 00:08:33.393259000 UTC +00:00>                                      
3.0.0 :004 > Person.create first_name:"Zora", last_name:"Jackson", phone:"404-566-0989"
  TRANSACTION (0.4ms)  BEGIN
  Person Create (0.8ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Zora"], ["last_name", "Jackson"], ["phone", "404-566-0989"], ["created_at", "2022-12-06 00:09:09.209675"], ["updated_at", "2022-12-06 00:09:09.209675"]]                         
  TRANSACTION (1.1ms)  COMMIT                                                                      
 =>                                                                                                
#<Person:0x00007fa2b1f79418                                                                        
 id: 3,                                                                                            
 first_name: "Zora",                                                                               
 last_name: "Jackson",                                                                             
 phone: "404-566-0989",                                                                            
 created_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00,                                       
 updated_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00>                                       
3.0.0 :005 > Person.create first_name:"Giavanna", last_name:"Clark", phone:"470-456-0984"
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.5ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Giavanna"], ["last_name", "Clark"], ["phone", "470-456-0984"], ["created_at", "2022-12-06 00:09:46.937939"], ["updated_at", "2022-12-06 00:09:46.937939"]]                         
  TRANSACTION (1.2ms)  COMMIT                                                                        
 =>                                                                                                  
#<Person:0x00007fa2b2ad6ce8                                                                          
 id: 4,                                                                                              
 first_name: "Giavanna",                                                                             
 last_name: "Clark",                                                                                 
 phone: "470-456-0984",                                                                              
 created_at: Tue, 06 Dec 2022 00:09:46.937939000 UTC +00:00,                                         
 updated_at: Tue, 06 Dec 2022 00:09:46.937939000 UTC +00:00>                                         
3.0.0 :006 > Person.create first_name:"Jason", last_name:"Young", phone:"404-989-0999"
  TRANSACTION (0.3ms)  BEGIN
  Person Create (0.6ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Jason"], ["last_name", "Young"], ["phone", "404-989-0999"], ["created_at", "2022-12-06 00:10:32.160780"], ["updated_at", "2022-12-06 00:10:32.160780"]]                         
  TRANSACTION (3.2ms)  COMMIT                                                                     
 =>                                                                                               
#<Person:0x00007fa2b1c7a0a0                                                                       
 id: 5,                                                                                           
 first_name: "Jason",                                                                             
 last_name: "Young",                                                                              
 phone: "404-989-0999",                                                                           
 created_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00,                                      
 updated_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00>                                      
3.0.0 :007 > Person.all
  Person Load (6.0ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x00007fa2b73eea70                                  
  id: 1,                                                      
  first_name: "Shannon",                                      
  last_name: "Young",                                         
  phone: "470-560-8639",                                      
  created_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00, 
  updated_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00>,
 #<Person:0x00007fa2b73ee930                                  
  id: 2,                                                      
  first_name: "Vita",                                         
  last_name: "Carter",                                        
  phone: "404-630-0613",                                      
  created_at: Tue, 06 Dec 2022 00:08:33.393259000 UTC +00:00, 
  updated_at: Tue, 06 Dec 2022 00:08:33.393259000 UTC +00:00>,
 #<Person:0x00007fa2b73ee868
  id: 3,
  first_name: "Zora",
  last_name: "Jackson",
  phone: "404-566-0989",
  created_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00>,
 #<Person:0x00007fa2b73ee7a0
  id: 4,
  first_name: "Giavanna",
  last_name: "Clark",
  phone: "470-456-0984",
  created_at: Tue, 06 Dec 2022 00:09:46.937939000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 00:09:46.937939000 UTC +00:00>,
 #<Person:0x00007fa2b73ee6d8
  id: 5,
  first_name: "Jason",
  last_name: "Young",
  phone: "404-989-0999",
  created_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00>] 
3.0.0 :008 > Person.include? "Young"
(irb):8:in `include?': wrong argument type String (expected Module) (TypeError)
3.0.0 :009 > Person.includes? last_name:"Young"
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `includes?' for Person:Class (NoMethodError)
Did you mean?  include?                                       
               includes                                       
               include                                        
3.0.0 :010 > Person.find "Young"
  Person Load (0.7ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", nil], ["LIMIT", 1]]
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/core.rb:284:in `find': Couldn't find Person with 'id'=Young (ActiveRecord::RecordNotFound)              
3.0.0 :011 > Person.find Young
(irb):11:in `<main>': uninitialized constant Young (NameError)
3.0.0 :012 > Person.find last_name:"Young"
  Person Load (0.5ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", nil], ["LIMIT", 1]]
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation/finder_methods.rb:381:in `raise_record_not_found_exception!': Couldn't find Person with 'id'={:last_name=>"Young"} (ActiveRecord::RecordNotFound)
3.0.0 :013 > Person.where last_name:"Young"
  Person Load (1.0ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Young"]]
 =>                                                           
[#<Person:0x00007fa2b720dc60                                  
  id: 1,                                                      
  first_name: "Shannon",                                      
  last_name: "Young",                                         
  phone: "470-560-8639",                                      
  created_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00, 
  updated_at: Tue, 06 Dec 2022 00:06:55.344248000 UTC +00:00>,
 #<Person:0x00007fa2b720dad0                                  
  id: 5,                                                      
  first_name: "Jason",                                        
  last_name: "Young",                                         
  phone: "404-989-0999",                                      
  created_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00, 
  updated_at: Tue, 06 Dec 2022 00:10:32.160780000 UTC +00:00>] 
3.0.0 :014 > number = "770-656-0923"
 => "770-656-0923" 
3.0.0 :015 > Person.3
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/irb-1.5.1/lib/irb/workspace.rb:119:in `eval': (irb):15: no .<digit> floating literal anymore; put 0 before dot (SyntaxError)                 
Person.3                                                      
      ^~                                                      
3.0.0 :016 > Person.find 3
  Person Load (1.5ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 =>                                                           
#<Person:0x00007fa2b81665b8                                   
 id: 3,                                                       
 first_name: "Zora",                                          
 last_name: "Jackson",                                        
 phone: "404-566-0989",                                       
 created_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00,  
 updated_at: Tue, 06 Dec 2022 00:09:09.209675000 UTC +00:00>  
3.0.0 :017 > Jackson.each{|value|value.destroy}
(irb):17:in `<main>': uninitialized constant Jackson (NameError)
3.0.0 :018 > Jackson = person.where last_name(Jackson)
(irb):18:in `<main>': undefined local variable or method `person' for main:Object (NameError)
3.0.0 :019 > 