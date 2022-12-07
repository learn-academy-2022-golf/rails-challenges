# Validations Challenges
# Create a Rails application called company_contacts. The app will have a PostgreSQL database.

rails new company_contacts -d postgresql -T
cd company_contacts
rails db:create

Created database 'company_contacts_development'
Created database 'company_contacts_test'

# Generate a model called Account that has a username, a password, and an email.

rails generate model Account username:string password:string email:string

invoke  active_record
      create    db/migrate/20221207194747_create_accounts.rb
      create    app/models/account.rb

# All stories should have accompanying model specs.
# Developer Stories

# As a developer, I need username, password, and email to be required.

 $ bundle add rspec-rails

    long output

 $ rails generate rspec:install

create  .rspec
      create  spec
      create  spec/spec_helper.rb
      create  spec/rails_helper.rb

    rails db:migrate we need to migrate earlier model generation

    -- create_table(:accounts)
   -> 0.0107s
== 20221207194747 CreateAccounts: migrated (0.0108s) ==========================


# As a developer, I need every username to be at least 5 characters long.


# As a developer, I need each username to be unique.
# As a developer, I need each password to be at least 6 characters long.
# As a developer, I need each password to be unique.
# As a developer, I want my Account model to have many associated Addresses.
# As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
# As a developer, I want to validate the presence of all fields on Address.


## Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.