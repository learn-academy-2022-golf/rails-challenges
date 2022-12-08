Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.
Generate a model called Account that has a username, a password, and an email.
All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
end

require 'rails_helper'

RSpec.describe Account, type: :model do
  it 'is not valid without a username' do
    bob = Account.create password:"pw", email:"bob@sample.com"
    expect(bob.errors[:username]).to_not be_empty
  end
  it 'is not valid without a password' do
    bob = Account.create username:"bob", email:"bob@sample.com"
    expect(bob.errors[:password]).to_not be_empty
  end
  it 'is not valid without an email' do
    bob = Account.create username:"bob", password:"bobspw"
    expect(bob.errors[:email]).to_not be_empty
  end
end


As a developer, I need every username to be at least 5 characters long.
  it 'has a username of at least 5 characters' do
    bob = Account.create username:"bob", email:"bob@smaple.com", password:"bobspw"
    expect(bob.errors[:username]).to_not be_empty
  end

    validates :username, length: { minimum: 5 }

As a developer, I need each username to be unique.
  it 'has a username that is unique' do
    Account.create(username:"bobert", email:"bob@smaple.com", password:"bobspw")
    bob = Account.create(username:"bobert", email:"bob@smaple.com", password:"bobspw")
    expect(bob.errors[:username]).to_not be_empty
  end
  
  class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :username, uniqueness: true
end


As a developer, I need each password to be at least 6 characters long.

As a developer, I need each password to be unique.

class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :username, :password, uniqueness: true
    validates :password, length: { minimum: 6 }
end

As a developer, I want my Account model to have many associated Addresses.


As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.


As a developer, I want to validate the presence of all fields on Address.

class Address < ApplicationRecord
    validates :street_number, :street_name, :city, :state, :zip, presence: true
end

RSpec.describe Address, type: :model do
  it 'has the field street_number' do
    address1 = Address.create street_name:"Main St", city: "San Diego", state: "CA", zip:92119
    expect(address1.errors[:street_number]).to_not be_empty
  end
  it 'has the field street_name' do
    address1 = Address.create street_number:123, city: "San Diego", state: "CA", zip:92119
    expect(address1.errors[:street_name]).to_not be_empty
  end
  it 'has the field city' do
    address1 = Address.create street_number:123, street_name:"Main St.", state: "CA", zip:92119
    expect(address1.errors[:city]).to_not be_empty
  end
  it 'has the field state' do
    address1 = Address.create street_number:123, street_name:"Main St.", city: "San Diego",  zip:92119
    expect(address1.errors[:state]).to_not be_empty
  end
  it 'has the field zip' do
    address1 = Address.create street_number:123, street_name:"Main St.", city: "San Diego", state: "CA"
    expect(address1.errors[:zip]).to_not be_empty
  end
end

Stretch Challenges

As a developer, I need each Account password to have at least one number.



HINT: Read about custom validations in the Active Record validation docs.



As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.



As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.