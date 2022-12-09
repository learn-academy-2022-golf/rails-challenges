As a user, I can visit a page called cubed that takes a number as a param and displays that number cubed.

class ParamsController < ApplicationController
    def home
    end

    def cubed
        @number=((params[:number]).to_i)**3
    end
end

<h1>Rails Params<h1>

<%= link_to "cubed", 'cubed' %>

Rails.application.routes.draw do
  # Define your application routes per the DSL in https://guides.rubyonrails.org/routing.html

  # Defines the root path route ("/")
  # root "articles#index"
  root "params#home"
  get "cubed/:number" => "params#cubed"
  get "cubed" => "params#cubed"
end

<h1>Rails Cubed<h1>
<h2><%=@number%><h2>
<%= link_to 'home', '/' %>


As a user, I can visit a page called evenly that takes two numbers as params and displays whether or not the first number is evenly divisible by the second.

 def evenly
        if (((params[:firstnum].to_i) % (params[:secondnum].to_i))==0)
            @evenly="True"
        else @evenly="False"
    end

    <%= link_to "evenly", 'evenly' %>

     get "evenly/:firstnum/:secondnum" => "params#evenly"
  get "evenly" => "params#evenly"

  <h1>Rails Evenly<h1>
<h2><%=@evenly%><h2>
<%= link_to 'home', '/' %>


As a user, I can visit a page called palindrome that takes a string as a param and displays whether it is a palindrome (the same word forward and backward).



As a user, I can visit a page called madlib that takes params of a noun, verb, adjective, adverb, and displays a short silly story.
