TESTS: 

account_spec.rb
RSpec.describe Account, type: :model do
  it 'throws error if there is no username' do
    test = Account.create username: nil, password: nil, email: nil
    expect(test.errors[:username]).to_not be_empty
    expect(test.errors[:password]).to_not be_empty
    expect(test.errors[:email]).to_not be_empty
  end
  it 'throws error if username is less than 5 characters long' do
    test = Account.create username: 'oof', password: nil, email: nil
    expect(test.errors[:username]).to_not be_empty
  end
  it 'throws error if username is not unique' do
    Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    test = Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    expect(test.errors[:username]).to_not be_empty
  end
  it 'throws error if password is less than 6 chars long' do
    test = Account.create username: 'Stinkies', password: 'stank', email: 'nope'
    expect(test.errors[:password]).to_not be_empty
  end
  it 'throws error if password is not unique' do
    Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    test = Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    expect(test.errors[:password]).to_not be_empty
  end
end

address_spec.rb
RSpec.describe Account, type: :model do
  it 'throws error if there is no username' do
    test = Account.create username: nil, password: nil, email: nil
    expect(test.errors[:username]).to_not be_empty
    expect(test.errors[:password]).to_not be_empty
    expect(test.errors[:email]).to_not be_empty
  end
  it 'throws error if username is less than 5 characters long' do
    test = Account.create username: 'oof', password: nil, email: nil
    expect(test.errors[:username]).to_not be_empty
  end
  it 'throws error if username is not unique' do
    Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    test = Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    expect(test.errors[:username]).to_not be_empty
  end
  it 'throws error if password is less than 6 chars long' do
    test = Account.create username: 'Stinkies', password: 'stank', email: 'nope'
    expect(test.errors[:password]).to_not be_empty
  end
  it 'throws error if password is not unique' do
    Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    test = Account.create username: 'Stinkies', password: 'stinkies', email: 'nope'
    expect(test.errors[:password]).to_not be_empty
  end
end


VALIDATIONS:

account.rb
class Account < ApplicationRecord
    has_many :addresses
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :username, :password, uniqueness: true
    validates :password, length: { minimum: 6 }
end

address.rb
class Address < ApplicationRecord
    belongs_to :account
    validates :street_number, :street_name, :city, :state, :zip, presence: true
end