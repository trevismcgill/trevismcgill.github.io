---
layout: post
title:      "Getting RailsRoaded"
date:       2020-10-20 20:37:58 +0000
permalink:  getting_railsroaded
---


Wow.

To say this project and in fact, the past couple weeks, were difficult would be an understatement. We were told over and over, "Rails is like magic, it does so much for you!" There's no arguing that this is true and for many things it's really awesome how powerful Rails is. 

However, unfortunately for me, my personality favors a more literal and explicitt workstyle and the level of abstraction that we've arrived at with Rails certainly made things more difficult for me. I spent a disproportionate amount of time researching and googling on this project compared to the actual time I spent coding. 

And apparently, I'm not the only one. This module seemed to be exceptionally difficult for the majority of my cohort. The even stranger aspect is that I've been told our cohort is the outlier and one of the only ones to "despise" Rails. Must be something in the water.

But now I'm here, on the other side of the Rails project, to talk with you fine folks about some nugget of knowledge and wisdom I walked away with. For this project I elected to do another D&D focused web app that allows a user to keep track of characters and campaigns they may have or be a part of.

I'm going to cover two topics today. The first being the most critical and beneficial lesson I learned in this project, and the second being an interesting gem I added to my project late in the game.

### Lesson One: Community

This topic is less technical in nature, but I can't overstate the importance of it enough. It may not be surprising to many of you, but I wouldn't have been able to complete the project without this lesson and that makes it more important than any project, language or even field specific tip I could give.

Something we've been taught from the beginning is to learn how to google and google well. Stack Overflow, Quora, GitHub, ruby guides, etc. are all places we've been directed to for guidance and answers. 

While these are excellent resources, and they even allow interaction between members, the resource I've relied on the most for the issues that have really given me the biggest problems is live person-to-person interaction. Now, you might say that people responding on forums qualifies. You'd be right, but I'm talking about having a real-time conversation where you have another person to pose your questions to and you get feedback from them in real-time.

The real-time aspect is important considering efficient use of time. More often than not, when I've been tackling a problem, I really don't want to post to a forum and hope I get an answer by tomorrow. I'm either being bottlenecked by the problem that is keeping me from progressing or I'm trying to wrap up a feature. 

The best results I've had and the most I've learned in this program has been from lectures from the instructor, office hours, zoom calls with cohort members, or a multitude of discord servers. These are all places where I can post my issue to the collective and have individuals in the industry that can take a look at my issue right then and there.

Putting my issue in front of many eyes, all from different walks of life, means I get some really great feedback. I learn to be better thanks to the experience of those who came before me. Many of these people have already learned the hard lessons for me.

### Lesson Two: Rubocop Gem

Railroading has a really strong advantage —  convention and standards. These exist to make our lives easier. By "forcing" a person to work in a specific way means others can assist and understand your work more effectively because you both approach the situation in the same way. RESTful routing is a great example. You don't *have* to follow convention, but if you do, those involved will be better for it.

Once again, I'm not going to give you a step by step guide on how to include this gem, but if you're interested you can [check it out here](https://github.com/rubocop-hq/rubocop).

You'll also want to grab [Rubocop-rails](https://github.com/rubocop-hq/rubocop-rails) if you're using rails (duh).

Rubocop is a linter, if you don't know what that is, I didn't either so...

"lint, or a linter, is a static code analysis tool used to flag programming errors, bugs, stylistic errors, and suspicious constructs."  Thanks, Wikipedia!

In other words, it does this really cool thing of assisting you with following convention, in this case ruby/rails convention. Remember how we just talked about the benefits of following convention? This makes that easier. 

Aside from taking the time to go over the README, `rubocop -h` can give you a good glimpse into what this gem has to offer, but I would certainly suggest reading the [actual documentation](https://docs.rubocop.org/rubocop/0.93/index.html).

I won't give a deep dive into the actual functionality of the gem other than this:

Run `rubocop` and watch the magic.

`45 files inspected, 67 offenses detected, 56 offenses auto-correctable`

There's the readout from my project before I did anything. That's a lot of places where I didn't follow convention, the majority of those being honest mistakes, not anti-establishment rebellion. Take a look at a few examples from my terminal print-out.

```
app/controllers/application_controller.rb:14:3: W: Layout/DefEndAlignment: 
end at 14, 2 is not aligned with def at 12, 4.
  end
```

```
app/models/campaign.rb:4:5: C: Rails/Validation: 
Prefer the new style validations 
validates :column, presence: value 
over validates_presence_of. 
validates_presence_of :campaign_name, :setting, :min_level
```

```
config/routes.rb:18:20: C: Style/HashSyntax: Use hash rockets syntax.
  delete 'logout', to: 'sessions#destroy'
```

As you can see, it's not that any of this is broken. The code works, but it doesn't follow convention. If you recall, running `rubocop` told me, "56 offenses auto-correctable". That's right, Rubocop can fix the majority of the errors itself. You can run `rubocop -a` to have many of your syntax mistakes fixed for you. 

Now, I didn't use it for that. I think the real power of Rubocop at this stage in my development journey is helping me understand what mistakes I'm making. I didn't use it as a quick-fix cleaner, but instead as a teacher of convention. 

Being on the same page as your fellow developers is extremely useful. Whether or not you're going to follow convention is up to you; however, educating yourself on what the standard is will certainly assist you moving forward in your career and with being a better team player.

If you find yourself wondering how RailsRoading played into this blog at all, railroading is a term often used in D&D to represent a story that doesn't give much control to the players. It's where the person running the game forces you into a certain situation or way of playing. 

It generally has a negative connotation to it; however, I think, in a professional environment, railroading — a.k.a. convention  — helps us to be better collectively by giving us standards and similar expectations to what code should do and how it should function. 

This structure allows me to take a project that's been completely built alone and place it in front of another developer who will be able to contribute to my project without having to familiarize themselves with the very specific way I have structured everything.

What's the takeaway from all this? For me it was the realization that I'm not just an individual behind a screen working in absolute solitude, but that I'm a part of a much larger industry where my ability to work and communicate with others may be what makes the most difference.



