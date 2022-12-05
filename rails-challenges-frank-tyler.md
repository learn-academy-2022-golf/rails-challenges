# Challenge: Rolodex
As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

# Set Up
# Create a new Rails app named 'rolodex_challenge'.
'''' ruby

rails new rolodex_challenge -d postgresql -T
cd rolodex_challenge


# Create the database. The output in the terminal should look like this:
# Created database 'rolodex_development'
# Created database 'rolodex_test'

$ rails db:create
$ rails server

# Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.

rails generate model Person first_name:string last_name:string phone:string 
      invoke  active_record
      create    db/migrate/20221205221105_create_people.rb
      create    app/models/person.rb

# Run a migration to set up the database.

rails db:migrate
== 20221205221105 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.0083s
== 20221205221105 CreatePeople: migrated (0.0084s) ============================

# Open up Rails console.

rails c

# Actions
# Add five family members into the Person table in the Rails console.

#<Person:0x00000001144db100                                                            
 id: 1,                                                                                
 first_name: "fname1",                                                                 
 last_name: "lname1",                                                                  
 phone: "fonestring1",                                                                 
 created_at: Mon, 05 Dec 2022 22:18:42.216305000 UTC +00:00,                           
 updated_at: Mon, 05 Dec 2022 22:18:42.216305000 UTC +00:00>  

the above repeated 4 more times

# Retrieve all the items in the database.

Person.all

[#<Person:0x0000000115839b98                                                 
  id: 1,                                                                     
  first_name: "fname1",                                                      
  last_name: "lname1",                                                       
  phone: "fonestring1",                                                      
  created_at: Mon, 05 Dec 2022 22:18:42.216305000 UTC +00:00,                
  updated_at: Mon, 05 Dec 2022 22:18:42.216305000 UTC +00:00>,               
 #<Person:0x0000000115839a58                                                 
  id: 2,                                                                     
  first_name: "fname2",                                                      
  last_name: "lname2",                                        
  phone: "fonestring2",                                       
  created_at: Mon, 05 Dec 2022 22:19:55.863491000 UTC +00:00, 
  updated_at: Mon, 05 Dec 2022 22:19:55.863491000 UTC +00:00>,
 #<Person:0x0000000115839850
  id: 3,
  first_name: "fname3",
  last_name: "lname3",
  phone: "fonestring3",
  created_at: Mon, 05 Dec 2022 22:20:08.170173000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:20:08.170173000 UTC +00:00>,
 #<Person:0x00000001158396e8
  id: 4,
  first_name: "fname4",
  last_name: "lname4",
  phone: "fonestring4",
  created_at: Mon, 05 Dec 2022 22:20:27.556414000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:20:27.556414000 UTC +00:00>,
 #<Person:0x0000000115839440
  id: 5,
  first_name: "fname5",
  last_name: "lname5",
  phone: "fonestring5",
  created_at: Mon, 05 Dec 2022 22:20:43.489425000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:20:43.489425000 UTC +00:00>]

# Add yourself to the Person table.
#<Person:0x0000000115831ce0                                                            
 id: 6,                                                                                
 first_name: "frnk",                                                                   
 last_name: "burgs",                                                                   
 phone: "5555555",                                                                     
 created_at: Mon, 05 Dec 2022 22:23:49.741098000 UTC +00:00,                           
 updated_at: Mon, 05 Dec 2022 22:23:49.741098000 UTC +00:00>   

# Retrieve all the entries that have the same last_name as you.

Person.where lname: 'burgs'

[#<Person:0x00000001159d73b0             
  id: 6,                                 
  first_name: "frnk",
  last_name: "burgs",
  phone: "5555555",
  created_at: Mon, 05 Dec 2022 22:23:49.741098000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.741098000 UTC +00:00>] 

# Update the phone number of the last entry in the database.

randomName = Person.last

randomName.phone = '666'

randomName.save

Person.last

#<Person:0x0000000105026cb8                                       
 id: 8,                                                           
 first_name: "frnk",                                              
 last_name: "burgs",                                              
 phone: "666",                                                    
 created_at: Mon, 05 Dec 2022 22:23:49.741098000 UTC +00:00,  
 updated_at: Mon, 05 Dec 2022 22:28:58.060237000 UTC +00:00>


# Retrieve the first_name of the third Person in the database.
Person.third.first_name
  Person Load (0.3ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" ASC LIMIT $1 OFFSET $2  [["LIMIT", 1], ["OFFSET", 2]]                                       
 => "fname3" 

## Stretch Challenges

# Update all the family members with the same last_name as you, to have the same phone number as you.


# Remove all family members that do not have your last_name.

