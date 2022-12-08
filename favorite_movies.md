Favorite Movies Challenge

Setup

Create a new Rails application called 'favorite_movies'.
-$ rails new favorite_movies -d postgresql -T

Create the database
-$ rails db:create

Generate a Movie model with a title attribute and a category attribute
-$ rails g model Movie title:string category:string
invoke active_record
create db/migrate/20221206183856_create_movies.rb
create app/models/movie.rb

```ruby
class CreateMovies < ActiveRecord::Migration[7.0]
  def change
    create_table :movies do |t|
      t.string :title
      t.string :category

      t.timestamps
    end
  end
end

```

Challenges

Add five entries to the database via the Rails console
-$ rails c
[#<Movie:0x00007f9b31afdf38
id: 1,
title: "Predator",
category: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:52:27.710541000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:52:27.710541000 UTC +00:00>,
#<Movie:0x00007f9b31afdad8
id: 2,
title: "Star-Wars",
category: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:53:26.166939000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:53:26.166939000 UTC +00:00>,
#<Movie:0x00007f9b31afd538
id: 3,
title: "Star-Trek",
category: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:53:44.634879000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:53:44.634879000 UTC +00:00>,
#<Movie:0x00007f9b31afd088
id: 4,
title: "Aliens",
category: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:54:00.290540000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:54:00.290540000 UTC +00:00>,
#<Movie:0x00007f9b31afce58
id: 5,
title: "Aliens VS Predator",
category: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:54:15.589092000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 18:54:15.589092000 UTC +00:00>]

Create a migration to add a new column to the database called movie_length

```ruby
class AddColumnToTheDatabaseCalledMovieLength < ActiveRecord::Migration[7.0]
  def change
  end
end

```

accidentaly migrated to database, have to generate a new migration

Update the values of the five existing attributes to include a movie_length value

- inside rails console
- create a variable for the movie that we want to update
- $ Predator = Movie.find 1
- then update with command
- Predator.update movie_length:"3 Hr"

```ruby
class AddColumnToTheDatabaseCalledMovieLength2 < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :movie_length, :string
  end
end
```

Generate a migration to rename the column 'category' to 'genre'

```ruby
class ChangeCategoryToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end
```

-$ rails db:migrate

[#<Movie:0x00007fb01c8a09e8
 id: 1,
 title: "Predator",
 genre: "Sci-Fi",
 created_at: Tue, 06 Dec 2022 18:52:27.710541000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:17:08.499712000 UTC +00:00,
movie_length: "3 Hr">,
 #<Movie:0x00007fb01c8a0920
 id: 2,
 title: "Star-Wars",
 genre: "Sci-Fi",
 created_at: Tue, 06 Dec 2022 18:53:26.166939000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:21:22.167264000 UTC +00:00,
movie_length: "30 Days">,
#<Movie:0x00007fb01c8a0858
id: 3,
title: "Star-Trek",
genre: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:53:44.634879000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:22:16.443985000 UTC +00:00,
movie_length: "1 Year">,
#<Movie:0x00007fb01c8a0790
id: 4,
title: "Aliens",
genre: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:54:00.290540000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:23:05.174668000 UTC +00:00,
movie_length: "30 sec">,
#<Movie:0x00007fb01c8a06c8
id: 5,
title: "Aliens VS Predator",
genre: "Sci-Fi",
created_at: Tue, 06 Dec 2022 18:54:15.589092000 UTC +00:00,
updated_at: Tue, 06 Dec 2022 19:24:13.621996000 UTC +00:00,
movie_length: "1 week">]
