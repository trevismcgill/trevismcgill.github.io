---
layout: post
title:      "To Infinity and D&DBeyond"
date:       2020-12-28 23:00:13 +0000
permalink:  to_infinity_and_d_and_dbeyond
---

The final hurdle was laid out in front of us a couple weeks back now. Our project was to build an application utilizing the React framework coupled with Redux. I opted for doing my best at making a D&DBeyond clone. The last five months have been filled with many long nights and a lot of frustration, but nothing like this. To say I bit off more than I could chew is a massive understatement, and while I'm proud of what I accomplished, it's nowhere near complete.

Anyway, React makes creating a web app easier than vanilla Javascript, but for some reason, it was hard to wrap my mind around. Come to think of it, I had a similar problem with Rails. My brain parses verbose, explicit code easier than the magic and abstraction that Rails and React offer. Once you come to grips with what these frameworks offer you, it's hard to go back.

Regardless, this final project was hard. Harder and more painful than any before it — at least for me. So hard, in fact, that I struggle as to what I could even hope to make the focus of this blog post. Who am I to teach anything about React or Redux?

Despite that, I'm going to do my best to tackle Redux primarily in hopes that I will better acquaint myself with it. It should also be noted that my experience with Redux is paired with React, and all my knowledge of Redux is confined to that partnership. 

We'll need to begin with what Redux is. As far as I'm concerned Redux is a global container. A place where you can place data and that data, with little effort, is then able to be accessed globally across your application. This isn't native to Javascript or React and was created to make developers lives easier. Easier is good.

Redux is excellent at combating something called prop-drilling. Props —short for properties— are pieces of data your React components have access too. Without Redux, if a component requires data from a parent component, sometimes many levels above that component, you would have to pass the data from parent to child again and again until finally reaching your destination. The larger the application and the move moving parts, the more difficult, time-consuming, and error-prone this becomes.

In order to avoid this, we utilize Redux.

Redux eliminates the need, but not the ability, to pass data through chains of components and allows any component to access the global store and manipulate the data within. In this instance, "store" is the term Redux uses for naming that global container we discussed earlier.

Redux gives us a single source of truth. A container where we can put data and have all our components plugged in. If one component changes the data in the store, it's changed for all the components that rely on it. Not only do we maintain our data in a single place, it's also accessible from anywhere. No more prop-drilling, and a component 20 layers down the line can access the same data, just as easily, as the top-level component.

That's a mighty high flyover of what Redux offers. Mostly the why and not the how. If you want to check out more about it, hop on over to https://redux.js.org to peruse the actual Redux docs for the specifics.
