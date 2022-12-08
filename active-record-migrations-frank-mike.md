# Favorite Movies Challenge
# Setup
# Create a new Rails application called 'favorite_movies'.
rails new favorite_movies -d postgresql -T
cd favorite_movies

# Create the database
rails db:create

rails generate model List
rails s

# Generate a Movie model with a title attribute and a category attribute

rails generate migration add_columns_to_list

invoke  active_record
      create    db/migrate/20221206191642_add_columns_to_list.rb




rails generate model FavoriteMovie title:string category:string

      invoke  active_record
      create    db/migrate/20221206184952_create_favorite_movies.rb
      create    app/models/favorite_movie.rb

rails db:migrate

== 20221206184952 CreateFavoriteMovies: migrating =============================
-- create_table(:favorite_movies)
   -> 0.0072s
== 20221206184952 CreateFavoriteMovies: migrated (0.0073s) ====================

class FavoriteMovie < ApplicationRecord
end

# Challenges
# Add five entries to the database via the Rails console
rails c

FavoriteMovies.create title:"Home alone 1" category:"Political Commentary"
FavoriteMovies.create title:"Thank you for smoking" category:"Political Commentary"
FavoriteMovies.create title:"1984" category:"Documentary"
FavoriteMovies.create title:"Patton:"Documentary"
FavoriteMovies.create title:"Time Cop" category:"Science Fiction"

# Create a migration to add a new column to the database called movie_length

# Update the values of the five existing attributes to include a movie_length value

# Generate a migration to rename the column 'category' to 'genre'

This is what we did in the terminal and Rails C
****************************************************************************************************
➜  favorite_movies git:(main) ✗ rails generate model FavoriteMovies title:string catagory:string
[WARNING] The model name 'FavoriteMovies' was recognized as a plural, using the singular 'FavoriteMovie' instead. Override with --force-plural or setup custom inflection rules for this noun before running the generator.
      invoke  active_record
      create    db/migrate/20221206193454_create_favorite_movies.rb
      create    app/models/favorite_movie.rb
➜  favorite_movies git:(main) ✗ rails db:migrate
== 20221206193454 CreateFavoriteMovies: migrating =============================
-- create_table(:favorite_movies)
   -> 0.0057s
== 20221206193454 CreateFavoriteMovies: migrated (0.0058s) ====================

➜  favorite_movies git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > FavoriteMovie.create title: "Home Alone 1", catagory: "Political Commentary"
  TRANSACTION (0.2ms)  BEGIN
  FavoriteMovie Create (2.2ms)  INSERT INTO "favorite_movies" ("title", "catagory", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Home Alone 1"], ["catagory", "Political Commentary"], ["created_at", "2022-12-06 19:39:04.690196"], ["updated_at", "2022-12-06 19:39:04.690196"]]                                
  TRANSACTION (1.8ms)  COMMIT                                                                
 =>                                                                                          
#<FavoriteMovie:0x00000001102b8f98                                                           
 id: 1,                                                                                      
 title: "Home Alone 1",                                                                      
 catagory: "Political Commentary",                                       
 created_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00,             
 updated_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00>             
3.0.0 :002 > FavoriteMovie.create title: "1984", catagory: "Documentary" 
  TRANSACTION (0.5ms)  BEGIN
  FavoriteMovie Create (0.8ms)  INSERT INTO "favorite_movies" ("title", "catagory", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "1984"], ["catagory", "Documentary"], ["created_at", "2022-12-06 19:42:15.305376"], ["updated_at", "2022-12-06 19:42:15.305376"]]                                                   
  TRANSACTION (0.8ms)  COMMIT                                                                  
 =>                                                                                            
#<FavoriteMovie:0x000000010794c548                                                             
 id: 2,                                                                                        
 title: "1984",                                                                                
 catagory: "Documentary",                                            
 created_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00,         
 updated_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00>         
