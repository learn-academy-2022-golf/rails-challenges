class MainController < ApplicationController
    def tyler
        @favorite_things=["water", "coffee", "trail mix"]
    end

    def garrett
        @favorite_things = ["pizza", "burgers", "beer"]

    end
    def cubed 
         @cubednum = params[:number].to_i ** 3 
    end
    def evenly
        
        params[:number1].to_i % params[:number2].to_i  == 0 ? @show="This is evenly divisible!" : @show="Hell no!"
    end
    def palindrome
        params[:string].reverse == params[:string] ? @palin="Nice job, it's a palindrome!" 
        : @palin="No it's not."
    end
    def madlib 
        @story =
        "#{params[:adj]} 
        #{params[:noun]}
        #{params[:verb]}
        #{params[:adverb]}"
    end
end
___________________________________________
Rails.application.routes.draw do
  # Define your application routes per the DSL in https://guides.rubyonrails.org/routing.html

  # Defines the root path route ("/")
  # root "articles#index"

root 'main#home' 
get '/tyler' => 'main#tyler'
get '/garrett' => 'main#garrett'
get '/' => 'main#home'
get '/cubed/:number' => 'main#cubed'
get '/evenly/:number1/:number2' => 'main#evenly'
get '/palindrome/:string' => 'main#palindrome'
get '/madlib/:noun/:verb/:adj/:adverb' => 'main#madlib'
end

