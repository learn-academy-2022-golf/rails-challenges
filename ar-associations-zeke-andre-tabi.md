----------- SETUP ------------------
== 20221206230020 CreateOwners: migrating =====================================
-- create_table(:owners)
   -> 0.0424s
== 20221206230020 CreateOwners: migrated (0.0425s) ============================

== 20221206230346 CreateCreditCards: migrating ================================
-- create_table(:credit_cards)
   -> 0.0119s
== 20221206230346 CreateCreditCards: migrated (0.0120s) ======================

----------------- Challenges --------------------
1. Create three owners and save them in a database.
3.0.0 :015 > Owner.create name:"Phillip", address: "123 Bay Area", credit_card: 136474938
  TRANSACTION (17.1ms)  BEGIN
  Owner Create (7.8ms)  INSERT INTO "owners" ("name", "address", "credit_card", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["name", "Phillip"], ["address", "123 Bay Area"], ["credit_card", 136474938], ["created_at", "2022-12-06 23:25:55.557422"], ["updated_at", "2022-12-06 23:25:55.557422"]]
  TRANSACTION (5.6ms)  COMMIT                                                       
 =>                                                                                 
#<Owner:0x00007fdacd45b230                                                          
 id: 1,                                                                             
 name: "Phillip",                                                                   
 address: "123 Bay Area",                                                           
 credit_card: 136474938,
 created_at: Tue, 06 Dec 2022 23:25:55.557422000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 23:25:55.557422000 UTC +00:00> 
3.0.0 :016 > Owner.create name:"Derreck", address: "456 Not Bay Area", credit_card:907306735569
  TRANSACTION (5.9ms)  BEGIN
  Owner Create (0.7ms)  INSERT INTO "owners" ("name", "address", "credit_card", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["name", "Derreck"], ["address", "456 Not Bay Area"], ["credit_card", 907306735569], ["created_at", "2022-12-06 23:27:09.816412"], ["updated_at", "2022-12-06 23:27:09.816412"]]
  TRANSACTION (1.4ms)  COMMIT                                                         
 =>                                                                                   
#<Owner:0x00007fdacd481098                                                            
 id: 2,                                                                               
 name: "Derreck",                                                                     
 address: "456 Not Bay Area",                                                         
 credit_card: 907306735569,                                                           
 created_at: Tue, 06 Dec 2022 23:27:09.816412000 UTC +00:00,                          
 updated_at: Tue, 06 Dec 2022 23:27:09.816412000 UTC +00:00>                          
3.0.0 :017 > Owner.create name:"Niki", address: "789 Not the West Coasa", credit_card:83547359624
  TRANSACTION (18.8ms)  BEGIN
  Owner Create (0.9ms)  INSERT INTO "owners" ("name", "address", "credit_card", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["name", "Niki"], ["address", "789 Not the West Coasa"], ["credit_card", 83547359624], ["created_at", "2022-12-06 23:28:07.151568"], ["updated_at", "2022-12-06 23:28:07.151568"]]
  TRANSACTION (4.1ms)  COMMIT                                                      
 =>                                                                                
#<Owner:0x00007fdacf08ef88                                                         
 id: 3,                                                                            
 name: "Niki",                                                                     
 address: "789 Not the West Coasa",                                                
 credit_card: 83547359624,                                                         
 created_at: Tue, 06 Dec 2022 23:28:07.151568000 UTC +00:00,                       
 updated_at: Tue, 06 Dec 2022 23:28:07.151568000 UTC +00:00>                       
3.0.0 :018 > 
                  
2. Create a credit card in the database for each owner.
<Owner:0x00007fdacfb6f538                                                                                               
 id: 1,                                                                                                                  
 name: "Phillip",                                                                                                        
 address: "123 Bay Area",                                                                                                
 credit_card: 136474938,                                                                                                 
 created_at: Tue, 06 Dec 2022 23:25:55.557422000 UTC +00:00,                                                             
 updated_at: Tue, 06 Dec 2022 23:25:55.557422000 UTC +00:00>                                                             
3.0.0 :028 > phillip.credit_cards.create number:2497577628576543, expiration_date: Date.today  
  TRANSACTION (11.2ms)  BEGIN
  CreditCard Create (1.0ms)  INSERT INTO "credit_cards" ("number", "expiration_date", "owner_id", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["number", 2497577628576543], ["expiration_date", "2022-12-06"], ["owner_id", 1], ["created_at", "2022-12-06 23:43:35.492041"], ["updated_at", "2022-12-06 23:43:35.492041"]]
  TRANSACTION (1.7ms)  COMMIT                   
 =>                                             
