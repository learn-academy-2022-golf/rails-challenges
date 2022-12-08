Active Record Validations and Model Specs Challenge

Validations Challenges

Create a Rails application called company_contacts. The app will have a PostgreSQL database.
$ rails new validations -d postgresql -T
$ cd validations
$ rails db:create
$ bundle add rspec-rails
$ rails g rspec:install

******************************************************************
Generate a model called Account that has a username, a password, and an email.
$ rails g model Account user_name:string password:string email:string
$ rails db:migrate

******************************************************************
All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.
RSpec.describe Account, type: :model do
  it 'throws an error if there is no user_name' do
  account = Account.create user_name:nil
  p account.errors[:user_name] 
  expect(account.errors[:user_name]).to_not be_empty 
end
  it 'throws an error if there is no password' do
  account = Account.create password:nil
  p account.errors[:password] 
  expect(account.errors[:password]).to_not be_empty 
  end
  it 'throws an error if there is no email' do
    account = Account.create email:nil
    p account.errors[:email] 
    expect(account.errors[:email]).to_not be_empty
  end
end

Validate Tests:

class Account < ApplicationRecord
    validates :user_name, :password, :email, presence: true
end

➜  validations git:(main) ✗ rspec spec/models/account_spec.rb
["can't be blank"]
.["can't be blank"]
.["can't be blank"]
.
Finished in 0.03563 seconds (files took 0.90486 seconds to load)
3 examples, 0 failures

******************************************************************
As a developer, I need every username to be at least 5 characters long.

  it 'throws and error if the user_name is less than 5 characters' do
    account = Account.create user_name:"mike" 
    p account.errors[:user_name] 
    expect(account.errors[:user_name]).to_not be_empty
  end

class Account < ApplicationRecord
    validates :user_name, :password, :email, presence: true
    validates :user_name, length: { minimum: 5 }
end

➜  validations git:(main) ✗ rspec spec/models/account_spec.rb
["can't be blank", "is too short (minimum is 5 characters)"]
.["can't be blank"]
.["can't be blank"]
.["is too short (minimum is 5 characters)"]
.
Finished in 0.04235 seconds (files took 0.83656 seconds to load)
4 examples, 0 failures

******************************************************************
As a developer, I need each username to be unique.

  it 'throws and error if the user_name is not unique' do
    Account.create user_name: 'Benjamin', password: '100', email: 'Bentastic@100.com' 
    account = Account.create user_name: 'Benjamin', password: '100', email: 'Bentastic@100.com'
    p account.errors[:user_name] 
    expect(account.errors[:user_name]).to_not be_empty
  end

class Account < ApplicationRecord
    validates :user_name, :password, :email, presence: true
    validates :user_name, length: { minimum: 5 }
    validates :user_name, uniqueness: true
end

➜  validations git:(main) ✗ rspec spec/models/account_spec.rb
["can't be blank", "is too short (minimum is 5 characters)"]
.["can't be blank"]
.["can't be blank"]
.["is too short (minimum is 5 characters)"]
.["has already been taken"]
.
Finished in 0.04293 seconds (files took 0.93038 seconds to load)
5 examples, 0 failures

******************************************************************
As a developer, I need each password to be at least 6 characters long.
  it 'throws and error if the password is less than 6 characters' do
    account = Account.create password: 'mikes'
    p account.errors[:password] 
    expect(account.errors[:password]).to_not be_empty
  end
class Account < ApplicationRecord
    validates :user_name, :password, :email, presence: true
    validates :user_name, length: { minimum: 5 }
    validates :user_name, uniqueness: true
    validates :password, length: { minimum: 6 }
end



As a developer, I need each password to be unique.
As a developer, I want my Account model to have many associated Addresses.
As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
As a developer, I want to validate the presence of all fields on Address.
Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.