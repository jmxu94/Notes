## Sessions and Flash

>Sessions
>>Flash

### What are Sessions?

If HTTP is a stateless protocol....then sessions makes it stateful.

#### Sessions...
* consists of a hash of values
* a session id to identify the hash
* allows you to persist data between HTTP requests without using the database

#### Session Examples:
* shopping cart contents
* user id

````
session['user_id'] = @user.id
User.find(session['user_id']
````
````
session.clear
````


#### Session Rules of Thumb:
* don't store large objects
* don't store critical data
* watch out for session hijacking

*****

### What is the Flash?

Part of the session...but cleared after *each* request.

#### The Flash....
* is useful for passing error messages that only need to be available for the next request
* accessed similar to the session
* allows you to persist data for a single HTTP request

#### Flash Examples:
* sending singular messages
* sending a message on logout
* sending an alert
* sending a success or failure message

````
flash['notice'] = "Logged out"
````
````
flash.keep
````


[Ruby on Rails Guide: Sessions](http://guides.rubyonrails.org/security.html#sessions)

[Ruby on Rails Guide: Flash](http://guides.rubyonrails.org/action_controller_overview.html#the-flash)
