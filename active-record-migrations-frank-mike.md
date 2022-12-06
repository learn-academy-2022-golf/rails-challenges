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