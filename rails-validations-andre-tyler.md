learnacademy@LEARNs-MacBook-Air company_contacts % rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Account.all
  Account Load (0.6ms)  SELECT "accounts".* FROM "accounts"
 =>                                                            
[#<Account:0x00000001305f6f50                                  
  id: 3,                                                       
  created_at: Wed, 07 Dec 2022 22:21:58.647866000 UTC +00:00,  
  updated_at: Wed, 07 Dec 2022 22:21:58.647866000 UTC +00:00,  
  TRANSACTION (0.1ms)  BEGIN
  Address Create (0.7ms)  INSERT INTO "addresses" ("street_number", "street_name", "city", "state", "zip", "created_at", "update
  TRANSACTION (0.2ms)  BEGIN
  Address Create (0.4ms)  INSERT INTO "addresses" ("street_number", "street_name", "city", "state", "zip", "created_at", "update
  TRANSACTION (0.3ms)  BEGIN
  Address Create (0.4ms)  INSERT INTO "addresses" ("street_number", "street_name", "city", "state", "zip", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5, $6, $7) RETURNING "id"  [["street_number", 51], ["street_name", "stormcrest dr."], ["city", "las vegas"], ["state", "NV"], ["zip", 89103], ["created_at", "2022-12-07 23:02:14.571366"], ["updated_at", "2022-12-07 23:02:14.571366"]]                                                                                                                       
  TRANSACTION (0.4ms)  COMMIT                                                                                                   
 =>                                                                                                                             
#<Address:0x0000000130978408                                                                                                    
 id: 3,                                                                                                                         
 street_number: 51,                                                                                                             
 street_name: "stormcrest dr.",                                                                         
learnacademy@LEARNs-MacBook-Air company_contacts % rspec spec/models/address.rb

An error occurred while loading ./spec/models/address.rb. - Did you mean?
                    rspec ./spec/models/address_spec.rb

Failure/Error: __send__(method, file)

LoadError:
  cannot load such file -- /Users/learnacademy/Desktop/company_contacts/spec/models/address.rb
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.12756 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec spec/models/address.rb

An error occurred while loading ./spec/models/address.rb. - Did you mean?
                    rspec ./spec/models/address_spec.rb

Failure/Error: __send__(method, file)

LoadError:
  cannot load such file -- /Users/learnacademy/Desktop/company_contacts/spec/models/address.rb
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.12212 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec spec/models/address.rb

An error occurred while loading ./spec/models/address.rb. - Did you mean?
                    rspec ./spec/models/address_spec.rb

Failure/Error: __send__(method, file)

LoadError:
  cannot load such file -- /Users/learnacademy/Desktop/company_contacts/spec/models/address.rb
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'              y initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
*

Pending: (Failures listed here are expected and do not affect your suite's status)

  1) Address add some examples to (or delete) /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb
     # Not yet implemented
     # ./spec/models/address_spec.rb:4


Finished in 0.00287 seconds (files took 1.95 seconds to load)
1 example, 0 failures, 1 pending

learnacademy@LEARNs-MacBook-Air company_contacts % rails c
Loading development environment (Rails 7.0.4)
  street_number: 999,                                          
  street_name: "texan Rd.",                                    
  city: "corpus christy",
  state: "TX",
  zip: 10002,
  created_at: Wed, 07 Dec 2022 23:01:30.218484000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 23:01:30.218484000 UTC +00:00>,
 #<Address:0x000000011707f860
  id: 3,
  street_number: 51,
  street_name: "stormcrest dr.",
  city: "las vegas",
  state: "NV",
  zip: 89103,
  created_at: Wed, 07 Dec 2022 23:02:14.571366000 UTC +00:00,
  updated_at: Wed, 07 Dec 2022 23:02:14.571366000 UTC +00:00>] 
3.0.0 :002 > exit
learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
F

Failures:

  1) Address is not valid without an entry
     Failure/Error: expect(tyler.errors[:street_name]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:7:in `block (2 levels) in <top (required)>'

Finished in 0.05387 seconds (files took 0.76404 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:4 # Address is not valid without an entry

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
F

Failures:

  1) Address is not valid without an entry
     Failure/Error: expect(tyler.errors[:street_name]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:7:in `block (2 levels) in <top (required)>'

Finished in 0.02626 seconds (files took 0.69073 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:4 # Address is not valid without an entry

learnacademy@LEARNs-MacBook-Air company_contacts % rspec spec/models/address.rb       

An error occurred while loading ./spec/models/address.rb. - Did you mean?
                    rspec ./spec/models/address_spec.rb

Failure/Error: __send__(method, file)

LoadError:
  cannot load such file -- /Users/learnacademy/Desktop/company_contacts/spec/models/address.rb
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00003 seconds (files took 0.10388 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
F

Failures:

  1) Address is not valid without an entry
     Failure/Error: expect(tyler.errors[:street_name]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:7:in `block (2 levels) in <top (required)>'

Finished in 0.02473 seconds (files took 0.60088 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:4 # Address is not valid without an entry

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
F

Failures:

  1) Address is not valid without a street_name
     Failure/Error: expect(tyler.errors[:street_name]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:7:in `block (2 levels) in <top (required)>'

Finished in 0.02955 seconds (files took 0.64229 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:4 # Address is not valid without a street_name

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
F

Failures:

  1) Address is not valid without a street_name
     Failure/Error: expect(tyler.errors[:street_name]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:7:in `block (2 levels) in <top (required)>'

Finished in 0.02171 seconds (files took 0.58026 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:4 # Address is not valid without a street_name

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb

An error occurred while loading ./spec/models/address_spec.rb.
Failure/Error: __send__(method, file)

SyntaxError:
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:5: syntax error, unexpected ','
  ...Address.create street_number: , street_name: "oak cliff dr."...
  ...                              ^
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:5: syntax error, unexpected ',', expecting `end'
  ..., street_name: "oak cliff dr.", city: "temecula",
  ...                              ^
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:5: syntax error, unexpected ',', expecting `end'
  ...k cliff dr.", city: "temecula",
  ...                              ^
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:6: syntax error, unexpected ',', expecting end-of-input
      state: "CA", zip: 92591
                 ^
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.09718 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
.

Finished in 0.02565 seconds (files took 0.74294 seconds to load)
1 example, 0 failures

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb

An error occurred while loading ./spec/models/address_spec.rb.
Failure/Error: __send__(method, file)

SyntaxError:
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:33: syntax error, unexpected end-of-input, expecting `end'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.09866 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb

An error occurred while loading ./spec/models/address_spec.rb.
Failure/Error: __send__(method, file)

SyntaxError:
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:33: syntax error, unexpected end-of-input, expecting `end'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.10151 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb

An error occurred while loading ./spec/models/address_spec.rb.
Failure/Error: __send__(method, file)

SyntaxError:
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:27: syntax error, unexpected `end', expecting end-of-input
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00003 seconds (files took 0.09837 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb

An error occurred while loading ./spec/models/address_spec.rb.
Failure/Error: __send__(method, file)

SyntaxError:
  /Users/learnacademy/Desktop/company_contacts/spec/models/address_spec.rb:27: syntax error, unexpected `end', expecting end-of-input
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:2117:in `load_file_handling_errors'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1617:in `block in load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `each'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/configuration.rb:1615:in `load_spec_files'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:102:in `setup'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:86:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:71:in `run'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/lib/rspec/core/runner.rb:45:in `invoke'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rspec-core-3.12.0/exe/rspec:4:in `<top (required)>'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `load'
# /Users/learnacademy/.rvm/gems/ruby-3.0.0/bin/rspec:23:in `<main>'
# 
#   Showing full backtrace because every line was filtered out.
#   See docs for RSpec::Configuration#backtrace_exclusion_patterns and
#   RSpec::Configuration#backtrace_inclusion_patterns for more information.
No examples found.


Finished in 0.00002 seconds (files took 0.09606 seconds to load)
0 examples, 0 failures, 1 error occurred outside of examples

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
.F..

Failures:

  1) Address is not valid without a street_number
     Failure/Error: expect(tyler.errors[:street_number]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/address_spec.rb:15:in `block (2 levels) in <top (required)>'

Finished in 0.03203 seconds (files took 0.65819 seconds to load)
4 examples, 1 failure

Failed examples:

rspec ./spec/models/address_spec.rb:12 # Address is not valid without a street_number

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
....

Finished in 0.02591 seconds (files took 0.70399 seconds to load)
4 examples, 0 failures

learnacademy@LEARNs-MacBook-Air company_contacts % rspec ./spec/models/address_spec.rb
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Version
/Users/learnacademy/.rvm/rubies/ruby-3.0.0/lib/ruby/3.0.0/arm64-darwin21/strscan.bundle: warning: already initialized constant StringScanner::Id
.....

Finished in 0.02636 seconds (files took 0.64379 seconds to load)
5 examples, 0 failures

learnacademy@LEARNs-MacBook-Air company_contacts % rails db:drop
Dropped database 'company_contacts_development'
Dropped database 'company_contacts_test'
learnacademy@LEARNs-MacBook-Air company_contacts % 