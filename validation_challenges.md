# Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.
Generate a model called Account that has a username, a password, and an email.
All stories should have accompanying model specs.
# Developer Stories

As a developer, I need username, password, and email to be required.
```ruby
Finished in 0.03567 seconds (files took 0.7982 seconds to load)
1 example, 0 failures
```
As a developer, I need every username to be at least 5 characters long.
```ruby
Finished in 0.03235 seconds (files took 0.70178 seconds to load)
2 examples, 0 failures
```
As a developer, I need each username to be unique.
```ruby
Finished in 0.03828 seconds (files took 0.66207 seconds to load)
3 examples, 0 failures
```
As a developer, I need each password to be at least 6 characters long.
As a developer, I need each password to be unique.
```ruby
Finished in 0.03874 seconds (files took 0.6313 seconds to load)
5 examples, 0 failures
```
As a developer, I want my Account model to have many associated Addresses.
As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
As a developer, I want to validate the presence of all fields on Address.


# Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.