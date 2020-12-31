---
layout: post
title:      "Looking Forward"
date:       2020-12-31 05:08:19 +0000
permalink:  looking_forward
---


We actually made it to the "end". It is utterly crazy to imagine that our journey with Flatiron is nearing completion. It's been one heck of a ride, a long and difficult road to be sure. We began our 5-month trek into the bowels of web development just midway through summer of this year. The world found itself in the midst of a global pandemic, the likes of which we haven't seen in a century. What a time for a career change huh? 

Mine, unlike many others, was voluntary rather than forced. I had been looking for something different, something more, even before the pandemic wreaked its havoc. The pandemic revealed to many that work from home capabilities were not only possible, but in some cases preferable. For better or worse our world was changing. I found a desire to pursue something not limited by geographically boundaries, but a career that would be possible regardless of my location... Pretty much had to be with computers, right? So, I found Flatiron, did my research, and decided to go for it. What a wild ride it's been.

So other than the obvious importance of the soon to be full swing job hunt, what's next? Well job-searching, of course, take precedence. That means networking as best I can, resume drafting, souping up previous projects, and mock interviews etc. Other than that, however, I'm really looking forward to my next personal adventure. It's one I likely jumped the gun on, to the detriment of my mental state here at the end of the bootcamp.

About a month ago, I started tackling C#.

Now, if you've been around for a while, or have been in the programming world for some time, learning a new language may not seem like a big undertaking. I've read multiple accounts of seasoned programmers learning new languages in a matter of days. Unfortunately for me, I'm neither seasoned or experienced enough to have that easy of a time with it, let alone at the same time as learning React and Redux. I'm still very much in the infancy of learning C#, but fortunately, it shares many a similarity with Javascript and is an Object-Oriented Programming language. That means I should be well positioned for making it my next language to take on.

I figured I'd take this opportunity to go over a few things I've currently been struggling with. The major hurdle for me is that C# uses typed data, meaning a variable has to be declared with a type. If this doesn't sound like a big deal, it is for me. I'm absolutely spoiled after coming from Ruby and Javascript. In Ruby and JS a variable can store pretty much whatever, strings, integers, hashes/objects... whatever. In C# a variable must know it's type when being declared, which isn't a huge deal other than extra keystrokes I suppose, but it certainly feels annoying with Ruby and JS gave me so much freedom. For a side-by-side comparison if we look at variable declarations and assignment in each language we'd have

```
#Ruby
num = 1

//Javascript
let num = 1

//C#
int num = 1
```

C# gets even more finicky with its numbers with multiple data types depending on the number you want to use (int, float, double, decimal) arguably seem to be the most commonly used data types when dealing with numbers.

Again, maybe this doesn't seem like much, but `int num = 1` and `float num = 1.0` aren't the same. In fact, `int num = 1.0` actually throws an error where the compiler tries to convert 1.0 to an integer. So not only is it picky about its data type being a number, it's picky about what kind of number it is. This isn't difficult to learn per se, it simply feels annoying after coming from more flexible languages.

A similar annoyance I've encountered is that arrays not only share this typing issues (as in an array can't have varying data of strings and integer, each element must be of the same data type) and their length isn't dynamic either. So, if we compare array's similar to how we compared variables we will see a similar pattern.

```
#Ruby
num_array = [1, 2, 3, '4']

//Javascript
let numArray = [1, 2, 3, '4']

//C#
int[] numArray = new int[] {1, 2, 3, 4}
```

In the example above, there are a few things to note. The first is the Ruby and JS arrays are allowed to store both integers and strings in a single array no issue, the C# array would not allow that. The second is that the C# numArray is now set at 4 elements and that length can't be changed. Both Ruby and JS employ functions like `.push()`  to tack on an element at the end of an existing array.

So, I know it sounds like I'm being a big baby and those of you who are used to working with typed data maybe look at Ruby and JS like it's too freeform. I suppose it's whatever you learn first that often sticks with you as the "way things should be". Regardless, I'm really looking forward to diving into C# more and learning all about it intricacies and what it has to offer. If you're a fellow Flatiron member who hasn't yet had any exposure to C# and want to know more, I'd definitely suggest checking out some YouTube tutorials and heading over to [the C# docs](https://docs.microsoft.com/en-us/dotnet/csharp/) to get started.
