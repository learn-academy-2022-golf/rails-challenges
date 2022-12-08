CONTROLLER:
class ThingController < ApplicationController
    def home
    end
    def blake_thing
    end
    def zeke_thing
    end
end

ROUTES: 
Rails.application.routes.draw do
  # Define your application routes per the DSL in https://guides.rubyonrails.org/routing.html

  # Defines the root path route ("/")
  # root "articles#index"

  root 'thing#home'
  get 'blake' => 'thing#blake_thing'
  get 'zeke' => 'thing#zeke_thing'
end

VIEWS: 
<h1>OUR FAVORITE THINGS!<h1>
<p>This is a place to see our favorite stuff</p>
<%= link_to 'blake', '/blake' %>
<%= link_to 'zeke', '/zeke' %>

<h1>BLAKES FAVORITE THINGS</h1>
<ul>
    <li>Gladiator</li>
    <li>Space ships</li>
    <li>spaghetti</li>
</ul>
<%= link_to 'home', '/' %>

<h1>ZEKES FAVORITE THINGS</h1>
<ul>
    <li>CHOCOLATE</li>
    <li>DOGS</li>
    <li>airplanes</li>
</ul>
<%= link_to 'home', '/' %>