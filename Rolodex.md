- Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
    $ rails new rolodex_bella_mike  -d postgresql -T
    $ rails db:create
    $ rails s
    $ rails generate model Person first_name:string last_name:string phone:string

- Run a migration to set up the database.
    $ rails db:migrate 

- Open up Rails console.
    $ rails c
3.0.0 :002 > Person
 => Person(id: integer, first_name: string, last_name: string, phone: string, created_at: datetime, updated_at: datetime) 

Actions

- Add five family members into the Person table in the Rails console.
    - Person.create first_name:"Jack", last_name:"Smith", phone:"619-555-1234"
    - Person.create first_name:"Chase", last_name:"Chan", phone:"510-123-4567"
    - Person.create first_name:"Kaya", last_name:"Farrington", phone:"415-305-7890"
    - Person.create first_name:"Bob", last_name:"Jones", phone:"123-456-7890"
    - Person.create first_name:"Amy", last_name:"Doe", phone:"526-675-4456"

- Retrieve all the items in the database.
    3.0.0 :008 > Person.all
  Person Load (0.6ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x0000000115ea7110                                  
  id: 1,                                                      
  first_name: "Jack",                                         
  last_name: "Smith",                                         
  phone: "619-555-1234",                                      
  created_at: Mon, 05 Dec 2022 22:30:21.116861000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:30:21.116861000 UTC +00:00>,
 #<Person:0x0000000115ea6fd0                                  
  id: 2,                                                      
  first_name: "Chase",                                        
  last_name: "Chan",                                          
  phone: "510-123-4567",                                      
  created_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00>,
 #<Person:0x0000000115ea6f08
  id: 3,
  first_name: "Kaya",
  last_name: "Farrington",
  phone: "415-305-7890",
  created_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00>,
 #<Person:0x0000000115ea6e40
  id: 4,
  first_name: "Bob",
  last_name: "Jones",
  phone: "123-456-7890",
  created_at: Mon, 05 Dec 2022 22:32:22.241739000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:32:22.241739000 UTC +00:00>,
 #<Person:0x0000000115ea6d78
  id: 5,
  first_name: "Amy",
  last_name: "Doe",
  phone: "526-675-4456",
  created_at: Mon, 05 Dec 2022 22:33:09.943450000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:33:09.943450000 UTC +00:00>] 

- Add yourself to the Person table.
    - 3.0.0 :009 > Person.create first_name:"Bella", last_name:"Chan", phone:"510-098-7654"
    
Retrieve all the entries that have the same last_name as you.
    - 3.0.0 :003 > Person.where last_name:"Chan"
    Person Load (0.4ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Chan"]]                                             
    =>                                                           
    [#<Person:0x00000001361eeb50                                  
    id: 2,                                                      
    first_name: "Chase",                                        
    last_name: "Chan",                                          
    phone: "510-123-4567",                                      
    created_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00, 
    updated_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00>,
    #<Person:0x00000001361eea88                                  
    id: 6,                                                      
    first_name: "Bella",                                        
    last_name: "Chan",                                          
    phone: "510-098-7654",                                      
    created_at: Mon, 05 Dec 2022 22:37:06.112125000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:37:06.112125000 UTC +00:00>] 

Update the phone number of the last entry in the database.
    - 3.0.0 :005 > Bella.update phone:"510-261-0819"
    TRANSACTION (0.2ms)  BEGIN
    Person Update (6.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "510-261-0819"], ["updated_at", "2022-12-05 23:35:36.931628"], ["id", 6]]
    TRANSACTION (1.5ms)  COMMIT                                         
    => true 

