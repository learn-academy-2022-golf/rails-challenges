Challenges
Routes, Views, Controllers

As a user, I can visit a custom landing page at localhost:3000.
- Inside team_likes_controller.rb
class TeamLikesController < ApplicationController
    def home_page 
    end
end

- Inside routes.rb
Rails.application.routes.draw do
  root "team_likes#home_page"
end

- created home_page.html.erb file in app/views/team_likes folder
- on home_page.html.erb
    <h1> "We like fun days" </h1>

********************************************************************

As a user, I can see the names of my team members as hyperlinks on the landing page.
- Inside team_likes_controller.rb
class TeamLikesController < ApplicationController
    def home_page 
    end
    def renita 
    end
    def mike
    end
end

- Inside home_page.html.erb
    <h1> "We like fun days" </h1>
    <%= link_to 'Renita', '/renita' %>
    <%= link_to 'Mike', '/mike' %>

- Inside routes.rb
    Rails.application.routes.draw do
  root "team_likes#home_page"
  get 'renita' => 'team_likes#renita'
  get 'mike' => 'team_likes#mike'
end

********************************************************************
As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.

- Inside renita.html.erb
  <h1>
   Renita's faviorite 3 of all time: 
   thai food, 
   mexican food,
   chinese food!
  </h1>

-Inside mike.html.erb
   <h1>
     Mike's faviorite 3 of all time:
     brisket,
     boston butt,
     hamburgers!
    </h1> 

********************************************************************
Stretch Assigned by Austin
- put your 3 favs in an array and link to your page.

- Inside team_likes_controller.rb
class TeamLikesController < ApplicationController
    def home_page 
    end
    def renita 
        @renita_list = ["thai food", 
        "mexican food",
        "chinese food"]
    end
    def mike
        @mike_list = ["brisket",
        "boston butt",
        "hamburgers"]
    end
end

- Inside renita.html.erb
    <h1>
     Renita's faviorite 3 of all time: 
     <% @renita_list.map do |value|%>
     <%=value%>
     <%end%>
    </h1>

- Inside mike.html.erb
   <h1>
     Mike's faviorite 3 of all time:
     <% @mike_list.map do |value|%>
     <%=value%>
     <%end%>
    </h1> 