#<CreditCard:0x00007fdacd5ba108              
 id: 2,
 number: 2497577628576543,
 expiration_date: Tue, 06 Dec 2022,
 owner_id: 1,
 created_at: Tue, 06 Dec 2022 23:43:35.492041000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 23:43:35.492041000 UTC +00:00> 
3.0.0 :029 > derreck = Owner.find 2
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
 =>                                                                    
#<Owner:0x00007fdacd5d1d30                                             
...                                                                    
3.0.0 :030 > derreck
 => 
#<Owner:0x00007fdacd5d1d30                                             
 id: 2,                                                                
 name: "Derreck",                                                      
 address: "456 Not Bay Area",                                          
 credit_card: 907306735569,                                            
 created_at: Tue, 06 Dec 2022 23:27:09.816412000 UTC +00:00,           
 updated_at: Tue, 06 Dec 2022 23:27:09.816412000 UTC +00:00>           
3.0.0 :031 > derreck.credit_cards.create number:420860372648883, expiration_date: Date.tomorrow  
  TRANSACTION (1.7ms)  BEGIN
  CreditCard Create (0.8ms)  INSERT INTO "credit_cards" ("number", "expiration_date", "owner_id", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["number", 420860372648883], ["expiration_date", "2022-12-07"], ["owner_id", 2], ["created_at", "2022-12-06 23:45:12.503095"], ["updated_at", "2022-12-06 23:45:12.503095"]]
  TRANSACTION (1.0ms)  COMMIT                                                                  
 =>                                                                                            
#<CreditCard:0x00007fdac9b7f2b8                                                                
 id: 3,                                                                                        
 number: 420860372648883,                                                                      
 expiration_date: Wed, 07 Dec 2022,          
 owner_id: 2,                                
 created_at: Tue, 06 Dec 2022 23:45:12.503095000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 23:45:12.503095000 UTC +00:00> 
3.0.0 :032 > 

3.id: 1,                                                                           
  number: 2457828455,                                                              
  expiration_date: nil,                                                            
  owner_id: 3,                                                                     
  created_at: Tue, 06 Dec 2022 23:40:58.188293000 UTC +00:00,                      
  updated_at: Tue, 06 Dec 2022 23:40:58.188293000 UTC +00:00>,                     
 #<CreditCard:0x00007fedd4e1fd10                                                  
  id: 2,                                                                          
  number: 2497577628576543,                                                       
  expiration_date: Tue, 06 Dec 2022,                                              
  owner_id: 1,                                                    
  created_at: Tue, 06 Dec 2022 23:43:35.492041000 UTC +00:00,     
  updated_at: Tue, 06 Dec 2022 23:43:35.492041000 UTC +00:00>,
 #<CreditCard:0x00007fedd4e1fc48
  id: 3,
  number: 420860372648883,
  expiration_date: Wed, 07 Dec 2022,
  owner_id: 2,
  created_at: Tue, 06 Dec 2022 23:45:12.503095000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:45:12.503095000 UTC +00:00>,
 #<CreditCard:0x00007fedd4e1fb80
  id: 4,
  number: 4208603726488223,
  expiration_date: Wed, 07 Dec 2022,
  owner_id: 2,
  created_at: Tue, 06 Dec 2022 23:49:39.195532000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:49:39.195532000 UTC +00:00>] 

  4.Add a credit limit to each card.
  id: 1,
  number: 2457828455,
  expiration_date: nil,
  owner_id: 3,
  created_at: Tue, 06 Dec 2022 23:40:58.188293000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 00:25:27.470202000 UTC +00:00,
  credit_limit: 12000000>,
 #<CreditCard:0x00007fe7b809e910
  id: 2,
  number: 2497577628576543,
  expiration_date: Tue, 06 Dec 2022,
  owner_id: 1,
  created_at: Tue, 06 Dec 2022 23:43:35.492041000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 00:25:27.477882000 UTC +00:00,
  credit_limit: 12000000>,
 #<CreditCard:0x00007fe7b809e848
  id: 3,
  number: 420860372648883,
  expiration_date: Wed, 07 Dec 2022,
  owner_id: 2,
  created_at: Tue, 06 Dec 2022 23:45:12.503095000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 00:25:27.511631000 UTC +00:00,
  credit_limit: 12000000>,
 #<CreditCard:0x00007fe7b809e780
  id: 4,
  number: 4208603726488223,
  expiration_date: Wed, 07 Dec 2022,
  owner_id: 2,
  created_at: Tue, 06 Dec 2022 23:49:39.195532000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 00:25:27.518233000 UTC +00:00,
  credit_limit: 12000000>]