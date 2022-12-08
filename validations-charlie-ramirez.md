Validations Challenges

Create a Rails application called company_contacts. The app will have a PostgreSQL database.
-$ rails new company_contacts -d postgresql -T

Generate a model called Account that has a username, a password, and an email.
-$ rails g model Account username:string password:string email:string

```ruby
class CreateAccounts < ActiveRecord::Migration[7.0]
  def change
    create_table :accounts do |t|
      t.string :username
      t.string :password
      t.string :email

      t.timestamps
    end
  end
end
```

All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.

```ruby
it 'is not valid without name, password and email' do
    blank = Account.create
    expect(blank.errors[:username]).to_not be_empty
    expect(blank.errors[:password]).to_not be_empty
    expect(blank.errors[:email]).to_not be_empty
  end
```

As a developer, I need every username to be at least 5 characters long.
```ruby
it 'needs every username to be at least 5 char' do
    blank = Account.create username: 'sup'
    expect(blank.errors[:username]).to_not be_empty 
  end
```
As a developer, I need each username to be unique.
```ruby
 it 'needs every username to be unique' do 
    Account.create(username: 'sup', password:'super1', email:'1')
    blank = Account.create(username: 'sup', password:'super1', email:'1')
    expect(blank.errors[:username]).to_not be_empty
  end
```
As a developer, I need each password to be at least 6 characters long.
```ruby
 it 'password needs to be at least 6 char' do
  blank = Account.create(username: 'super1', password:'sup', email:'1')
    expect(blank.errors[:password]).to_not be_empty 
 end
```
As a developer, I need each password to be unique.
```ruby
 it 'needs every password to be unique' do 
  Account.create(username: 'super1', password:'super1', email:'1')
  blank = Account.create(username: 'super1', password:'super1', email:'1')
  expect(blank.errors[:password]).to_not be_empty
end
```
As a developer, I want my Account model to have many associated Addresses.
```ruby

```


As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
```ruby
 it 'validates the presence of all attributes' do
    blank = Address.create
  expect(blank.errors[:street_number]).to_not be_empty
  expect(blank.errors[:street_name]).to_not be_empty
  expect(blank.errors[:city]).to_not be_empty
  expect(blank.errors[:state]).to_not be_empty
  expect(blank.errors[:zip]).to_not be_empty
  expect(blank.errors[:user_id]).to_not be_empty
  end
```


As a developer, I want to validate the presence of all fields on Address.
```ruby

```

Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.


class Account < ApplicationRecord
    has_many:address
    validates :username, :password, :email, presence: true 
     validates :username, length: { minimum: 5}
     validates :username, :password, uniqueness: true
     validates :password, length: { minimum: 6}
     validates :password, inclusion: {in:%w(Integer)}
    end

    class Address < ApplicationRecord
    belongs_to :account
    validates :street_number,:user_id, :zip, :state, :city, :street_name, presence:true
    validates :street_name, :street_number, :zip, uniqueness:true
end