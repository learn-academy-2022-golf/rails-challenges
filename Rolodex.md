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
Update the phone number of the last entry in the database.
Retrieve the first_name of the third Person in the database.
Stretch Challenges

Update all the family members with the same last_name as you, to have the same phone number as you.
Remove all family members that do not have your last_name.