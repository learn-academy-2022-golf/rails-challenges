learnacademy@LEARNs-MacBook-Air desktop % rails new rolidex_app -d postgresql -T
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
Initialized empty Git repository in /Users/learnacademy/Desktop/rolidex_app/.git/
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
Resolving dependencies.........................
Using rake 13.0.6
Using concurrent-ruby 1.1.10
Using minitest 5.16.3
Using crass 1.0.6
Using rack 2.2.4
Using nio4r 2.5.8
Using websocket-extensions 0.1.5
Using builder 3.2.4
Using marcel 1.0.2
Using timeout 0.3.1
Using bindex 0.8.1
Using mini_mime 1.1.2
Using bundler 2.2.3
Using io-console 0.5.11
Using method_source 1.0.0
Using thor 1.2.1
Using zeitwerk 2.6.6
Using erubi 1.11.0
Using i18n 1.12.0
Using tzinfo 2.0.5
Using rack-test 2.0.2
Using sprockets 4.1.1
Using puma 5.6.5
Using websocket-driver 0.7.5
Using net-protocol 0.2.0
Using msgpack 1.6.0
Fetching racc 1.6.1
Fetching pg 1.4.5
Using activesupport 7.0.4
Using net-pop 0.1.2
Using net-smtp 0.3.3
Using net-imap 0.3.1
Using reline 0.3.1
Using globalid 1.0.0
Using activemodel 7.0.4
Using mail 2.8.0
Fetching bootsnap 1.15.0
Using activejob 7.0.4
Using activerecord 7.0.4
Using irb 1.5.1
Fetching debug 1.7.0
Installing bootsnap 1.15.0 with native extensions
Installing racc 1.6.1 with native extensions
Installing debug 1.7.0 with native extensions
Installing pg 1.4.5 with native extensions
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.

    current directory: /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/racc-1.6.1/ext/racc/cparse
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/bin/ruby -I
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0 -r ./siteconf20221205-4938-6ionv4.rb extconf.rb
checking for rb_block_call()... *** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of necessary
libraries and/or headers.  Check the mkmf.log file for more details.  You may
need configuration options.

