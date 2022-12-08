Setup
#Create a new Rails application called 'favorite_movies'.

#Create the database

#Generate a Movie model with a title attribute and a category attribute

rails generate model Movie title:string category:string 

Challenges
#Add five entries to the database via the Rails console

``` ruby 
  Movie Load (0.6ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x0000000127b144a0                                  
  id: 1,                                                     
  title: "Mean Girls",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00>,
 #<Movie:0x0000000127b87f68                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00>,
 #<Movie:0x0000000127b87ea0                                  
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00>,
 #<Movie:0x0000000127b87dd8
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00>,
 #<Movie:0x0000000127b87d10
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00>] 
3.0.0 :008 > 
```

#Create a migration to add a new column to the database called movie_length

``` ruby

class AddColumnMovieLength < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :movie_length, :float
  end
end

```
#Update the values of the five existing attributes to include a movie_length value
```ruby

3.0.0 :024 > Movie.all
  Movie Load (0.4ms)  SELECT "movies".* FROM "movies"
 =>                                                                                   
[#<Movie:0x000000010e8e6390                                                           
  id: 1,                                                                              
  title: "Mean Girls",                                                                
  category: "comedy",                                                                 
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,                         
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,                         
  movie_length: 1.37>,                                       
 #<Movie:0x000000010e8e6278                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>,
 #<Movie:0x000000010e8e61b0
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,
  movie_length: 1.36>,
 #<Movie:0x000000010e8e60c0
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:12:19.706580000 UTC +00:00,
  movie_length: 1.22>,
 #<Movie:0x000000010e8e5ff8
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:14:42.997061000 UTC +00:00,
  movie_length: 1.34>] 
3.0.0 :025 > 

```
#Generate a migration to rename the column 'category' to 'genre'
```ruby

class ChangeCategoryColumnNameToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end
Last login: Mon Dec  5 13:46:58 on ttys000
➜  ~ desktop
➜  desktop golf
➜  golf ls
-tic-tac-toe-kent-zeke             react-challenges
GitHub-Practice                    react-challenges-personal
Pairing-Activity                   ruby-challenges
database-challenges                terminal.md
ezequielperez.github.io            test
javascript-foundations-challenges  text-based-game-frank-zeke
javascript-intro-challenges        treasurehunt-challenge
practice-challenges                weekly-assessments
random-check-in-question-generator whiteboarding-practice
➜  golf mkdir rails-challenges
➜  golf rails-challenges 
➜  rails-challenges ls
➜  rails-challenges git clone https://github.com/learn-academy-2022-golf/rails-challenges.git
Cloning into 'rails-challenges'...
remote: Enumerating objects: 33, done.
remote: Counting objects: 100% (33/33), done.
remote: Compressing objects: 100% (29/29), done.
remote: Total 33 (delta 9), reused 20 (delta 3), pack-reused 0
Receiving objects: 100% (33/33), 26.80 KiB | 1.07 MiB/s, done.
Resolving deltas: 100% (9/9), done.
➜  rails-challenges ls
rails-challenges
➜  rails-challenges rails-challenges 
➜  rails-challenges git:(main) git checkout -b migrations-tt-zp
Switched to a new branch 'migrations-tt-zp'
➜  rails-challenges git:(migrations-tt-zp) touch migration-tabi-zeke.md
➜  rails-challenges git:(migrations-tt-zp) ✗ git branch
➜  rails-challenges git:(migrations-tt-zp) ✗ rails new favorite_movie -d postgresql -T
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  .gitattributes
      create  Gemfile
         run  git init from "."
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /Users/learnacademy/Desktop/golf/rails-challenges/rails-challenges/favorite_movie/.git/
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/assets.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/new_framework_defaults_7_0.rb
      create  config/initializers/permissions_policy.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_7_0.rb
         run  bundle install
Fetching gem metadata from https://rubygems.org/...........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Using rake 13.0.6
Using concurrent-ruby 1.1.10
Using websocket-extensions 0.1.5
Using marcel 1.0.2
Using erubi 1.11.0
Using timeout 0.3.1
Using bindex 0.8.1
Using msgpack 1.6.0
Using bundler 2.2.3
Using minitest 5.16.3
Using method_source 1.0.0
Using thor 1.2.1
Using racc 1.6.1
Using mini_mime 1.1.2
Using pg 1.4.5
Using i18n 1.12.0
Using tzinfo 2.0.5
Using websocket-driver 0.7.5
Using net-protocol 0.2.0
Using bootsnap 1.15.0
Using rack 2.2.4
Using activesupport 7.0.4
Using nokogiri 1.13.9 (arm64-darwin)
Using net-imap 0.3.1
Using rails-dom-testing 2.0.3
Using io-console 0.5.11
Using rack-test 2.0.2
Using globalid 1.0.0
Using activemodel 7.0.4
Using sprockets 4.1.1
Using activejob 7.0.4
Using activerecord 7.0.4
Using crass 1.0.6
Using zeitwerk 2.6.6
Using net-pop 0.1.2
Using net-smtp 0.3.3
Using nio4r 2.5.8
Using mail 2.8.0
Using reline 0.3.1
Using loofah 2.19.0
Using builder 3.2.4
Using puma 5.6.5
Using rails-html-sanitizer 1.4.3
Using irb 1.5.1
Using actionview 7.0.4
Using debug 1.7.0
Using actionpack 7.0.4
Using jbuilder 2.11.5
Using actioncable 7.0.4
Using activestorage 7.0.4
Using actionmailer 7.0.4
Using railties 7.0.4
Using sprockets-rails 3.4.2
Using importmap-rails 1.1.5
Using actionmailbox 7.0.4
Using stimulus-rails 1.2.1
Using turbo-rails 1.3.2
Using web-console 4.2.0
Using actiontext 7.0.4
Using rails 7.0.4
Bundle complete! 12 Gemfile dependencies, 60 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
         run  bundle binstubs bundler
       rails  importmap:install
Add Importmap include tags in application layout
      insert  app/views/layouts/application.html.erb
Create application.js module as entrypoint
      create  app/javascript/application.js
Use vendor/javascript for downloaded pins
      create  vendor/javascript
      create  vendor/javascript/.keep
Ensure JavaScript files are in the Sprocket manifest
      append  app/assets/config/manifest.js
Configure importmap paths in config/importmap.rb
      create  config/importmap.rb
Copying binstub
      create  bin/importmap
       rails  turbo:install stimulus:install
Import Turbo
      append  app/javascript/application.js
Pin Turbo
      append  config/importmap.rb
Run turbo:install:redis to switch on Redis and use it in development for turbo streams
Create controllers directory
      create  app/javascript/controllers
      create  app/javascript/controllers/index.js
      create  app/javascript/controllers/application.js
      create  app/javascript/controllers/hello_controller.js
Import Stimulus controllers
      append  app/javascript/application.js
Pin Stimulus
Appending: pin "@hotwired/stimulus", to: "stimulus.min.js", preload: true"
      append  config/importmap.rb
Appending: pin "@hotwired/stimulus-loading", to: "stimulus-loading.js", preload: true
      append  config/importmap.rb
Pin all controllers
Appending: pin_all_from "app/javascript/controllers", under: "controllers"
      append  config/importmap.rb
➜  rails-challenges git:(migrations-tt-zp) ✗ favorite_movie 
➜  favorite_movie git:(main) ✗ rails db:create
Created database 'favorite_movie_development'
Created database 'favorite_movie_test'
➜  favorite_movie git:(main) ✗ rails s 
=> Booting Puma
=> Rails 7.0.4 application starting in development 
=> Run `bin/rails server --help` for more startup options
Puma starting in single mode...
* Puma version: 5.6.5 (ruby 3.0.0-p0) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*          PID: 12534
* Listening on http://127.0.0.1:3000
* Listening on http://[::1]:3000
Use Ctrl-C to stop
Started GET "/" for 127.0.0.1 at 2022-12-06 10:35:44 -0800
Processing by Rails::WelcomeController#index as HTML
  Rendering /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb
  Rendered /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb (Duration: 1.0ms | Allocations: 840)
Completed 200 OK in 8ms (Views: 3.3ms | ActiveRecord: 0.0ms | Allocations: 7305)


code .
^C- Gracefully stopping, waiting for requests to finish
=== puma shutdown: 2022-12-06 10:35:58 -0800 ===
- Goodbye!
Exiting
➜  favorite_movie git:(main) ✗ code .
➜  favorite_movie git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > 
^C                                     
3.0.0 :001 > exit
➜  favorite_movie git:(main) ✗ rails generate model FavoriteMovie title:string category:string
      invoke  active_record
The name 'FavoriteMovie' is either already used in your application or reserved by Ruby on Rails. Please choose an alternative or use --skip-collision-check or --force to skip this check and run this generator again.
➜  favorite_movie git:(main) ✗ rails generate model Movie title:string category:string 
      invoke  active_record
      create    db/migrate/20221206184232_create_movies.rb
      create    app/models/movie.rb
➜  favorite_movie git:(main) ✗ rails db:migrate
== 20221206184232 CreateMovies: migrating =====================================
-- create_table(:movies)
   -> 0.0098s
== 20221206184232 CreateMovies: migrated (0.0099s) ============================

➜  favorite_movie git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Movie.create title:"Mean Girls", categories:"comedy"
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_assignment.rb:51:in `_assign_attribute': unknown attribute 'categories' for Movie. (ActiveModel::UnknownAttributeError)                                                                        
3.0.0 :002 > Movie.create title:"Mean Girls", category:"comedy"
  TRANSACTION (0.2ms)  BEGIN
  Movie Create (6.8ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Mean Girls"], ["category", "comedy"], ["created_at", "2022-12-06 18:47:13.468534"], ["updated_at", "2022-12-06 18:47:13.468534"]]      
  TRANSACTION (5.2ms)  COMMIT                                               
 =>                                                                         
#<Movie:0x000000012629b658                                                  
 id: 1,                                                                     
 title: "Mean Girls",                                                       
 category: "comedy",                                                        
 created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,                
 updated_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00> 
3.0.0 :003 > Movie.create title:"The Grinch", category:"comedy" 
  TRANSACTION (0.3ms)  BEGIN
  Movie Create (0.5ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "The Grinch"], ["category", "comedy"], ["created_at", "2022-12-06 18:48:48.369836"], ["updated_at", "2022-12-06 18:48:48.369836"]]
  TRANSACTION (4.1ms)  COMMIT
 => 
