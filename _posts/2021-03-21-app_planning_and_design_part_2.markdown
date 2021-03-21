---
layout: post
title:      "App Planning and Design (Part 2)"
date:       2021-03-21 17:22:09 -0400
permalink:  app_planning_and_design_part_2
---


Hello everyone! I'm back to dive a little deeper into the app I'm currently working on. Unfortuantely, I wasn't able to work on it as much as I wanted too. I recently took a part-time job to help make ends meet which had me out of town the majority of the week.

However, I've got some ideas for what to do with the app so let's get started.

#### **Goals**

So as I mentioned last week, the main objective of the app is going to be to connect people interested in falconry and ideally help build associations and relationships between would-be apprenctices and general/master falconeers.

In order to realize that dream, I've come up with a fews things that the app either has to have or would be pretty cool.

* The app has to have some way to connect individual users so I definitely want to have account creation

* Ideally the app will have some way to communicate with other users (either inbox messaging or pop-up style chat)

* I'd love to have some type of Google maps overlay to show potential mentor's in your area (filterable by distance maybe?)

* I'd also like to include a few informational pages to showcase the different types of raptors or falconry clubs by state

#### **User Account**

Creation of a user account will be fairly straightforward using rails and ActiveRecord. I am opting for authentication using Oauth as it just seems the logical solution to me. I could handle authentication as a solo dev or I could rely on the infastructure of a large corporation with far more manpower and resources. It's an obvious choice to me.

#### **Chat**

So I haven't done anything like a chat before. Honestly, I'd really like to give it a facebook messenger vibe. Pop-up in the lower right corner to allow you to correspond with another user. I'm definitely not a big fan of the email or forum post style, seems outdated to me. Since React is maintained by Facebook, I think I'll have pretty decent luck finding a way to accomplish this.

#### **Google Maps**

This one is going to be the most difficult for sure as it's the area I have the least experience in / idea of how to make it happen. 

The first hurdle to overcome here is going to be getting the information to begin with. There are two options here. I could simply set up the app to require a person include city and state when setting up an account or I could try to gather the information myself. The main issue I can forsee with having the user provide the data is that many people would opt out of providing a location even as broad as city and state. I have considered some kind of clause where a person can opt into being connected with other users in their area. That way if a person didn't want to be connected their information wouldn't be necessary.

Option two is that certification's, at least in Illinois, tend to be public record. This is favorable to me because it most accurtately represents the whole motivation behind my app idea. Having a hard time finding a sponsor myself, it'd be nice if there was a centralized resource available that I could go look at to find someone in my area. This one will take more work on my end of course, but would better option in my opinion.

Let me be clear to say, city, state would be totally adequate as far as needed information goes. I have no desire to plaster people's intimate or private personal information all over the internet.

From a technical side, I have no idea at the moment how to accomplish this. That might come as a later blog post when I get to it.

#### **Informational Pages**

This item is also pretty straightforward as well. It'll be a lot of React Bootstrap to format and prettify the site and some scraping for information about birds of prey. Then I'll likely compile a list of links to websites for all the major falconry clubs in America.


#### **Till Next Time**

That's where I'm at with things at the end of this week. I think if I can manage to get the above things incorporated well then the app will be in a pretty good spot. It's main purpose will be to connect falconeer's, but could certainly be interesting for others as well.








