#### Using Subject.find_each instead of Subject.find when iterating
When looping thorugh a collection of records from the database using the `SUbject.all` method causes Ruby to pull and cache batch size of 5000mb (more than you need). Instead, use [batch processing](http://api.rubyonrails.org/classes/ActiveRecord/Batches.html).<br>
Instead of iterating with, <br>
```ruby
Material.each do |material|
    material.do_something
end
```
Use,
```ruby
Material.find_each do |material|
    material.do_something
end
```

#### When 'bundle install' is being stupid and doesn't work with 'pg' gem
Use:
`ARCHFLAGS="-arch x86_64" bundle install`

#### Before pushing on Heroku, clean up /tmp/ with:
`rake tmp:clear`
