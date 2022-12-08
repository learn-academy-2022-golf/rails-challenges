Favorite Movies Challenge
Setup
Create a new Rails application called 'favorite_movies'.

➜  rails-practice-app rails new favorite_movies -d postgresql -T

Create the database

➜  favorite_movies git:(main) ✗ rails db:create
Created database 'favorite_movies_development'
Created database 'favorite_movies_test'

Generate a Movie model with a title attribute and a category attribute

➜  favorite_movies git:(main) ✗ rails generate model Movie title:string category:string
      invoke  active_record
      create    db/migrate/20221206183730_create_movies.rb
      create    app/models/movie.rb

Challenges
Add five entries to the database via the Rails console
3.0.0 :001 > Movie.create title: "Harry Potter", category: "fantasy"
  TRANSACTION (18.2ms)  BEGIN
  Movie Create (2.8ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Harry Potter"], ["category", "fantasy"], ["created_at", "2022-12-06 18:41:24.784271"], ["updated_at", "2022-12-06 18:41:24.784271"]]
  TRANSACTION (1.1ms)  COMMIT
 => 
#<Movie:0x00007f919547c3d0
 id: 1,
 title: "Harry Potter",
 category: "fantasy",
 created_at: Tue, 06 Dec 2022 18:41:24.784271000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 18:41:24.784271000 UTC +00:00> 
3.0.0 :002 > Movie.create title: "Star Wars", category: "sci-fi"
  TRANSACTION (0.2ms)  BEGIN
  Movie Create (0.5ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Star Wars"], ["category", "sci-fi"], ["created_at", "2022-12-06 18:42:15.665902"], ["updated_at", "2022-12-06 18:42:15.665902"]]
  TRANSACTION (1.1ms)  COMMIT                                  
 =>                                                            
#<Movie:0x00007f9196e84bb0                                     
 id: 2,                                                        
 title: "Star Wars",                                           
 category: "sci-fi",                                           
 created_at: Tue, 06 Dec 2022 18:42:15.665902000 UTC +00:00,   
 updated_at: Tue, 06 Dec 2022 18:42:15.665902000 UTC +00:00>   
3.0.0 :003 > Movie.create title: "Lord of the Rings", category: "fantasy"
  TRANSACTION (0.3ms)  BEGIN
  Movie Create (0.6ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Lord of the Rings"], ["category", "fantasy"], ["created_at", "2022-12-06 18:42:41.112342"], ["updated_at", "2022-12-06 18:42:41.112342"]]
  TRANSACTION (1.0ms)  COMMIT                                             
 =>                                                                       
#<Movie:0x00007f919b5cb050                                                
 id: 3,                                                                   
 title: "Lord of the Rings",                                              
 category: "fantasy",                                                     
 created_at: Tue, 06 Dec 2022 18:42:41.112342000 UTC +00:00,              
 updated_at: Tue, 06 Dec 2022 18:42:41.112342000 UTC +00:00>              
3.0.0 :004 > Movie.create title: "Elf", category: "Christmas"
  TRANSACTION (0.3ms)  BEGIN
  Movie Create (0.5ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Elf"], ["category", "Christmas"], ["created_at", "2022-12-06 18:43:13.071053"], ["updated_at", "2022-12-06 18:43:13.071053"]]
  TRANSACTION (0.9ms)  COMMIT                                
 =>                                                          
#<Movie:0x00007f919b519d28                                   
 id: 4,                                                      
 title: "Elf",                                               
 category: "Christmas",                                      
 created_at: Tue, 06 Dec 2022 18:43:13.071053000 UTC +00:00, 
 updated_at: Tue, 06 Dec 2022 18:43:13.071053000 UTC +00:00> 
3.0.0 :005 > Movie.create title: "End Game", category: "action"
  TRANSACTION (0.3ms)  BEGIN
  Movie Create (0.4ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "End Game"], ["category", "action"], ["created_at", "2022-12-06 18:43:33.949687"], ["updated_at", "2022-12-06 18:43:33.949687"]]
  TRANSACTION (1.0ms)  COMMIT                                 
 =>                                                           
#<Movie:0x00007f919b431a78                                    
 id: 5,                                                       
 title: "End Game",                                           
 category: "action",                                          
 created_at: Tue, 06 Dec 2022 18:43:33.949687000 UTC +00:00,  
 updated_at: Tue, 06 Dec 2022 18:43:33.949687000 UTC +00:00>  
3.0.0 :006 > exit

Create a migration to add a new column to the database called movie_length
➜  favorite_movies git:(main) ✗ rails generate migration add_new_column_length
      invoke  active_record
      create    db/migrate/20221206184440_add_new_column_length.rb

      class AddNewColumnLength < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :length, :float
  end
end


Update the values of the five existing attributes to include a movie_length value

3.0.0 :007 > two.update length: 2.25
  TRANSACTION (17.7ms)  BEGIN
  Movie Update (0.8ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 18:58:15.283978"], ["length", 2.25], ["id", 2]]                                                                  
  TRANSACTION (1.2ms)  COMMIT                                      
 => true                                                           
3.0.0 :008 > three = Movie.find 3
  Movie Load (1.1ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 =>                                                                
#<Movie:0x00007faa708148c8                                         
...                                                                
3.0.0 :009 > three.update length: 2.5
  TRANSACTION (0.2ms)  BEGIN
  Movie Update (0.7ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 18:58:39.864096"], ["length", 2.5], ["id", 3]]
  TRANSACTION (1.1ms)  COMMIT                                       
 => true                                                            
3.0.0 :010 > four = Movie.find 4
  Movie Load (13.4ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 4], ["LIMIT", 1]]
 =>                                                                 
#<Movie:0x00007faa70bcc5b0                                          
...                                                                 
3.0.0 :011 > four.update length: 3.25
  TRANSACTION (0.2ms)  BEGIN
  Movie Update (0.4ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 18:59:28.655393"], ["length", 3.25], ["id", 4]]                                                                   
  TRANSACTION (1.0ms)  COMMIT                                       
 => true                                                            
3.0.0 :012 > five = Movie.find 5
  Movie Load (0.4ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 5], ["LIMIT", 1]]
 =>                    
#<Movie:0x00007faa704ffa98
...                    
3.0.0 :013 > five.update length: 3.0
  TRANSACTION (0.3ms)  BEGIN
  Movie Update (0.6ms)  UPDATE "movies" SET "updated_at" = $1, "length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:00:15.671437"], ["length", 3.0], ["id", 5]]
  TRANSACTION (1.0ms)  COMMIT                                      
 => true                                                           
3.0.0 :014 > 


Generate a migration to rename the column 'category' to 'genre'
➜  favorite_movies git:(main) ✗ rails generate migration change_category_to_genre
      invoke  active_record
      create    db/migrate/20221206190103_change_category_to_genre.rb

class ChangeCategoryToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end
