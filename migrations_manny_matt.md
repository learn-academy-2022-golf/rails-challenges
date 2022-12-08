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

# NOTES/DOCUMENTATION

$ rails db:migrate

learnacademy@learns-air migrations_practice % rails db:migrate
== 20221206184058 AddColumnsToMovie: migrating ================================
-- add_column(:movies, :title, :string)
-> 0.0077s
-- add_column(:movies, :category, :string)
-> 0.0012s
== 20221206184058 AddColumnsToMovie: migrated (0.0090s) =======================

$ rails c

learnacademy@learns-air migrations_practice % rails c

# Creating the five Movie instances individually

Loading development environment (Rails 7.0.4)
3.0.0 :001 > Movie.create title:"Avengers: Infinity War", category:"Action"
TRANSACTION (0.3ms)  BEGIN
Movie Create (1.3ms)  INSERT INTO "movies" ("created_at", "updated_at", "title", "category") VALUES ($1, $2, $3, $4) RETURNING "id"  [["created_at", "2022-12-06 18:51:00.265047"], ["updated_at", "2022-12-06 18:51:00.265047"], ["title", "Avengers: Infinity War"], ["category", "Action"]]
TRANSACTION (0.8ms)  COMMIT                                
=>                                                          
#<Movie:0x00007f7df913d340                                   
id: 1,                                                      
created_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00, 
updated_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00, 
title: "Avengers: Infinity War",                            
category: "Action">                                         

3.0.0 :002 > Movie.create title:"Star Wars IV", category:"Sci-Fi"
TRANSACTION (0.2ms)  BEGIN
Movie Create (0.4ms)  INSERT INTO "movies" ("created_at", "updated_at", "title", "category") VALUES ($1, $2, $3, $4) RETURNING "id"  [["created_at", "2022-12-06 18:52:02.810767"], ["updated_at", "2022-12-06 18:52:02.810767"], ["title", "Star Wars IV"], ["category", "Sci-Fi"]]
TRANSACTION (1.0ms)  COMMIT                        
=>                                                  
#<Movie:0x00007f7df44c4c70                           
id: 2,                                              
created_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
title: "Star Wars IV",                      
category: "Sci-Fi">                         

3.0.0 :003 > Movie.create title:"Inception", category:"Psychological"
TRANSACTION (0.2ms)  BEGIN
Movie Create (0.5ms)  INSERT INTO "movies" ("created_at", "updated_at", "title", "category") VALUES ($1, $2, $3, $4) RETURNING "id"  [["created_at", "2022-12-06 18:52:30.351655"], ["updated_at", "2022-12-06 18:52:30.351655"], ["title", "Inception"], ["category", "Psychological"]]
TRANSACTION (1.1ms)  COMMIT                        
=>                                                  
#<Movie:0x00007f7df998c9d8                           
id: 3,                                              
created_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
title: "Inception",
category: "Psychological"> 

3.0.0 :004 > Movie.create title:"Forrest Gump", category:"Drama"
TRANSACTION (0.3ms)  BEGIN
Movie Create (0.5ms)  INSERT INTO "movies" ("created_at", "updated_at", "title", "category") VALUES ($1, $2, $3, $4) RETURNING "id"  [["created_at", "2022-12-06 18:52:55.509892"], ["updated_at", "2022-12-06 18:52:55.509892"], ["title", "Forrest Gump"], ["category", "Drama"]]
TRANSACTION (1.0ms)  COMMIT
=> 
#<Movie:0x00007f7df9835288
id: 4,
created_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
title: "Forrest Gump",
category: "Drama"> 

3.0.0 :005 > Movie.create title:"Bridesmaids", category:"Comedy"
TRANSACTION (0.2ms)  BEGIN
Movie Create (0.4ms)  INSERT INTO "movies" ("created_at", "updated_at", "title", "category") VALUES ($1, $2, $3, $4) RETURNING "id"  [["created_at", "2022-12-06 18:53:17.179495"], ["updated_at", "2022-12-06 18:53:17.179495"], ["title", "Bridesmaids"], ["category", "Comedy"]]
TRANSACTION (1.1ms)  COMMIT
=> 
#<Movie:0x00007f7dfa06c140
id: 5,
created_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
title: "Bridesmaids",
category: "Comedy"> 

$ Movie.all

3.0.0 :006 > Movie.all
Movie Load (1.7ms)  SELECT "movies".* FROM "movies"
=>                                                          
[#<Movie:0x00007f7df453b6b8                                  
id: 1,                                                     
created_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,
title: "Avengers: Infinity War",                           
category: "Action">,                                       
#<Movie:0x00007f7df453b578                                  
id: 2,                                                     
created_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
title: "Star Wars IV",                                     
category: "Sci-Fi">,                                       
#<Movie:0x00007f7df453b4b0                                  
id: 3,
created_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
title: "Inception",
category: "Psychological">,
#<Movie:0x00007f7df453b3e8
id: 4,
created_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
title: "Forrest Gump",
category: "Drama">,
#<Movie:0x00007f7df453b320
id: 5,
created_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
title: "Bridesmaids",
category: "Comedy">]