Provided configuration options:
	--with-opt-dir
	--without-opt-dir
	--with-opt-include
	--without-opt-include=${opt-dir}/include
	--with-opt-lib
	--without-opt-lib=${opt-dir}/lib
	--with-make-prog
	--without-make-prog
	--srcdir=.
	--curdir
	--ruby=/Users/learnacademy/.rvm/rubies/ruby-3.0.0/bin/$(RUBY_BASE_NAME)
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:471:in `try_do': The compiler failed to
generate an executable file. (RuntimeError)
You have to install development tools first.
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:564:in `try_link0'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:582:in `try_link'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:794:in `try_func'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:1083:in `block in have_func'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:971:in `block in checking_for'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:361:in `block (2 levels) in postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:331:in `open'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:361:in `block in postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:331:in `open'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:357:in `postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:970:in `checking_for'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:1082:in `have_func'
	from extconf.rb:6:in `<main>'

To see why this extension failed to compile, please check the mkmf.log which can be found here:

  /Users/learnacademy/.rvm/gems/ruby-3.0.0/extensions/x86_64-darwin-21/3.0.0/racc-1.6.1/mkmf.log

extconf failed, exit code 1

Gem files will remain installed in /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/racc-1.6.1 for inspection.
Results logged to
/Users/learnacademy/.rvm/gems/ruby-3.0.0/extensions/x86_64-darwin-21/3.0.0/racc-1.6.1/gem_make.out

An error occurred while installing racc (1.6.1), and Bundler cannot continue.
Make sure that `gem install racc -v '1.6.1' --source 'https://rubygems.org/'` succeeds before bundling.

In Gemfile:
  rails was resolved to 7.0.4, which depends on
    actioncable was resolved to 7.0.4, which depends on
      actionpack was resolved to 7.0.4, which depends on
        actionview was resolved to 7.0.4, which depends on
          rails-dom-testing was resolved to 2.0.3, which depends on
            nokogiri was resolved to 1.13.9, which depends on
              racc
         run  bundle binstubs bundler
Resolving dependencies...
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
learnacademy@LEARNs-MacBook-Air desktop % cd rolidex_app 
learnacademy@LEARNs-MacBook-Air rolidex_app % gem install racc -v '1.6.1' --source 'https://rubygems.org/'
Building native extensions. This could take a while...
ERROR:  Error installing racc:
	ERROR: Failed to build gem native extension.

    current directory: /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/racc-1.6.1/ext/racc/cparse
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/bin/ruby -I /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0 -r ./siteconf20221205-5056-ev3g8s.rb extconf.rb
checking for rb_block_call()... *** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of necessary
libraries and/or headers.  Check the mkmf.log file for more details.  You may
need configuration options.

Provided configuration options:
	--with-opt-dir
	--without-opt-dir
	--with-opt-include
	--without-opt-include=${opt-dir}/include
	--with-opt-lib
	--without-opt-lib=${opt-dir}/lib
	--with-make-prog
	--without-make-prog
	--srcdir=.
	--curdir
	--ruby=/Users/learnacademy/.rvm/rubies/ruby-3.0.0/bin/$(RUBY_BASE_NAME)
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:471:in `try_do': The compiler failed to generate an executable file. (RuntimeError)
You have to install development tools first.
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:564:in `try_link0'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:582:in `try_link'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:794:in `try_func'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:1083:in `block in have_func'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:971:in `block in checking_for'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:361:in `block (2 levels) in postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:331:in `open'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:361:in `block in postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:331:in `open'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:357:in `postpone'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:970:in `checking_for'
	from /Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/mkmf.rb:1082:in `have_func'
	from extconf.rb:6:in `<main>'

To see why this extension failed to compile, please check the mkmf.log which can be found here:

  /Users/learnacademy/.rvm/gems/ruby-3.0.0/extensions/x86_64-darwin-21/3.0.0/racc-1.6.1/mkmf.log

extconf failed, exit code 1

Gem files will remain installed in /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/racc-1.6.1 for inspection.
Results logged to /Users/learnacademy/.rvm/gems/ruby-3.0.0/extensions/x86_64-darwin-21/3.0.0/racc-1.6.1/gem_make.out
learnacademy@LEARNs-MacBook-Air rolidex_app % rails db:create
Created database 'rolidex_app_development'
Created database 'rolidex_app_test'
learnacademy@LEARNs-MacBook-Air rolidex_app % rails server
=> Booting Puma
=> Rails 7.0.4 application starting in development 
=> Run `bin/rails server --help` for more startup options
Puma starting in single mode...
* Puma version: 5.6.5 (ruby 3.0.0-p0) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*          PID: 5084
* Listening on http://127.0.0.1:3000
* Listening on http://[::1]:3000
Use Ctrl-C to stop
Started GET "/" for 127.0.0.1 at 2022-12-05 17:00:15 -0500
Processing by Rails::WelcomeController#index as HTML
  Rendering /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb
  Rendered /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb (Duration: 12.6ms | Allocations: 740)
Completed 200 OK in 82ms (Views: 37.1ms | ActiveRecord: 0.0ms | Allocations: 7115)


rails generate model Rolidex first_name:string last_name:string phone_number:string
^C- Gracefully stopping, waiting for requests to finish
=== puma shutdown: 2022-12-05 17:07:53 -0500 ===
- Goodbye!
Exiting
learnacademy@LEARNs-MacBook-Air rolidex_app % rails generate model Rolidex first_name:string last_name:string phone_number:string
      invoke  active_record
      create    db/migrate/20221205220832_create_rolidexes.rb
      create    app/models/rolidex.rb
learnacademy@LEARNs-MacBook-Air rolidex_app % rails db:migrate
== 20221205220832 CreateRolidexes: migrating ==================================
-- create_table(:rolidexes)
   -> 0.0789s
== 20221205220832 CreateRolidexes: migrated (0.0791s) =========================

learnacademy@LEARNs-MacBook-Air rolidex_app % rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Rolidex.create first_name: "Kent", last_name: "Stone", phone_number: "974-635-098"
  TRANSACTION (0.2ms)  BEGIN
  Rolidex Create (1.5ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Kent"], ["last_name", "Stone"], ["phone_number", "974-635-098"], ["created_at", "2022-12-05 22:19:03.725514"], ["updated_at", "2022-12-05 22:19:03.725514"]]                                                                                                     
  TRANSACTION (25.6ms)  COMMIT                                                                                
 =>                                                                                                           
#<Rolidex:0x00007fa7af1e0240                                                                                  
 id: 1,                                                                                                       
 first_name: "Kent",                                                                                          
 last_name: "Stone",                                                                                          
 phone_number: "974-635-098",                                                                                 
 created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,                                                  
 updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>                                                  
3.0.0 :002 >  Rolidex.create first_name: "DeAnna", last_name: "Stone", phone_number: "405-579-0606"
  TRANSACTION (0.2ms)  BEGIN
  Rolidex Create (0.6ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "DeAnna"], ["last_name", "Stone"], ["phone_number", "405-579-0606"], ["created_at", "2022-12-05 22:23:10.774890"], ["updated_at", "2022-12-05 22:23:10.774890"]]                                                                                                  
  TRANSACTION (1.1ms)  COMMIT                                                                                 
 =>                                                                                                           
#<Rolidex:0x00007fa7ace5c148                                                                                  
 id: 2,                                                                                                       
 first_name: "DeAnna",                                                                                        
 last_name: "Stone",                                                                                          
 phone_number: "405-579-0606",                                                                                
 created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,                                                  
 updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>                                                  
3.0.0 :003 > Rolidex.create first_name: "Ryan", last_name: "Stone", phone_number: "405-598-8602"
  TRANSACTION (5.6ms)  BEGIN
  Rolidex Create (0.7ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Ryan"], ["last_name", "Stone"], ["phone_number", "405-598-8602"], ["created_at", "2022-12-05 22:23:49.849258"], ["updated_at", "2022-12-05 22:23:49.849258"]]
  TRANSACTION (1.2ms)  COMMIT
 => 
#<Rolidex:0x00007fa7a94c9340
 id: 3,
 first_name: "Ryan",
 last_name: "Stone",
 phone_number: "405-598-8602",
 created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00> 
3.0.0 :004 > Rolidex.create first_name: "Gaby", last_name: "Guzman", phone_number: "983-423-426"
  TRANSACTION (13.0ms)  BEGIN
  Rolidex Create (0.8ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Gaby"], ["last_name", "Guzman"], ["phone_number", "983-423-426"], ["created_at", "2022-12-05 22:24:57.547750"], ["updated_at", "2022-12-05 22:24:57.547750"]]
  TRANSACTION (0.7ms)  COMMIT
 => 
#<Rolidex:0x00007fa7a9ecd698
 id: 4,
 first_name: "Gaby",
 last_name: "Guzman",
 phone_number: "983-423-426",
 created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00> 
3.0.0 :005 > Rolidex.create first_name: "Sue", last_name: "Cantrel", phone_number: "405-273-0293"
  TRANSACTION (0.3ms)  BEGIN
  Rolidex Create (0.6ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Sue"], ["last_name", "Cantrel"], ["phone_number", "405-273-0293"], ["created_at", "2022-12-05 22:25:38.715870"], ["updated_at", "2022-12-05 22:25:38.715870"]]
  TRANSACTION (1.0ms)  COMMIT
 => 
#<Rolidex:0x00007fa7a946a6b0
 id: 5,
 first_name: "Sue",
 last_name: "Cantrel",
 phone_number: "405-273-0293",
 created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00> 
3.0.0 :006 > family = Family.find(1,10)
(irb):6:in `<main>': uninitialized constant Family (NameError)
3.0.0 :007 > Rolidex.all
  Rolidex Load (2.7ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7af875d80                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7af875c40                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7af875b78
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7af875ab0
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8759e8
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>] 
3.0.0 :008 > Rolidex.create first_name: "Kenny", last_name: "Stone", phone_number: "405-598-2648"
  TRANSACTION (14.7ms)  BEGIN
  Rolidex Create (0.6ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Kenny"], ["last_name", "Stone"], ["phone_number", "405-598-2648"], ["created_at", "2022-12-05 22:35:19.837632"], ["updated_at", "2022-12-05 22:35:19.837632"]]                                                                                                   
  TRANSACTION (0.9ms)  COMMIT                                                                                 
 =>                                                                                                           
#<Rolidex:0x00007fa7ad35df98                                                                                  
 id: 6,                                                                                                       
 first_name: "Kenny",                                                                                         
 last_name: "Stone",                                                                                          
 phone_number: "405-598-2648",                                                                                
 created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,                                                  
 updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>                                                  
3.0.0 :009 > Rolidex.all
  Rolidex Load (6.8ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7acf05130                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7acf05068                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7acf04fa0
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7acf04ed8
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7acf04e10
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7acf04d48
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>] 
3.0.0 :010 > Rolidex.find 3
  Rolidex Load (0.3ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 =>                                                            
#<Rolidex:0x00007fa7aced7bb8                                   
 id: 3,                                                        
 first_name: "Ryan",                                           
 last_name: "Stone",                                           
 phone_number: "405-598-8602",                                 
 created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,   
 updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>   
3.0.0 :011 > Rolidex.find 6
  Rolidex Load (0.5ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."id" = $1 LIMIT $2  [["id", 6], ["LIMIT", 1]]
 =>                                                            
#<Rolidex:0x00007fa7af85e040                                   
 id: 6,                                                        
 first_name: "Kenny",                                          
 last_name: "Stone",                                           
 phone_number: "405-598-2648",                                 
 created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,   
 updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>   
3.0.0 :012 > Rolidex.destroy
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:447:in `destroy': wrong number of arguments (given 0, expected 1) (ArgumentError)                                                     
3.0.0 :013 > Rolidex.phone = 405-598-8602
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `phone=' for Rolidex:Class (NoMethodError)                                              
3.0.0 :014 > Rolidex.find 3
  Rolidex Load (9.5ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
 =>                                                            
#<Rolidex:0x00007fa7acf56c38                                   
 id: 3,                                                        
 first_name: "Ryan",                                           
 last_name: "Stone",                                           
 phone_number: "405-598-8602",                                 
 created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,   
 updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>   
3.0.0 :015 > Rolidex.where
  Rolidex Load (0.5ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
#<ActiveRecord::QueryMethods::WhereChain:0x00007fa7acefd5e8    
 @scope=                                                       
  [#<Rolidex:0x00007fa7ad316be8                                
    id: 1,                                                     
    first_name: "Kent",                                        
    last_name: "Stone",                                        
    phone_number: "974-635-098",                               
    created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>,
   #<Rolidex:0x00007fa7ad316b20                                
    id: 2,                                                     
    first_name: "DeAnna",                                      
    last_name: "Stone",                                        
    phone_number: "405-579-0606",
    created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
   #<Rolidex:0x00007fa7ad316a58
    id: 3,
    first_name: "Ryan",
    last_name: "Stone",
    phone_number: "405-598-8602",
    created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
   #<Rolidex:0x00007fa7ad316990
    id: 4,
    first_name: "Gaby",
    last_name: "Guzman",
    phone_number: "983-423-426",
    created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
   #<Rolidex:0x00007fa7ad3168a0
    id: 5,
    first_name: "Sue",
    last_name: "Cantrel",
    phone_number: "405-273-0293",
    created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
   #<Rolidex:0x00007fa7ad3167d8
    id: 6,
    first_name: "Kenny",
    last_name: "Stone",
    phone_number: "405-598-2648",
    created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
    updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>]> 
3.0.0 :016 > Rolidex.where "last_name = Stone"
  Rolidex Load (11.4ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE (last_name = Stone)
(Object doesn't support #inspect)                              
 =>                                                            
3.0.0 :017 > Rolidex.where(last_name: "Stone")
  Rolidex Load (0.6ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."last_name" = $1  [["last_name", "Stone"]]
 =>                                                            
[#<Rolidex:0x00007fa7acc561a0                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7acc560d8                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7acc56010
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7acc55f48
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>] 
3.0.0 :018 > Rolidex.create first_name: "Victoria", last_name: "Guzman", phone_number: "946-869-031"
  TRANSACTION (14.0ms)  BEGIN
  Rolidex Create (0.5ms)  INSERT INTO "rolidexes" ("first_name", "last_name", "phone_number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Victoria"], ["last_name", "Guzman"], ["phone_number", "946-869-031"], ["created_at", "2022-12-05 22:54:04.026970"], ["updated_at", "2022-12-05 22:54:04.026970"]]
  TRANSACTION (0.6ms)  COMMIT
 => 
#<Rolidex:0x00007fa7af092708
 id: 7,
 first_name: "Victoria",
 last_name: "Guzman",
 phone_number: "946-869-031",
 created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
 updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00> 
3.0.0 :019 > Rolidex.all
  Rolidex Load (11.9ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7a9670fb8                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7a9670ef0                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7a9670e28
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7a9670d60
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7a9670c98
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7a9670bd0
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>,
 #<Rolidex:0x00007fa7a9670b08
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :020 > Rolidex.where (last_name: "Guzman")
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/irb-1.5.1/lib/irb/workspace.rb:119:in `eval': (irb):20: syntax error, unexpected label, expecting ')' (SyntaxError)
Rolidex.where (last_name: "Guzman")                            
               ^~~~~~~~~~                                      
(irb):20: syntax error, unexpected ')', expecting end-of-input 
...dex.where (last_name: "Guzman")                             
...                              ^                             
3.0.0 :021 > Rolidex.where(last_name: "Guzman")
  Rolidex Load (17.5ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."last_name" = $1  [["last_name", "Guzman"]]
 =>                                                            
[#<Rolidex:0x00007fa7ace45358                                  
  id: 4,                                                       
  first_name: "Gaby",                                          
  last_name: "Guzman",                                         
  phone_number: "983-423-426",                                 
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7ace45290
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :022 > bella = Rolidex.find 6
  Rolidex Load (0.4ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."id" = $1 LIMIT $2  [["id", 6], ["LIMIT", 1]]
 =>                                                                    
#<Rolidex:0x00007fa7ace8f0e8                                           
...                                                                    
3.0.0 :023 > bella.last_name ="Guzman"
 => "Guzman" 
3.0.0 :024 > rolidex.all
(irb):24:in `<main>': undefined local variable or method `rolidex' for main:Object (NameError)
3.0.0 :025 > Rolidex.all
  Rolidex Load (1.2ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                                           
[#<Rolidex:0x00007fa7af0ca428                                                 
  id: 1,                                                                      
  first_name: "Kent",                                                         
  last_name: "Stone",                                                         
  phone_number: "974-635-098",                                                
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,                 
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>,                
 #<Rolidex:0x00007fa7af0ca360                                                 
  id: 2,                                                                      
  first_name: "DeAnna",                                                       
  last_name: "Stone",                                                         
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0ca298
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0ca1d0
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0ca108
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0ca040
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0c9f78
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :026 > Rolidex.first_name 3
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `first_name' for Rolidex:Class (NoMethodError)                                          
Did you mean?  sti_name                                        
3.0.0 :027 > Rolidex.first_name "3"
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `first_name' for Rolidex:Class (NoMethodError)                                          
Did you mean?  sti_name                                        
3.0.0 :028 > sti_name
(irb):28:in `<main>': undefined local variable or method `sti_name' for main:Object (NameError)
3.0.0 :029 > Rolidex.sti_name
 => "Rolidex" 
3.0.0 :030 > rails s
(irb):30:in `<main>': undefined local variable or method `s' for main:Object (NameError)
3.0.0 :031 > rails -e
(irb):31:in `<main>': undefined local variable or method `e' for main:Object (NameError)
3.0.0 :032 > Rolidex.all
  Rolidex Load (0.5ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7af027980                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7af0278b8                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7af0277f0
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7af027728
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7af027660
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7af027598
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>,
 #<Rolidex:0x00007fa7af027408
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :033 > Rolidex.delete_by "3"
  Rolidex Delete All (5.2ms)  DELETE FROM "rolidexes" WHERE (3)
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/connection_adapters/postgresql_adapter.rb:768:in `exec_params': PG::DatatypeMismatch: ERROR:  argument of WHERE must be type boolean, not type integer (ActiveRecord::StatementInvalid)
LINE 1: DELETE FROM "rolidexes" WHERE (3)                                     
                                       ^                                      
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/connection_adapters/postgresql_adapter.rb:768:in `exec_params': ERROR:  argument of WHERE must be type boolean, not type integer (PG::DatatypeMismatch)             
LINE 1: DELETE FROM "rolidexes" WHERE (3)                                     
                                       ^                                      
3.0.0 :034 > Rolidex.all
  Rolidex Load (24.0ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                                           
[#<Rolidex:0x00007fa7af04f368                                                 
  id: 1,                                                                      
  first_name: "Kent",                                                         
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7af04f200                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7af04f138
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7af04f070
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7af04efa8
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7af04eee0
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>,
 #<Rolidex:0x00007fa7af04ee18
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :035 > Rolidex.delete_all(last_name: "Guzman")
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation.rb:601:in `delete_all': wrong number of arguments (given 1, expected 0) (ArgumentError)                                                     
3.0.0 :036 > Rolidex.destroy_all(last_name:"Guzman") 
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/relation.rb:579:in `destroy_all': wrong number of arguments (given 1, expected 0) (ArgumentError)                                                    
3.0.0 :037 > Rolidex.all
  Rolidex Load (5.0ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7af8ec868                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7af8ec7a0                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8ec6d8
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8ec610
  id: 4,
  first_name: "Gaby",
  last_name: "Guzman",
  phone_number: "983-423-426",
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8ec548
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8ec480
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>,
 #<Rolidex:0x00007fa7af8ec3b8
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :038 > guzman = Rolidex.where last_name:"Guzman"
  Rolidex Load (21.8ms)  SELECT "rolidexes".* FROM "rolidexes" WHERE "rolidexes"."last_name" = $1  [["last_name", "Guzman"]]
 =>                                                                     
[#<Rolidex:0x00007fa7af8a1de0                                           
...                                                                     
3.0.0 :039 > guzman
 => 
[#<Rolidex:0x00007fa7af8a1de0                                           
  id: 4,                                                                
  first_name: "Gaby",                                                   
  last_name: "Guzman",                                                  
  phone_number: "983-423-426",                                          
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,           
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,          
 #<Rolidex:0x00007fa7af8a1d18                                           
  id: 7,                                                                
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :040 > guzman.delete
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:473:in `delete': wrong number of arguments (given 0, expected 1) (ArgumentError)                                             
3.0.0 :041 > guzman.destroy
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/persistence.rb:447:in `destroy': wrong number of arguments (given 0, expected 1) (ArgumentError)                                            
3.0.0 :042 > guzman.each{|value| value.destroy}
  TRANSACTION (0.9ms)  BEGIN
  Rolidex Destroy (3.5ms)  DELETE FROM "rolidexes" WHERE "rolidexes"."id" = $1  [["id", 4]]     
  TRANSACTION (0.7ms)  COMMIT                                                                   
  TRANSACTION (5.3ms)  BEGIN                                                                    
  Rolidex Destroy (0.8ms)  DELETE FROM "rolidexes" WHERE "rolidexes"."id" = $1  [["id", 7]]     
  TRANSACTION (0.6ms)  COMMIT                                                                   
 =>                                                                                             
[#<Rolidex:0x00007fa7af8a1de0                                                                   
  id: 4,                                                                                        
  first_name: "Gaby",                                                                           
  last_name: "Guzman",                                                                          
  phone_number: "983-423-426",                                                                  
  created_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00,                                   
  updated_at: Mon, 05 Dec 2022 22:24:57.547750000 UTC +00:00>,                                  
 #<Rolidex:0x00007fa7af8a1d18                                                                   
  id: 7,
  first_name: "Victoria",
  last_name: "Guzman",
  phone_number: "946-869-031",
  created_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:54:04.026970000 UTC +00:00>] 
3.0.0 :043 > Rolidex.all
  Rolidex Load (0.8ms)  SELECT "rolidexes".* FROM "rolidexes"
 =>                                                            
[#<Rolidex:0x00007fa7ad2dfe40                                  
  id: 1,                                                       
  first_name: "Kent",                                          
  last_name: "Stone",                                          
  phone_number: "974-635-098",                                 
  created_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:19:03.725514000 UTC +00:00>, 
 #<Rolidex:0x00007fa7ad2dfd78                                  
  id: 2,                                                       
  first_name: "DeAnna",                                        
  last_name: "Stone",                                          
  phone_number: "405-579-0606",                                
  created_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00,  
  updated_at: Mon, 05 Dec 2022 22:23:10.774890000 UTC +00:00>,
 #<Rolidex:0x00007fa7ad2dfcb0
  id: 3,
  first_name: "Ryan",
  last_name: "Stone",
  phone_number: "405-598-8602",
  created_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:23:49.849258000 UTC +00:00>,
 #<Rolidex:0x00007fa7ad2dfbe8
  id: 5,
  first_name: "Sue",
  last_name: "Cantrel",
  phone_number: "405-273-0293",
  created_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:25:38.715870000 UTC +00:00>,
 #<Rolidex:0x00007fa7ad2dfb20
  id: 6,
  first_name: "Kenny",
  last_name: "Stone",
  phone_number: "405-598-2648",
  created_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00,
  updated_at: Mon, 05 Dec 2022 22:35:19.837632000 UTC +00:00>] 
3.0.0 :044 > 