Retrieve the first_name of the third Person in the database.
    - 3.0.0 :010 > Person.third
    Person Load (0.3ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" ASC LIMIT $1 OFFSET $2  [["LIMIT", 1], ["OFFSET", 2]]                         
    =>                                                           
    #<Person:0x000000013617d090                                   
    id: 3,                                                       
    first_name: "Kaya",                                          
    last_name: "Farrington",                                     
    phone: "415-305-7890",                                       
    created_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00,  
    updated_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00> 

Stretch Challenges

- Update all the family members with the same last_name as you, to have the same phone number as you.
    - 3.0.0 :020 > Person.where last_name:"Chan"
  Person Load (0.5ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Chan"]]                                                      
 =>                                                                    
[#<Person:0x0000000124d55780                                           
  id: 2,                                                               
  first_name: "Chase",                                                 
  last_name: "Chan",                                                   
  phone: "510-123-4567",                                               
  created_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00>,
 #<Person:0x0000000124d556b8                                  
  id: 6,                                                      
  first_name: "Bella",                                        
  last_name: "Chan",                                          
  phone: "510-261-0819",                                      
  created_at: Mon, 05 Dec 2022 22:37:06.112125000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 23:35:36.931628000 UTC +00:00>] 
3.0.0 :021 > new_pn = Person.where last_name:"Chan"
  Person Load (0.4ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Chan"]]                                                      
 =>                                                                    
[#<Person:0x00000001370b5fd0                                           
...                                                                    
3.0.0 :022 > new_pn.update phone:"333-3333"
  TRANSACTION (0.3ms)  BEGIN
  Person Update (0.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "333-3333"], ["updated_at", "2022-12-05 23:58:53.208976"], ["id", 2]]
  TRANSACTION (5.1ms)  COMMIT                                          
  TRANSACTION (0.2ms)  BEGIN                                           
  Person Update (0.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "333-3333"], ["updated_at", "2022-12-05 23:58:53.217888"], ["id", 6]]
  TRANSACTION (0.3ms)  COMMIT                                          
 =>                                                                    
[#<Person:0x00000001370b5fd0                               
  id: 2,                                                   
  first_name: "Chase",                                     
  last_name: "Chan",                                       
  phone: "333-3333",                                       
  created_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 23:58:53.208976000 UTC +00:00>,
 #<Person:0x00000001370b5f08
  id: 6,
  first_name: "Bella",
  last_name: "Chan",
  phone: "333-3333",
  created_at: Mon, 05 Dec 2022 22:37:06.112125000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 23:58:53.217888000 UTC +00:00>]

- Remove all family members that do not have your last_name.
        - 3.0.0 :030 > not_chan = Person.where "last_name!='Chan'"
    Person Load (1.3ms)  SELECT "people".* FROM "people" WHERE (last_name!='Chan')
    =>                                                                                           
    [#<Person:0x0000000124c2c408                                                                  
    ...                                                                                           
    3.0.0 :031 > not_chan.destroy_all
    TRANSACTION (0.2ms)  BEGIN
    Person Destroy (0.3ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 1]]          
    TRANSACTION (5.2ms)  COMMIT                                                                 
    TRANSACTION (0.1ms)  BEGIN                                                                  
    Person Destroy (0.3ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 3]]          
    TRANSACTION (0.2ms)  COMMIT                                                                 
    TRANSACTION (0.1ms)  BEGIN                            
    Person Destroy (0.2ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 4]]
    TRANSACTION (0.2ms)  COMMIT                           
    TRANSACTION (0.1ms)  BEGIN                            
    Person Destroy (0.2ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 5]]
    TRANSACTION (0.2ms)  COMMIT                           
    =>                                                     
    [#<Person:0x0000000124c2c408                            
    id: 1,                                                
    first_name: "Jack",
    last_name: "Smith",
    phone: "619-555-1234",
    created_at: Mon, 05 Dec 2022 22:30:21.116861000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:30:21.116861000 UTC +00:00>,
    #<Person:0x0000000124c2c340
    id: 3,
    first_name: "Kaya",
    last_name: "Farrington",
    phone: "415-305-7890",
    created_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:31:38.086150000 UTC +00:00>,
    #<Person:0x0000000124c2c278
    id: 4,
    first_name: "Bob",
    last_name: "Jones",
    phone: "123-456-7890",
    created_at: Mon, 05 Dec 2022 22:32:22.241739000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:32:22.241739000 UTC +00:00>,
    #<Person:0x0000000124c2c1b0
    id: 5,
    first_name: "Amy",
    last_name: "Doe",
    phone: "526-675-4456",
    created_at: Mon, 05 Dec 2022 22:33:09.943450000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:33:09.943450000 UTC +00:00>] 
    3.0.0 :032 > Person.all
    Person Load (0.5ms)  SELECT "people".* FROM "people"
    =>                                                           
    [#<Person:0x000000013695ede0                                  
    id: 2,                                                      
    first_name: "Chase",                                        
    last_name: "Chan",                                          
    phone: "333-3333",                                          
    created_at: Mon, 05 Dec 2022 22:31:04.831135000 UTC +00:00, 
    updated_at: Mon, 05 Dec 2022 23:58:53.208976000 UTC +00:00>,
    #<Person:0x000000013695ed18                                  
    id: 6,                                                      
    first_name: "Bella",                                        
    last_name: "Chan",                                          
    phone: "333-3333",                                          
    created_at: Mon, 05 Dec 2022 22:37:06.112125000 UTC +00:00, 
    updated_at: Mon, 05 Dec 2022 23:58:53.217888000 UTC +00:00>] 