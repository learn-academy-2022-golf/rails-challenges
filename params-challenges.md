main cont#################################
```ruby
class MainController < ApplicationController

    def home
    end

    def cubed
        @number = params[:number].to_i**3
    end

    def evenly
        if params[:number1].to_i % params[:number2].to_i == 0 
            @evenly = 'yes'
        else @evenly = 'nope'
        end
    end

    def palindrome 
        if params[:word].downcase == params[:word].reverse.downcase
            @palindrome = 'sure does'
        else
            @palindrome = "sure doesn't"
        end
    end

    def madlib
        @noun = params[:noun]
        @verb = params[:verb]
        @adjective = params[:adjective]
        @adverb = params[:adverb]
    end
end
```



routes: 
```ruby

Rails.application.routes.draw do

root 'main#home'

get 'cubed/:number' => 'main#cubed'
get 'evenly/:number1/:number2' => 'main#evenly'
get 'palindrome/:word' => 'main#palindrome'
get 'madlib/:noun/:verb/:adjective/:adverb' => 'main#madlib'
end

```

home.html.erb:
```ruby
<h1>WELCOME HOME!<h1/>
```

cubed.html.erb
```ruby 
<h1> <%= @number %> <h1/>
```

evenly.html.erb
```ruby
<h1> <%= @evenly %> <h1/>
```

palindrome.html.erb
```ruby
<h1> <%= @palindrome %> <h1/>
```

madlib.html.erb
```ruby
<h1>Hi, we went to the <%= @noun %> today. I saw <%= @noun %> there! <%= @noun %> was very <%= @adjective %>, so I <%= @verb %>. Then I left <%= @adverb %> to my car. <h1/>

```