#<Movie:0x0000000117156d60
 id: 2,
 title: "The Grinch",
 category: "comedy",
 created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00> 
3.0.0 :004 > Movie.create title:"Mr Deeds", category:"comedy"
  TRANSACTION (0.8ms)  BEGIN
  Movie Create (1.0ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Mr Deeds"], ["category", "comedy"], ["created_at", "2022-12-06 18:49:33.821973"], ["updated_at", "2022-12-06 18:49:33.821973"]]
  TRANSACTION (0.6ms)  COMMIT                        
 =>                                                  
#<Movie:0x0000000127f05c58                           
 id: 3,                                              
 title: "Mr Deeds",                                  
 category: "comedy",                                 
 created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00> 
3.0.0 :005 > Movie.create title:"Napolean Dynamite", category:"comedy"
  TRANSACTION (0.2ms)  BEGIN
  Movie Create (0.5ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Napolean Dynamite"], ["category", "comedy"], ["created_at", "2022-12-06 18:49:53.902250"], ["updated_at", "2022-12-06 18:49:53.902250"]]
  TRANSACTION (4.7ms)  COMMIT                              
 =>                                                        
#<Movie:0x00000001201e4cb0                                 
 id: 4,                                                    
 title: "Napolean Dynamite",                               
 category: "comedy",                                       
 created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00> 
3.0.0 :006 > Movie.create title:"Big Daddy", category:"comedy"
  TRANSACTION (0.2ms)  BEGIN
  Movie Create (0.4ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Big Daddy"], ["category", "comedy"], ["created_at", "2022-12-06 18:50:12.441732"], ["updated_at", "2022-12-06 18:50:12.441732"]]
  TRANSACTION (4.9ms)  COMMIT                         
 =>                                                   
#<Movie:0x000000012059c830                            
 id: 5,                                               
 title: "Big Daddy",                                  
 category: "comedy",                                  
 created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00> 
3.0.0 :007 > Movie.all
  Movie Load (0.6ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x0000000127b144a0                                  
  id: 1,                                                     
  title: "Mean Girls",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00>,
 #<Movie:0x0000000127b87f68                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00>,
 #<Movie:0x0000000127b87ea0                                  
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00>,
 #<Movie:0x0000000127b87dd8
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00>,
 #<Movie:0x0000000127b87d10
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00>] 
3.0.0 :008 > 
^C                                                           
3.0.0 :008 > exit
➜  favorite_movie git:(main) ✗ rails generate migration add_column_movie_length
      invoke  active_record
      create    db/migrate/20221206185718_add_column_movie_length.rb
➜  favorite_movie git:(main) ✗ rails db:migrate 
== 20221206185718 AddColumnMovieLength: migrating =============================
-- add_column(:movies, :movie_length, :float)
   -> 0.0061s
== 20221206185718 AddColumnMovieLength: migrated (0.0061s) ====================

➜  favorite_movie git:(main) ✗ rails c 
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Movie.all
  Movie Load (0.6ms)  SELECT "movies".* FROM "movies"
 =>                                                                         
[#<Movie:0x0000000118abebe0                                                 
  id: 1,                                                                    
  title: "Mean Girls",                                                      
  category: "comedy",                                                       
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,               
  updated_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,               
  movie_length: nil>,                                                       
 #<Movie:0x0000000118bcdab8                                                 
  id: 2,                                                                    
  title: "The Grinch",                                                      
  category: "comedy",                                                       
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,               
  updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,               
  movie_length: nil>,
 #<Movie:0x0000000118bcd9f0
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118bcd928
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118bcd860
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  movie_length: nil>] 
3.0.0 :002 > mean_girls = Movie.find 1 
  Movie Load (0.3ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                          
 =>                                                                                   
#<Movie:0x0000000118b556a8                                                            
...                                                                                   
3.0.0 :003 > mean_girls 
 => 
#<Movie:0x0000000118b556a8                                                            
 id: 1,                                                                               
 title: "Mean Girls",                                                                 
 category: "comedy",                                                                  
 created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,                          
 updated_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,                          
 movie_length: nil>                                                                   
3.0.0 :004 > mean_girls.update :movie_length
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_assignment.rb:30:in `assign_attributes': When assigning attributes, you must pass a hash as an argument, Symbol passed. (ArgumentError)                                
3.0.0 :005 > mean_girls.update movie_length:1.37
  TRANSACTION (0.5ms)  BEGIN
  Movie Update (7.4ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:06:35.381757"], ["movie_length", 1.37], ["id", 1]]                                                                    
  TRANSACTION (1.0ms)  COMMIT                                                         
 => true                                                                              
3.0.0 :006 > mean
(irb):6:in `<main>': undefined local variable or method `mean' for main:Object (NameError)                                                                                  
3.0.0 :007 > mean_girls
 => 
#<Movie:0x0000000118b556a8                                                            
 id: 1,                                                                               
 title: "Mean Girls",                                                                 
 category: "comedy",                                                                  
 created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
 updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
 movie_length: 1.37> 
3.0.0 :008 > Movie.all
  Movie Load (8.5ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x0000000118fdfef8                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  movie_length: nil>,                                        
 #<Movie:0x0000000118fdfe30                                  
  id: 3,                                                     
  title: "Mr Deeds",                                         
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118fdfd68
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118fdfca0
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118fdfbd8
  id: 1,
  title: "Mean Girls",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
  movie_length: 1.37>] 
3.0.0 :009 > the_grinch = Movie.find 2
  Movie Load (0.8ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]                                                          
 =>                                                                                   
#<Movie:0x00000001190b5418                                                            
...                                                                                   
3.0.0 :010 > the_grinch
 => 
#<Movie:0x00000001190b5418                                                            
 id: 2,                                                                               
 title: "The Grinch",                                                                 
 category: "comedy",                                                                  
 created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,                          
 updated_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,                          
 movie_length: nil>                                                                   
3.0.0 :011 > the_grinch.update movie_length:1.45
  TRANSACTION (0.5ms)  BEGIN
  Movie Update (0.6ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:08:54.392540"], ["movie_length", 1.45], ["id", 2]]                                                                    
  TRANSACTION (4.8ms)  COMMIT                                                         
 => true                                                                              
3.0.0 :012 > the_grinch
 => 
#<Movie:0x00000001190b5418                                                            
 id: 2,                                                                               
 title: "The Grinch",                                                                 
 category: "comedy",                                                                  
 created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,                          
 updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,                          
 movie_length: 1.45>                                                                  
3.0.0 :013 > Movie.all
  Movie Load (0.7ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x0000000118f8ecb0                                  
  id: 3,                                                     
  title: "Mr Deeds",                                         
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  movie_length: nil>,                                        
 #<Movie:0x0000000118f8ebe8                                  
  id: 4,                                                     
  title: "Napolean Dynamite",                                
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118f8eb20
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x0000000118f8ea30
  id: 1,
  title: "Mean Girls",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
  movie_length: 1.37>,
 #<Movie:0x0000000118f8e968
  id: 2,
  title: "The Grinch",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>] 
3.0.0 :014 > mr_deeds = Movie.find 3
  Movie Load (0.5ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]                                            
 =>                                                                     
#<Movie:0x000000011914c7f0                                              
...                                                                     
3.0.0 :015 > mr_deeds
 => 
#<Movie:0x000000011914c7f0                                              
 id: 3,                                                                 
 title: "Mr Deeds",                                                     
 category: "comedy",                                                    
 created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,            
 updated_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,            
 movie_length: nil>                                                     
3.0.0 :016 > mr_deeds.update movie_length:1.36
  TRANSACTION (0.4ms)  BEGIN
  Movie Update (0.7ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:10:33.803742"], ["movie_length", 1.36], ["id", 3]]                                                                    
  TRANSACTION (0.3ms)  COMMIT                                                         
 => true                                                                              
3.0.0 :017 > mr_deeds
 => 
#<Movie:0x000000011914c7f0                                                            
 id: 3,                                                                               
 title: "Mr Deeds",                                                                   
 category: "comedy",                                                                  
 created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,                          
 updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,                          
 movie_length: 1.36>                                                                  
3.0.0 :018 > Movie.all
  Movie Load (0.4ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x0000000148579880                                  
  id: 4,                                                     
  title: "Napolean Dynamite",                                
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  movie_length: nil>,                                        
 #<Movie:0x00000001485796f0                                  
  id: 5,                                                     
  title: "Big Daddy",                                        
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  movie_length: nil>,
 #<Movie:0x00000001485795b0
  id: 1,
  title: "Mean Girls",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
  movie_length: 1.37>,
 #<Movie:0x0000000148579498
  id: 2,
  title: "The Grinch",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>,
 #<Movie:0x00000001485793a8
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,
  movie_length: 1.36>] 
3.0.0 :019 > nap_dyn = Movie.find 4
  Movie Load (0.5ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 4], ["LIMIT", 1]]                                                          
 =>                                                                                   
#<Movie:0x0000000119325478                                                            
...                                                                                   
3.0.0 :020 > nap_dyn.update movie_length:1.22
  TRANSACTION (0.5ms)  BEGIN
  Movie Update (0.6ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:12:19.706580"], ["movie_length", 1.22], ["id", 4]]                                                                    
  TRANSACTION (5.6ms)  COMMIT                                                         
 => true                                                                              
3.0.0 :021 > Movie.all
  Movie Load (1.0ms)  SELECT "movies".* FROM "movies"
 =>                                                                                   
[#<Movie:0x00000001481c3948                                                           
  id: 5,                                                                              
  title: "Big Daddy",                                                                 
  category: "comedy",                                                                 
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,                         
  updated_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,                         
  movie_length: nil>,                                        
 #<Movie:0x00000001481c36c8                                  
  id: 1,                                                     
  title: "Mean Girls",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
  movie_length: 1.37>,
 #<Movie:0x00000001481c3498
  id: 2,
  title: "The Grinch",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>,
 #<Movie:0x00000001481c30b0
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,
  movie_length: 1.36>,
 #<Movie:0x00000001481c2930
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:12:19.706580000 UTC +00:00,
  movie_length: 1.22>] 
3.0.0 :022 > big_daddy = Movie.find 5
  Movie Load (0.5ms)  SELECT "movies".* FROM "movies" WHERE "movies"."id" = $1 LIMIT $2  [["id", 5], ["LIMIT", 1]]                                             
 =>                                                                      
#<Movie:0x0000000148651a00                                               
...                                                                      
3.0.0 :023 > big_daddy.update movie_length:1.34
  TRANSACTION (0.5ms)  BEGIN
  Movie Update (0.7ms)  UPDATE "movies" SET "updated_at" = $1, "movie_length" = $2 WHERE "movies"."id" = $3  [["updated_at", "2022-12-06 19:14:42.997061"], ["movie_length", 1.34], ["id", 5]]                                                                    
  TRANSACTION (4.9ms)  COMMIT                                                         
 => true                                                                              
3.0.0 :024 > Movie.all
  Movie Load (0.4ms)  SELECT "movies".* FROM "movies"
 =>                                                                                   
[#<Movie:0x000000010e8e6390                                                           
  id: 1,                                                                              
  title: "Mean Girls",                                                                
  category: "comedy",                                                                 
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,                         
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,                         
  movie_length: 1.37>,                                       
 #<Movie:0x000000010e8e6278                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  category: "comedy",                                        
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>,
 #<Movie:0x000000010e8e61b0
  id: 3,
  title: "Mr Deeds",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,
  movie_length: 1.36>,
 #<Movie:0x000000010e8e60c0
  id: 4,
  title: "Napolean Dynamite",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:12:19.706580000 UTC +00:00,
  movie_length: 1.22>,
 #<Movie:0x000000010e8e5ff8
  id: 5,
  title: "Big Daddy",
  category: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:14:42.997061000 UTC +00:00,
  movie_length: 1.34>] 
3.0.0 :025 > exit 
➜  favorite_movie git:(main) ✗ rails generate migration change_category_column_name_to_genre
      invoke  active_record
      create    db/migrate/20221206192520_change_category_column_name_to_genre.rb
➜  favorite_movie git:(main) ✗ rails db:migrate
== 20221206192520 ChangeCategoryColumnNameToGenre: migrating ==================
-- rename_column(:movies, :category, :genre)
   -> 0.0083s
== 20221206192520 ChangeCategoryColumnNameToGenre: migrated (0.0084s) =========

➜  favorite_movie git:(main) ✗ rails c
mLoading development environment (Rails 7.0.4)
3.0.0 :001 > Movie.all
  Movie Load (4.3ms)  SELECT "movies".* FROM "movies"
 =>                                                          
[#<Movie:0x00000001335fd4d8                                  
  id: 1,                                                     
  title: "Mean Girls",                                       
  genre: "comedy",                                           
  created_at: Tue, 06 Dec 2022 18:47:13.468534000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:06:35.381757000 UTC +00:00,
  movie_length: 1.37>,                                       
 #<Movie:0x0000000150f0bfa8                                  
  id: 2,                                                     
  title: "The Grinch",                                       
  genre: "comedy",                                           
  created_at: Tue, 06 Dec 2022 18:48:48.369836000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:08:54.392540000 UTC +00:00,
  movie_length: 1.45>,
 #<Movie:0x0000000150f0bee0
  id: 3,
  title: "Mr Deeds",
  genre: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:33.821973000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:10:33.803742000 UTC +00:00,
  movie_length: 1.36>,
 #<Movie:0x0000000150f0be18
  id: 4,
  title: "Napolean Dynamite",
  genre: "comedy",
  created_at: Tue, 06 Dec 2022 18:49:53.902250000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:12:19.706580000 UTC +00:00,
  movie_length: 1.22>,
 #<Movie:0x0000000150f0bd50
  id: 5,
  title: "Big Daddy",
  genre: "comedy",
  created_at: Tue, 06 Dec 2022 18:50:12.441732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 19:14:42.997061000 UTC +00:00,
  movie_length: 1.34>] 
3.0.0 :002 > exit
➜  favorite_movie git:(main) ✗ git branch   
➜  favorite_movie git:(main) ✗ git checkout main
error: pathspec 'main' did not match any file(s) known to git
➜  favorite_movie git:(main) ✗ cd ..                       
➜  rails-challenges git:(migrations-tt-zp) ✗ git status      
On branch migrations-tt-zp
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	favorite_movie/
	migration-tabi-zeke.md

nothing added to commit but untracked files present (use "git add" to track)
➜  rails-challenges git:(migrations-tt-zp) ✗ git add .
error: 'favorite_movie/' does not have a commit checked out
fatal: adding files failed
➜  rails-challenges git:(migrations-tt-zp) ✗ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
➜  rails-challenges git:(main) ✗ git branch -D migrations-tt-zp 
Deleted branch migrations-tt-zp (was 364b0ca).
➜  rails-challenges git:(main) ✗ git checkout -b migrations-tt-zp
Switched to a new branch 'migrations-tt-zp'
➜  rails-challenges git:(migrations-tt-zp) ✗ touch migration-tabi-zeke
➜  rails-challenges git:(migrations-tt-zp) ✗ code .
➜  rails-challenges git:(migrations-tt-zp) ✗ 
