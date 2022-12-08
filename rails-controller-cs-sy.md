As a user, I can visit a custom landing page at localhost:3000.

```ruby
class MainController < ApplicationController
    def MainController
        render html:'Hi'
    end
end
root "main#MainController"
```

As a user, I can see the names of my team members as hyperlinks on the landing page.
```ruby
def Charlie
end
    
def Shannon
end
Charlie.html.erb
Shannon.html.erb
<ul>
<li><%= link_to 'Charlie', 'Charlie' %></li>

<li><%= link_to 'Shannon', 'Shannon' %></li>
</ul>
 get "Charlie" => "main#Charlie"
  get "Shannon" => "main#Shannon"
```

As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)

```ruby
<h1>Favorite Things</h1>
<ul>
<li><h2>Anime</h2></li>
<li><h2>Video Games</h2></l1>
<li><h2>Looking good</h2></l1>
</ul>

<h1>Favorite Things</h1>
<ul>
<li><h2>Charcuterie Board</h2></li>
<li><h2>Prince</h2></l1>
<li><h2>Traveling</h2></l1>
</ul>
```

 .pic{
    height:100vh;
    width:100vw;
 }
 .pic1{
    height:200px;
    width:300px;
 }
 .center{
    display:flex;
    justify-content: space-between;
 
 }
 .center1{
    display: flex;
    justify-content: center;
 }
 <h1 class="center">Favorite Things</h1>
<ul class="center">
<li><h2>Charcuterie Board</h2><img class="pic1" src="<%= asset_path('S1.jpeg') %>"></li>
<li><h2>Prince</h2><img class="pic1" src="<%= asset_path('S2.webp') %>"></l1>
<li><h2>Traveling</h2><img class="pic1" src="<%= asset_path('S3.jpeg') %>"></l1>
</ul>
<%= link_to 'Home', '/' %>
<h1 class="center">Favorite Things</h1>
<ul class="center">
<li><h2>Anime</h2><img class="pic1" src="<%= asset_path('C1.jpeg') %>"></li>
<li><h2>Video Games</h2><img class="pic1" src="<%= asset_path('C2.webp') %>"></l1>
<li><h2>Looking good</h2><img class="pic1" src="<%= asset_path('C3.jpeg') %>"></l1>
</ul>
<%= link_to 'Home', '/' %>
<h1 class="center1">The Eiffel Tower Squad</h1>
<ul class="center">
<li><%= link_to 'Charlie', 'Charlie' %></li>

<li><%= link_to 'Shannon', 'Shannon' %></li>
</ul>
<img class="pic" src="<%= asset_path('Eiffel.webp') %>">
