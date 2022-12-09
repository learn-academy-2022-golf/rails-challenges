# NOTES

data_controller.rb

```ruby
class DataController < ApplicationController

    def cubed
        @number = params[:number].to_i ** 3
    end

    def evenly
        @num1 = params[:number1].to_i
        @num2 = params[:number2].to_i
        if @num1 % @num2 == 0
            @result_string = 'True'
        else
            @result_string = 'False'
        end
    end

end
```

cubed.html.erb

```ruby
<h1>Cubed</h1>
Number is: <%= @number %>
```

evenly.html.erb

```ruby
<h1>Cubed</h1>
Number is: <%= @number %>
```

routes.rb

```ruby
Rails.application.routes.draw do
  get '/cubed' => 'data#cubed'
  get '/cubed/:number' => 'data#cubed'
  get '/evenly' => 'data#evenly'
  get '/evenly/:number1/:number2' => 'data#evenly'
end
```