3.0.0 :003 > FavoriteMovie.create title: "Home Alone 2", catagory: "Political Commentary"
  TRANSACTION (0.5ms)  BEGIN
  FavoriteMovie Create (0.7ms)  INSERT INTO "favorite_movies" ("title", "catagory", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Home Alone 2"], ["catagory", "Political Commentary"], ["created_at", "2022-12-06 19:43:50.891821"], ["updated_at", "2022-12-06 19:43:50.891821"]]        
  TRANSACTION (0.3ms)  COMMIT                                        
 =>                                                                  
#<FavoriteMovie:0x0000000106120050                                   
 id: 3,                                                              
 title: "Home Alone 2",                                              
 catagory: "Political Commentary",                                   
 created_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00,         
 updated_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00>         
3.0.0 :004 > FavoriteMovie.create title: "Patton", catagory: "Documentary"
  TRANSACTION (0.4ms)  BEGIN
  FavoriteMovie Create (0.6ms)  INSERT INTO "favorite_movies" ("title", "catagory", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Patton"], ["catagory", "Documentary"], ["created_at", "2022-12-06 19:44:35.535849"], ["updated_at", "2022-12-06 19:44:35.535849"]]
  TRANSACTION (2.9ms)  COMMIT
 => 
#<FavoriteMovie:0x0000000107bcf770
 id: 4,
 title: "Patton",
 catagory: "Documentary",
 created_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00> 
3.0.0 :005 > FavoriteMovie.create title: "Time Cop", catagory: "Political Commentary"
  TRANSACTION (0.4ms)  BEGIN
  FavoriteMovie Create (0.7ms)  INSERT INTO "favorite_movies" ("title", "catagory", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Time Cop"], ["catagory", "Political Commentary"], ["created_at", "2022-12-06 19:45:37.852685"], ["updated_at", "2022-12-06 19:45:37.852685"]]            
  TRANSACTION (0.7ms)  COMMIT                                        
 =>                                                                  
#<FavoriteMovie:0x0000000107a162d0                                   
 id: 5,                                                              
 title: "Time Cop",                                                  
 catagory: "Political Commentary",                                   
 created_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00,         
 updated_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00>         
3.0.0 :006 > exit
➜  favorite_movies git:(main) ✗ rails g migration add_column_movie_length_to_favorite_movie
      invoke  active_record
      create    db/migrate/20221206195128_add_column_movie_length_to_favorite_movie.rb
➜  favorite_movies git:(main) ✗ rails db:migrate 
== 20221206195128 AddColumnMovieLengthToFavoriteMovie: migrating ==============
== 20221206195128 AddColumnMovieLengthToFavoriteMovie: migrated (0.0000s) =====

➜  favorite_movies git:(main) ✗ code .
➜  favorite_movies git:(main) ✗ rails g migration add_column_to_favorite_movie
      invoke  active_record
      create    db/migrate/20221206200206_add_column_to_favorite_movie.rb
➜  favorite_movies git:(main) ✗ rails db:migrate 
== 20221206200206 AddColumnToFavoriteMovie: migrating =========================
-- add_column(:favorite_movie, :movie_length, :string)
rails aborted!
StandardError: An error has occurred, this and all later migrations canceled:

PG::UndefinedTable: ERROR:  relation "favorite_movie" does not exist
/Users/learnacademy/Desktop/ar-migration/favorite_movies/db/migrate/20221206200206_add_column_to_favorite_movie.rb:3:in `change'

Caused by:
ActiveRecord::StatementInvalid: PG::UndefinedTable: ERROR:  relation "favorite_movie" does not exist
/Users/learnacademy/Desktop/ar-migration/favorite_movies/db/migrate/20221206200206_add_column_to_favorite_movie.rb:3:in `change'

Caused by:
PG::UndefinedTable: ERROR:  relation "favorite_movie" does not exist
/Users/learnacademy/Desktop/ar-migration/favorite_movies/db/migrate/20221206200206_add_column_to_favorite_movie.rb:3:in `change'
Tasks: TOP => db:migrate
(See full trace by running task with --trace)
➜  favorite_movies git:(main) ✗ rails db:migrate 
== 20221206200206 AddColumnToFavoriteMovie: migrating =========================
-- add_column(:favorite_movies, :movie_length, :string)
   -> 0.0028s
== 20221206200206 AddColumnToFavoriteMovie: migrated (0.0029s) ================

➜  favorite_movies git:(main) ✗ FavoriteMovie.all
zsh: command not found: FavoriteMovie.all
➜  favorite_movies git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > FavoriteMovie.all
  FavoriteMovie Load (0.5ms)  SELECT "favorite_movies".* FROM "favorite_movies"
 =>                                                                  
[#<FavoriteMovie:0x0000000106206320                                  
  id: 1,                                                             
  title: "Home Alone 1",                                             
  catagory: "Political Commentary",                                  
  created_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00,        
  movie_length: nil>,                                                
 #<FavoriteMovie:0x00000001064b6048                                  
  id: 2,                                                             
  title: "1984",                                                     
  catagory: "Documentary",                                           
  created_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00,        
  movie_length: nil>,
 #<FavoriteMovie:0x00000001064b5f80
  id: 3,
  title: "Home Alone 2",
  catagory: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00,
  movie_length: nil>,
 #<FavoriteMovie:0x00000001064b5eb8
  id: 4,
  title: "Patton",
  catagory: "Documentary",
  created_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00,
  movie_length: nil>,
 #<FavoriteMovie:0x00000001064b5df0
  id: 5,
  title: "Time Cop",
  catagory: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00,
  movie_length: nil>] 
3.0.0 :002 > FavoriteMovie.movie_length
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `movie_length' for FavoriteMovie:Class (NoMethodError)
3.0.0 :003 > new = FavoriteMovie.update "movie_length: '60min'"
  FavoriteMovie Load (16.9ms)  SELECT "favorite_movies".* FROM "favorite_movies"
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_assignment.rb:30:in `assign_attributes': When assigning attributes, you must pass a hash as an argument, String passed. (ArgumentError)
3.0.0 :004 > new = FavoriteMovie.update movie_length: "60min"
  FavoriteMovie Load (1.2ms)  SELECT "favorite_movies".* FROM "favorite_movies"
  TRANSACTION (0.2ms)  BEGIN                                         
  FavoriteMovie Update (2.4ms)  UPDATE "favorite_movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "favorite_movies"."id" = $3  [["updated_at", "2022-12-06 20:29:28.476909"], ["movie_length", "60min"], ["id", 1]]
  TRANSACTION (1.3ms)  COMMIT                                        
  TRANSACTION (0.1ms)  BEGIN                                         
  FavoriteMovie Update (0.2ms)  UPDATE "favorite_movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "favorite_movies"."id" = $3  [["updated_at", "2022-12-06 20:29:28.500553"], ["movie_length", "60min"], ["id", 2]]
  TRANSACTION (0.1ms)  COMMIT                                        
  TRANSACTION (0.1ms)  BEGIN                                         
  FavoriteMovie Update (0.5ms)  UPDATE "favorite_movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "favorite_movies"."id" = $3  [["updated_at", "2022-12-06 20:29:28.501849"], ["movie_length", "60min"], ["id", 3]]
  TRANSACTION (0.2ms)  COMMIT
  TRANSACTION (0.1ms)  BEGIN
  FavoriteMovie Update (0.2ms)  UPDATE "favorite_movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "favorite_movies"."id" = $3  [["updated_at", "2022-12-06 20:29:28.503246"], ["movie_length", "60min"], ["id", 4]]
  TRANSACTION (0.2ms)  COMMIT
  TRANSACTION (0.1ms)  BEGIN
  FavoriteMovie Update (0.4ms)  UPDATE "favorite_movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "favorite_movies"."id" = $3  [["updated_at", "2022-12-06 20:29:28.504295"], ["movie_length", "60min"], ["id", 5]]
  TRANSACTION (0.3ms)  COMMIT
 => 
[#<FavoriteMovie:0x00000001088f2538
... 
3.0.0 :005 > FavoriteMovie.al
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `al' for FavoriteMovie:Class (NoMethodError)
Did you mean?  all                                                   
3.0.0 :006 > FavoriteMovie.all
  FavoriteMovie Load (0.8ms)  SELECT "favorite_movies".* FROM "favorite_movies"
 =>                                                                  
[#<FavoriteMovie:0x000000010786cf60                                  
  id: 1,                                                             
  title: "Home Alone 1",                                             
  catagory: "Political Commentary",                                  
  created_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 20:29:28.476909000 UTC +00:00,        
  movie_length: "60min">,                                            
 #<FavoriteMovie:0x000000010786ce98                                  
  id: 2,                                                             
  title: "1984",                                                     
  catagory: "Documentary",                                           
  created_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 20:29:28.500553000 UTC +00:00,        
  movie_length: "60min">,
 #<FavoriteMovie:0x000000010786cdd0
  id: 3,
  title: "Home Alone 2",
  catagory: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.501849000 UTC +00:00,
  movie_length: "60min">,
 #<FavoriteMovie:0x000000010786cd08
  id: 4,
  title: "Patton",
  catagory: "Documentary",
  created_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.503246000 UTC +00:00,
  movie_length: "60min">,
 #<FavoriteMovie:0x000000010786cc40
  id: 5,
  title: "Time Cop",
  catagory: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.504295000 UTC +00:00,
  movie_length: "60min">] 
3.0.0 :007 > exit
➜  favorite_movies git:(main) ✗ rails g migration change_name_of_catagory_to_genre
      invoke  active_record
      create    db/migrate/20221206203526_change_name_of_catagory_to_genre.rb
➜  favorite_movies git:(main) ✗ code .
➜  favorite_movies git:(main) ✗ rails db:migrate
== 20221206203526 ChangeNameOfCatagoryToGenre: migrating ======================
-- rename_column(:favorite_movies, :catagory, :genre)
   -> 0.0051s
== 20221206203526 ChangeNameOfCatagoryToGenre: migrated (0.0052s) =============

➜  favorite_movies git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > FavoriteMovie.all
  FavoriteMovie Load (0.6ms)  SELECT "favorite_movies".* FROM "favorite_movies"
 =>                                                                  
[#<FavoriteMovie:0x000000010487f730                                  
  id: 1,                                                             
  title: "Home Alone 1",                                             
  genre: "Political Commentary",                                     
  created_at: Tue, 06 Dec 2022 19:39:04.690196000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 20:29:28.476909000 UTC +00:00,        
  movie_length: "60min">,                                            
 #<FavoriteMovie:0x0000000103bed738                                  
  id: 2,                                                             
  title: "1984",                                                     
  genre: "Documentary",                                              
  created_at: Tue, 06 Dec 2022 19:42:15.305376000 UTC +00:00,        
  updated_at: Tue, 06 Dec 2022 20:29:28.500553000 UTC +00:00,        
  movie_length: "60min">,
 #<FavoriteMovie:0x0000000103bed670
  id: 3,
  title: "Home Alone 2",
  genre: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:43:50.891821000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.501849000 UTC +00:00,
  movie_length: "60min">,
 #<FavoriteMovie:0x0000000103bed5a8
  id: 4,
  title: "Patton",
  genre: "Documentary",
  created_at: Tue, 06 Dec 2022 19:44:35.535849000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.503246000 UTC +00:00,
  movie_length: "60min">,
 #<FavoriteMovie:0x0000000103bed4e0
  id: 5,
  title: "Time Cop",
  genre: "Political Commentary",
  created_at: Tue, 06 Dec 2022 19:45:37.852685000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 20:29:28.504295000 UTC +00:00,
  movie_length: "60min">] 
3.0.0 :002 > 
