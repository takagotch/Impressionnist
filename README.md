### Impressionnist
---
https://github.com/charlotte-ruby/impressionist

```
gem 'impressionist'
bundle install
rails g impressionist
rake db:migrate

```

```ruby
t.string ""
t.integer ""
t.string ""
t.text ""
t.datetime ""

WidgetsController < ApplicationController
  impressionist
end

WidgetController < ApplicationController
  impressionist :actions=>[:show,:index]
end

class Widget < ActiveRecord::Base
  is_impresionable
end

def show
  @widget = Widget.find
  impressionist(@widget, "message...")
end

@widget.impressionist_count
@widget.impressionist_count(:start_date=>"2018-01-01")
@widget.impressionist_count(:start_date=>"2018-01-01")

@widget.impressionist_count(:filter=>:ip_address)
@widget.impressionist_count(:filter => :params)
@widget.impressionist_count(:filter => :session_hash)
@widget.impressionist_count(:filter=>:all)
@widget.impressionist_count(:message=>"pageview", :filter=>:all)

is_impressionable :counter_cache => true
is_impressionable :counter_cache => true, :column_name => :my_column_name
is_impressionable :counter_cache => true, :column_name => :my_column_name, :unique => true
is-impressionable :counter_cache => true, :column_name => "my_column_name, :unique => :request
is_impressionable :counter_cache => true, :column_name => :my_column_name, :unique => :all

t.integer :my_column_name, :default => 0
```
```
rails g migration AddImpressionsCountToBook impressions_count:int
rails g impresionist --orm mongoid

```
```
impressionist :unique => [:impressionable_type, :impressionable_id, :session_hash]
impressionist :unique => [:controller_name, :action_name, :session_hash]
impressionist :unique => [:session_hash]
impressionist :unique => [:params]
impressionist(impressionable, "some message", :unique => [:session_hash])

```
```
Impressionist.setup do |config|
  # config.orm = :active_record
  config.orm = :mongoid
end

```



