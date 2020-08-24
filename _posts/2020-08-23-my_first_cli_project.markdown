---
layout: post
title:      "My First CLI Project"
date:       2020-08-23 20:59:25 -0400
permalink:  my_first_cli_project
---


This week marks the first project for those of us in the 07/27 Full-Time Software Engineering Cohort. It would really be the first time we were "let loose" to tackle something of our own creation with minimal handholding. I was a little nervous, to say the least, and everything prior to this was very cut and dry. Pass these tests... move on. Thankfully, one of the last lessons leading up to project week led us through a mock CLI and did an awesome job preparing me for the actual project.

We were introduced to the concepts of scraping and utilizing an API and then given the choice of which one we wanted to be the focus of our project. Although I understand the usefulness of scraping — you can pretty much always scrap, but you can only use an API if it exists :P — I'm a big fan of consistency and my code not breaking when a site changes on a whim. With scraping eliminated, that left me the task of finding an API to use.

## The Actual Project

I set out on my grand journey to seek out whichever API suited my fancy. I figured I needed to look for something that I was both interested in and familiar with. I settled on an API of a card game I enjoy: Legends of Runeterra. There are several different parameters that cards have like cost, type, region, and additional subtypes. Those cards can be gathered into decks, so it seemed like a pretty great topic to do my project on. That was, however, until I found out that it wasn't an API that you send requests to over the internet. It was an actual JSON file. No big deal. I reached out to our cohort lead and they told me I could turn it into a csv and use the data that way. Great! It'll still work.

## It Was a Big Deal

By the time 3/4's of the first day had gone by, I had gotten nowhere other than setting up my project file. I Googled solutions and tried different gems, methods, etc. One error would be solved only for another to pop up. I guess we really are becoming software developers! I'm confident I could have figured it out, but I was more familar with online APIs. Work smarter, not harder. So, I did what anyone would do.

## I Scrapped It

I found a Dungeons and Dragons API that was available to request from via URL and was structured very similarly to the API our cohort lead had given a lecture on. Getting my minimum viable product (mvp) up and going was priority number one. Fancy can come after functional. My work had finally begun in earnest.

Things actually went pretty smoothly after that. About a day of work in and I had my mvp. However, I wanted to keep increasing functionality to give the user some more options and refactor things to be more intuitive. Really, my goal was to give the user a better experience with each commit. Things seemed to be fine, but I had one constant struggle throughout the whole process — optimization.

My program takes a real long freakin' time to load. It's what I feel is the biggest weakness of the whole project. I checked with some folks, did some research on how to improve it, and I received some great suggestions, but I wanted an established database. The main issue is compiling all the information. Once you're in, you're golden and All the information is at your fingertips instantly. I could have reduced frontload by grabbing only the information the user wants to see at that moment in time. I'm not sure which way is best. Personally, I like having the information readily available as you're only requesting from the API at initialization of the program.

## The Final Commit

Overall, I actually had a really great time with this project. It was crazy satisfying to accomplish something on this level that I never would have dreamed of doing three weeks ago. I loved seeing each iteration improve or collapse my previous work. The feeling of building this thing from scratch and it actually working was really cool. It was awesome getting to talk through things with cohortians and I joined a couple of discord servers for Rubyists and Riot Games Third-Party Developers and got some great advice from devs in those channels.

Who knew "work" could be this fun. It's a fantastic marriage of creativity and puzzle-solving, and it was a great learning experience and an even better confidence builder. 

Maybe I can actually do this thing.