# We already saved each movie instance to their respective variables, below is where we assign values to the length properties of the movies

3.0.0 :008 > avengers.length = "2:29"
=> "2:29" 
3.0.0 :009 > avengers
=> 
#<Movie:0x00007fb243661b18                                                 
id: 1,                                                                    
created_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,               
updated_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,               
title: "Avengers: Infinity War",                                          
category: "Action",                                                       
length: "2:29">                                                
3.0.0 :010 > star_wars.length = "1:45"
=> "1:45" 
3.0.0 :011 > inception.length = "2:28"
=> "2:28" 
3.0.0 :012 > forrest_gump.length = "2:22"
=> "2:22" 
3.0.0 :013 > bridesmaids.length = "2:05"
=> "2:05"
3.0.0 :018 > star_wars.save
TRANSACTION (0.2ms)  BEGIN
Movie Update (0.5ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:12.611486"], ["length", "1:45"], ["id", 2]]
TRANSACTION (1.0ms)  COMMIT                                    
=> true                                                         
3.0.0 :019 > inception.save
TRANSACTION (0.2ms)  BEGIN
Movie Update (0.7ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:15.432725"], ["length", "2:28"], ["id", 3]]
TRANSACTION (1.3ms)  COMMIT                                    
=> true                                                         
3.0.0 :020 > forrest_gump.save
TRANSACTION (68.1ms)  BEGIN
Movie Update (1.4ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:18.362047"], ["length", "2:22"], ["id", 4]]
TRANSACTION (1.0ms)  COMMIT                                       
=> true                                                            
3.0.0 :021 > bridesmaids.save
TRANSACTION (0.2ms)  BEGIN
Movie Update (0.6ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:20.950657"], ["length", "2:05"], ["id", 5]]
TRANSACTION (1.1ms)  COMMIT                                       
=> true 

# After the saves, we verify one more time that the length values are saved

3.0.0 :022 > Movie.all
Movie Load (0.5ms)  SELECT "movies".* FROM "movies"
=>                                                                 
[#<Movie:0x00007fb24346dfa0                                         
id: 1,                                                           
created_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,      
updated_at: Tue, 06 Dec 2022 19:09:45.849725000 UTC +00:00,      
title: "Avengers: Infinity War",                                 
category: "Action",                                              
length: "2:29">,                                                 
#<Movie:0x00007fb24346ded8                                  
id: 2,                                                     
created_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:12.611486000 UTC +00:00,
title: "Star Wars IV",                                     
category: "Sci-Fi",                                        
length: "1:45">,
#<Movie:0x00007fb24346de10
id: 3,
created_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:15.432725000 UTC +00:00,
title: "Inception",
category: "Psychological",
length: "2:28">,
#<Movie:0x00007fb24346dd48
id: 4,
created_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:18.362047000 UTC +00:00,
title: "Forrest Gump",
category: "Drama",
length: "2:22">,
#<Movie:0x00007fb24346dc80
id: 5,
created_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:20.950657000 UTC +00:00,
title: "Bridesmaids",
category: "Comedy",
length: "2:05">] 

$ rails generate migration rename_category_column_to_genre

# In the newly created file, we input
    # rename_column(:movies, :category, :genre)

$ rails db:migrate

$ rails c

$ Movie.all

[#<Movie:0x00007fca52a53970                       
id: 1,                                                
created_at: Tue, 06 Dec 2022 18:51:00.265047000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:09:45.849725000 UTC +00:00,
title: "Avengers: Infinity War",                           
genre: "Action",                                         
length: "2:29">,                                         
#<Movie:0x00007fca4cc39010                        
id: 2,                                                
created_at: Tue, 06 Dec 2022 18:52:02.810767000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:12.611486000 UTC +00:00,
title: "Star Wars IV",                                     
genre: "Sci-Fi",                                         
length: "1:45">,
#<Movie:0x00007fca4cc38e80
id: 3,
created_at: Tue, 06 Dec 2022 18:52:30.351655000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:15.432725000 UTC +00:00,
title: "Inception",
genre: "Psychological",
length: "2:28">,
#<Movie:0x00007fca4cc38cf0
id: 4,
created_at: Tue, 06 Dec 2022 18:52:55.509892000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:18.362047000 UTC +00:00,
title: "Forrest Gump",
genre: "Drama",
length: "2:22">,
#<Movie:0x00007fca4cc38b60
id: 5,
created_at: Tue, 06 Dec 2022 18:53:17.179495000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:10:20.950657000 UTC +00:00,
title: "Bridesmaids",
genre: "Comedy",
length: "2:05">]