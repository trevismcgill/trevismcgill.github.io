---
layout: post
title:      "All Aboard the Java Train"
date:       2021-04-05 02:34:49 +0000
permalink:  all_aboard_the_java_train
---


I'm back this week to talk a bit more about my learnings in Java since last Sunday. I've continued moving forward with the Codecademy course and I'm still really enjoying the structure of the curriculum and how it presents the basics to you. Last week I presented a super basic method that did nothing other than return whatever was passed to the method as an argument. I did this to compare it to Ruby, which I'm more familiar with, and to go over a few of Java's keywords. 

This week I'd like to talk a bit more about access. It's something I feel like we barely covered in our time at Flatiron. We used a few private methods in Ruby, but it was definitely more of a do this because this works and didn't really explain much of the why. Let's start by looking at the four access modifiers in Java.

### Access Keywords

Access keywords in Java can be assigned to variables, methods, and classes.

**Public-** Access is available from almost anyway.

**Private-** Access is only available within the same class.

**Protected-** Access is available within the same package or within child classes located in different packages.

**Default-** 
*Automatically assigned if you don't define an access keyword.* 
Access is available to anything within the same package.

Public and Private are likely relatively straightforward, but what's this talk about packages. 

A package is essentially just a directory where multiple, preferably related, class files live. So when we use the terms Protected and Default, we're allowing access to certain parts of our program, but not others. Whereas public is akin to everything has access and private is like almost nothing has access.

In my short time with Java, I have predominantly seen public and private used. I haven't dug deep enough yet, but I'm assuming protected plays a larger part in the seperation of concerns paradigm.

As far as omitting an access keyword, and by proxy assigning default access to something, I have hardly seen that used at all. From what I've read and seen, if you would make something default, you almost always make it public or protected instead. These both give wider access than default does, but it seems to be preferable to using no keyword at all.

### Why Limit Access?

As far as I can tell, there is no real requirement or necessity in making anything something other than public. In fact, limiting access to parts of our code tends to require more work. Privatizing variables then requires using getters and setters to read or write to that variable from outside the class, just as an example. This isn't at all to say everything should be public.

Access serves the purpose of giving readability to our code. It's extremely useful in conveying intent to other developers as to what and how our code is intended to be used.
