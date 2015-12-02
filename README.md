## Recreating Our Social Media App

![](http://192.169.195.161/wp-content/uploads/2014/02/smm1.png)

### Setting up Our Database

Today's Goal is to setup a database for your social media app to save all of your awesome content. 

**Step 1** - Add a database connection to your application (Hint: It's totally okay to copy the environment.rb file from your Fwitter project.)

**Step 2** - Set up your Gemfile with all of your gems - don't forget activerecord and sqlite3 (totally okay to copy from Fwitter again!)

**Step 3** - Create a Rakefile and add the necessary lines of code (again, use Fwitter as a reference)

**Step 4** - Now we need to modify your Content class so that it inherits from ActiveRecord::Base. 

**Step 5** - Create a migration for the items table `rake db:create_migration NAME="create_content"` and get in there to set up your `up` and `down` methods. (Look at your Fwitter migration). Don't forget to run your migration with `rake db:migrate` when you are done! The items table should include columns for:

```ruby
:username
:content
```

**Step 6** -  You'll want to modify your controller action for creating new content. Remember that ActiveRecord is like a hash when creating new content. For Twitter: 

```ruby
Tweet.new("ianstwitterhandle", "My first tweet!")
```
becomes

```ruby
tweet = Tweet.new(:username => "ianstwitterhandle", :status => "My first tweet!")
tweet.save
```

## Bonus Challenges
+ Add a page that displays all of the content for a user based on the user. For example, going to "www.fwitter.com/users/ianstwitterhandle" will display all of the tweets where the username is "ianstwitterhandle", "www.fwitter.com/users/taylorswift13" will display all of the tweets where the username is "taylorswift13", etc. You'll need: 
  * Dynamic URLs - check out the Sinatra documentation on routes [here](http://www.sinatrarb.com/intro.html#Routes)
  * ActiveRecord's where method - takes a condition as an argument and returns an array of items where the condition is true. [ActiveRecord's where](http://api.rubyonrails.org/classes/ActiveRecord/QueryMethods.html#method-i-where)

<a href='https://learn.co/lessons/hs-social-media-recreation-part-2' data-visibility='hidden'>View this lesson on Learn.co</a>
