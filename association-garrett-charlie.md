Setup
Create a new rails application and database
Create a model for owner
An owner has a name and address, and can have multiple credit cards
Create a model for credit card
A credit card has a number, an expiration date, and an owner
Challenges
Create three owners and save them in the database
Create a credit card in the database for each owner
Add two more credit cards to one of the owners
Stretch Challenge
Add a credit limit to each card
Find the total credit extended to the owner with multiple credit cards

```ruby
[#<Owner:0x00000001214e1ef8                                                  
  id: 1,                                                                     
  name: "Jeff Bezos",                                                        
  address: "Amazon.com",                                          
  created_at: Tue, 06 Dec 2022 23:10:50.560707000 UTC +00:00,     
  updated_at: Tue, 06 Dec 2022 23:10:50.560707000 UTC +00:00>,    
 #<Owner:0x00000001214dbb98                                       
  id: 2,                                                          
  name: "Elon Musk",                                              
  address: "Twitter Hell",                                   
  created_at: Tue, 06 Dec 2022 23:11:16.085553000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:11:16.085553000 UTC +00:00>,
 #<Owner:0x00000001214db788                                  
  id: 3,
  name: "Mark Zuckerberg",
  address: "Metaverse",
  created_at: Tue, 06 Dec 2022 23:11:50.339732000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:11:50.339732000 UTC +00:00>] 



[#<CreditCard:0x0000000121ac67b0                                    
  id: 1,                                                            
  number: 1234567890123345,                                         
  expiration_date: Thu, 31 Dec -4710,                               
  owner_id: 1,                                                      
  created_at: Tue, 06 Dec 2022 23:15:58.317279000 UTC +00:00,       
  updated_at: Tue, 06 Dec 2022 23:37:22.857943000 UTC +00:00,       
  limit: 1000>,                                                     
 #<CreditCard:0x0000000121ac66e8                                    
  id: 2,                                                            
  number: 1234567890109835,                                       
  expiration_date: Thu, 04 Jan -4712,                             
  owner_id: 2,                                                    
  created_at: Tue, 06 Dec 2022 23:18:17.805358000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:37:22.864217000 UTC +00:00,
  limit: 1000>,
 #<CreditCard:0x0000000121ac6620
  id: 3,
  number: 1987654657865436,
  expiration_date: Mon, 01 Jan -4712,
  owner_id: 3,
  created_at: Tue, 06 Dec 2022 23:20:42.210151000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:37:22.866172000 UTC +00:00,
  limit: 1000>,
 #<CreditCard:0x0000000121ac6558
  id: 4,
  number: 1987654657865436,
  expiration_date: Tue, 06 Dec 2022,
  owner_id: 3,
  created_at: Tue, 06 Dec 2022 23:28:28.866238000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:37:22.868009000 UTC +00:00,
  limit: 1000>,
 #<CreditCard:0x0000000121ac6490
  id: 5,
  number: 1987654657934586,
  expiration_date: Tue, 06 Dec 2022,
  owner_id: 3,
  created_at: Tue, 06 Dec 2022 23:29:46.055925000 UTC +00:00,
  updated_at: Tue, 06 Dec 2022 23:37:22.869844000 UTC +00:00,
  limit: 1000>] 


  def get_limits arr
         bezosArr = []
         muskArr = []
         zuckArr = []
         arr.map do |card|
             if card.owner_id == 1
                 bezosArr.push card.limit
             end
             if card.owner_id == 2
                 muskArr.push card.limit
             end
             if card.owner_id == 3
               zuckArr.push card.limit
             end
     
         end
        p " Bezos Limit is #{bezosArr.reduce(0) {|sum,num| sum+num}}"
         p " Musks Limit is #{muskArr.reduce(0) {|sum,num| sum+num}}"
          p " Zucks Limit is #{zuckArr.reduce(0) {|sum,num| sum+num}}"
 end
 => :get_limits 
 get_limits CreditCard.all
  CreditCard Load (15.6ms)  SELECT "credit_cards".* FROM "credit_cards"
" Bezos Limit is 1000"                                                 
" Musks Limit is 1000"                                                
" Zucks Limit is 3000"                                                 
 => " Zucks Limit is 3000"                                                   
3.0.0 :079 > 
```