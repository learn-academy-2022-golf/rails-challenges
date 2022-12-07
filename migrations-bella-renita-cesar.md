Create a new rails application and database
Create a model for owner

An owner has a name and address, and can have multiple credit cards
    $ rails generate model Owner name:string address:string 

    class AddUserIdColumn < ActiveRecord::Migration[7.0]
  def change
    add_column :credit_cards, :user_id, :integer
  end
end

Create a model for credit card
A credit card has a number, an expiration date, and an owner
Challenges
    $ rails generate model CreditCard number:bigint expiration_date:date

Create three owners and save them in the database
    $ User.create name:"Kaya", address:"123 Sesame St"
    $ User.create name:"Chase", address:"777 Lucky St"
    $ User.create name:"Bepop", address:"456 Meow St"

Create a credit card in the database for each owner
    
    $ kaya = User.first
    $ kaya.credit_cards.create number:123456789, expiration_date:Date.today

    $ chase = User.find 2
    $ chase.credit_cards.create number:987654321, expiration_date:Date.today + 5

    $ bepop = User.find 3
    $ bepop.credit_cards.create number:3458769536, expiration_date:Date.tomorrow


Add two more credit cards to one of the owners
    $ bepop.credit_cards.create number:332126890, expiration_date:Date.today
    $ chase.credit_cards.create number:555666777888, expiration_date:Date.today + 50

Stretch Challenge
Add a credit limit to each card
    class AddCreditLimit < ActiveRecord::Migration[7.0]
  def change
    add_column :credit_cards, :credit_limit, :integer
  end
end

    $ CreditCard.all.map{|card|card.update credit_limit:10000}
    CreditCard Load (0.6ms)  SELECT "credit_cards".* FROM "credit_cards"
    TRANSACTION (0.2ms)  BEGIN                                                                                 
    CreditCard Update (6.4ms)  UPDATE "credit_cards" SET "updated_at" = $1, "credit_limit" = $2 WHERE "credit_cards"."id" = $3  [["updated_at", "2022-12-06 23:39:41.691825"], ["credit_limit", 10000], ["id", 1]]          
    TRANSACTION (1.0ms)  COMMIT                                                                                
    TRANSACTION (0.1ms)  BEGIN                                                                                 
    CreditCard Update (0.3ms)  UPDATE "credit_cards" SET "updated_at" = $1, "credit_limit" = $2 WHERE "credit_cards"."id" = $3  [["updated_at", "2022-12-06 23:39:41.704168"], ["credit_limit", 10000], ["id", 2]]          
    TRANSACTION (0.2ms)  COMMIT                                                                                
    TRANSACTION (0.1ms)  BEGIN                                                                                 
    CreditCard Update (0.2ms)  UPDATE "credit_cards" SET "updated_at" = $1, "credit_limit" = $2 WHERE "credit_cards"."id" = $3  [["updated_at", "2022-12-06 23:39:41.706135"], ["credit_limit", 10000], ["id", 3]]
    TRANSACTION (0.2ms)  COMMIT
    TRANSACTION (0.1ms)  BEGIN
    CreditCard Update (0.2ms)  UPDATE "credit_cards" SET "updated_at" = $1, "credit_limit" = $2 WHERE "credit_cards"."id" = $3  [["updated_at", "2022-12-06 23:39:41.707575"], ["credit_limit", 10000], ["id", 4]]
    TRANSACTION (0.4ms)  COMMIT
    TRANSACTION (0.1ms)  BEGIN
    CreditCard Update (0.2ms)  UPDATE "credit_cards" SET "updated_at" = $1, "credit_limit" = $2 WHERE "credit_cards"."id" = $3  [["updated_at", "2022-12-06 23:39:41.709250"], ["credit_limit", 10000], ["id", 5]]
    TRANSACTION (0.2ms)  COMMIT
    => [true, true, true, true, true] 


Find the total credit extended to the owner with multiple credit cards
    $ CreditCard.where(user_id:3).sum(:credit_limit)
   
    CreditCard Sum (0.9ms)  SELECT SUM("credit_cards"."credit_limit") FROM "credit_cards" WHERE "credit_cards"."user_id" = $1  [["user_id", 3]]                                                                       
    => 20000  