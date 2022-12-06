rails new favorite_movies -d postgresql -T

cd favorite_movies

rails db:create

rails s

rails g model Movies title:string category:string

code .

rails db:migrate

rails c

Movie.create title:"Iron Man", category:"Action"

Movie.create title:"Captain America", category:"Action"

Movie.create title:"The Incredible Hulk", category:"Action"

Movie.create title:"Spider-man", category:"Action"

Movie.create title:"Dr.Strange", category:"Action"

exit

rails g migration add_column_to_movie movie_length:string 

rails db:migrate

rails c

Movie.all

Movie.all.map{|value| value.update movie_length:"90min" }

Movie.all

rails g migration change_category_to_genre category genre

class ChangeCategoryToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end

rails db:migrate

Movie.all

[#<Movie:0x0000000106baad18                                  
  id: 1,                                                     
  title: "Iron Man",                                         
  genre: "Action",                                           
  created_at: Tue, 06 Dec 2022 18:39:32.687806000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:44.047416000 UTC +00:00,
  movie_length: "90min">,                                    
 #<Movie:0x000000011ec4a4e0                                  
  id: 2,                                                     
  title: "Captain America",                                  
  genre: "Action",                                           
  created_at: Tue, 06 Dec 2022 18:40:06.580140000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:44.056053000 UTC +00:00,
  movie_length: "90min">,
 #<Movie:0x000000011ec4a418
  id: 3,
  title: "The Incredible Hulk",
  genre: "Action",
  created_at: Tue, 06 Dec 2022 18:40:25.995221000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:44.058283000 UTC +00:00,
  movie_length: "90min">,
 #<Movie:0x000000011ec4a350
  id: 4,
  title: "Spider-man",
  genre: "Action",
  created_at: Tue, 06 Dec 2022 18:40:43.682718000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:44.061250000 UTC +00:00,
  movie_length: "90min">,
 #<Movie:0x000000011ec4a288
  id: 5,
  title: "Dr.Strange",
  genre: "Action",
  created_at: Tue, 06 Dec 2022 18:40:59.898411000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:44.063266000 UTC +00:00,
  movie_length: "90min">] 