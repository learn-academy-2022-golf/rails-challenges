Challenges:

Add five entries to the database via the Rails console:
(Did this for 5 instances)
3.0.0 :001 > Movie.create title:"golden compass", category:"sci-fi"
  TRANSACTION (4.9ms)  BEGIN
  Movie Create (1.3ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "golden compass"], ["category", "sci-fi"], ["created_at", "2022-12-06 18:50:41.032122"], ["updated_at", "2022-12-06 18:50:41.032122"]]                           
  TRANSACTION (1.4ms)  COMMIT                                      
 =>                                                                
#<Movie:0x00007f909e3964e0                                         
 id: 1,                                                            
 title: "golden compass",                                          
 category: "sci-fi",                                               
 created_at: Tue, 06 Dec 2022 18:50:41.032122000 UTC +00:00,       
 updated_at: Tue, 06 Dec 2022 18:50:41.032122000 UTC +00:00>       
3.0.0 :002 > Movie.create title:"gladiator", category:"epic"

create a migration to add a new column to the databasse called movie_length
learnacademy@LEARNs-MacBook-Air favorite_movies % rails generate migration add_column_movie_length_to_movies
      invoke  active_record
      create    db/migrate/20221206185749_add_column_movie_length_to_movies.rb


Update the values of the five existing attributes to include a movie_length value:
class AddColumnMovieLengthToMovies < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :movie_length, :string
  end
end
learnacademy@LEARNs-MacBook-Air favorite_movies % rails db:migrate
== 20221206185749 AddColumnMovieLengthToMovies: migrating =====================
-- add_column(:movies, :movie_length, :string)
   -> 0.0174s
== 20221206185749 AddColumnMovieLengthToMovies: migrated (0.0175s) ============

(This part was done 5 times, one for each element)
3.0.0 :018 > avatar = Movie.find 5
  Movie Load (8.9ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 5], ["LIMIT", 1]]
 =>                                                                       
#<Movie:0x00007f8a32610710                                            
...                                                                   
3.0.0 :019 > avatar.movie_length = "2:10"
 => "2:10" 
3.0.0 :020 > avatar.save
  TRANSACTION (0.3ms)  BEGIN
  Movie Update (0.5ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:44.396729"], ["movie_length", "2:10"], ["id", 5]]                      
  TRANSACTION (1.0ms)  COMMIT                                         
 => true                                                              


Generate a migration to rename the column 'category' to 'genre':
class ChangeColumnCategoryToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end
learnacademy@LEARNs-MacBook-Air favorite_movies % rails db:migrate
== 20221206191812 ChangeColumnCategoryToGenre: migrating ======================
-- rename_column(:movies, :category, :genre)
   -> 0.0082s
== 20221206191812 ChangeColumnCategoryToGenre: migrated (0.0082s) =============