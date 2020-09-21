---
layout: post
title:      "Sinatra-Flash"
date:       2020-09-21 02:08:55 +0000
permalink:  sinatra-flash
---



Here we are at yet another major milestone of the Flatiron program. The end of this week marks the completion of our second project. This week we were utilizing Sinatra and ActiveRecord to create a program, that for the first time, was able to persist data. As might be recalled from my previous post, my CLI project took FOREVER to load. It was making a ton of API requests every time the program ran. All that data had to be gathered each time the program ran and lost each time it was terminated. Gone are those days! Thanks to ActiveRecord we are now able to store data between sessions that can be accessed again in the future. This is pretty common in our everyday live, but as a budding software engineer, is a huge deal.

I decided for this project that I'd like to create an application by which a user could create a board game collection. My idea was pretty simple. A user could sign up and create an account, add board games to their personal collection, and see other users and their board games. It wasn't a Mt. Everest sized project, but it was an excellent education experience.

### Setting up the Project 

I won't bore you with much of the details of the project. To sum it up as quickly as possible, I setup a model for users and board games, gave the user the capability of creating, reading, updating, and deleting data, and set up a way for the user to navigate through webpages in a RESTful routing manner. With the meat of the project completed, that left me in a position of what to do when things didn't go exactly the way I intended. ActiveRecord, paired with bcrypt, gives several validation and authentication methods to protect your application from being misused/used incorrectly. 

You can see more here if you're interested.

https://guides.rubyonrails.org/active_record_validations.html

### Introducing Sinatra-Flash

The part that is missing is communication with the user. Clarity is a big deal to communicating well. The tools given to us via ActiveRecord offer some failsafes, but as is, the user may have no idea what the problem is, or that there is even a problem at all. This leads to a less than ideal user experience (reducing potential customers) and more tech support (more man-hours, more expense). Both of these are bad for business.

Enter the sinatra-flash gem. This little dandy gives some neat functionality to our application. It gives us the option to maintain state in a stateless environment. 

Getting started with it was pretty easy and I'll skip the installation portion of it, but you can find that here. 

https://github.com/SFEley/sinatra-flash

### Digging Deeper

Sinatra-flash is a vehicle by which we as developers can communicate with our users. In the particular instance of my project, that was primarily error messages with some clarification and verifications thrown in. After set up, the first thing to do was to lay the ground work for how these message wouild be shown to the user. In my layout.erb, I tossed this in preceeding my yield.

```
<%if !!flash[:errors]%>
     <%flash[:errors].each do |error|%>
     <div data-alert class="alert-box">
     <%=error%>
     <a href="#" class="close">&times;</a>
     <%end%>
<%else%>
     <%flash.keys.each do |type| %>
     <div data-alert class="alert-box">
     <%= flash[type] %>
     <a href="#" class="close">&times;</a>
     </div>
     <% end %>
<%end%>
```

Flash is effectively just hashes and arrays, thus being able to iterate through it with each. What this chunk of code is doing on a practical level is... if there is a flash with a key of errors, show each error, otherwise just show each flash. If you were to just have 

```
<%flash.keys.each do |type| %>
     <div data-alert class="alert-box">
     <%= flash[type] %>
     <a href="#" class="close">&times;</a>
     </div>
     <% end %>
```

then multiple errors would look like "[error1, error2]" to your user and that's ugly to the way we as people read. I want my information that's presented to the user to look like the majority of this blog post, not the parts in the code snippet. With this in my layout.erb, the info is ready to display to the user on whatever page they might land if they hit one of these flashes.

### Flash Messages

Thankfully the most important of the flashes, the errors, are automatically created by the validation stuff I mentioned from ActiveRecord. This is all that's required of me.

`flash[:errors] = @user.errors.full_messages`

So if the user ends up in a route that shows this, they've done something wrong and this will let them know what that was. It would be really frustrating to end up in some kind of redirect cycle and not understand why. If you try to sign up with a blank password, sinatra-flash is going to let you know your password can't be blank.

Some areas of my code don't produce error message, so I added in some to give the user some feedback on their actions.

Once you successfully sign up or login, you'll see

`flash[:notice] = "You are now logged in."`

and you'll receive a similar message on logging out.

`flash[:notice] = "You are now logged out."`

Once I had the groundwork laid, placing flash messages in the routes they belonged was very simple.

### Clarity is Key

There's one more side benefit that I didn't touch on yet, and that's the fact that these flash messages not only bring clarity to your user, but they bring clarity to your code as well. RESTful routes are already pretty clear, but if statements inside of if statements can still become convoluted. By having a flash message that says

`flash[:notice] = "There is no account registered under that email address."`

it's pretty clear about what is happening in your code, or at least how someone ended up there.

Overall sinatra-flash makes the user experience of my application better and that's really the goal. I want people to enjoy and want to use something I've worked hard on. If it's obtuse or clunky, people won't enjoy their experience and they won't use your software.






