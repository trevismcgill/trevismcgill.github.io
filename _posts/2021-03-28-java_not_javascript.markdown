---
layout: post
title:      "Java, not JavaScript"
date:       2021-03-28 23:05:59 +0000
permalink:  java_not_javascript
---


This week gave me a bit of an unexpected, but wonderful surprise. Udemy was having another of their semi regular sales earlier in the week and I noticed there was a Java course available. Java is one of the most popular programming languages, arguably the most popular for many years until recently dethroned by C, and boasts 25+ years of being around and kicking. It's platform agnostic and an object oriented language, which means paradigm wise I should find myself in familar territory. Additionally, according to this [ScienceSoft article](https://www.scnsoft.com/blog/java-still-used#:~:text=After%2025%20years%20of%20life,innovations%20and%20software%20development%20trends.), Java is utilized by 90% of Fortune 500 companies, which was incentive enough for me to take a look. I went ahead and picked it up. I was curious so I decided to go ahead and start on it to see what it would be like. Well, it's been 5 days since I got it and I've done almost nothing else.

### Tackling Java

Right before graduation. I posted a blog talking about how I was looking into C#. I laid off of C# soonafter that to go back to Ruby and JavaScript based work and study. Here's what pretty cool, at least to me, about getting my feet wet with C# and JavaScript. Java is very much like a hybrid of JavaScript and C# (remember this is based on the order in which I've been exposed to these langauges so others may have very different opinions on that).

Java requires typing your variables and methods, just like I dicussed with C#, but it also shares many recognizable methods with JavaScript like .toUpperCase() and for loops appear to function nearly identically. Java also utilizes lambda expressions, which are equivocally just Java's version of JavaScript's anonymous functions. While these aspects may not be the most exciting things and are predominantly just syntax similarities, it has made things a lot easier for me as a newbie coder.

The biggest obstacle I've been faced with in Java is exactly the same one I ran into when trying to get acquainted with C#, data typing. Since neither Ruby nor JavaScript require this of the programmer, trying to parse Java code has been extra difficult. Every code block seems verbose and redundant. Let's make a method from Ruby and Java to show the difference.

### Java vs. Ruby

Let's simply make a class method that both prints to the terminal and returns the number passed to it as an argument.

-***Ruby***
```
def self.return_num(n)
     puts n
     return n
end
```

Not much to it to be honest. Now take a look at the same method in Java.

-***Java***
```
public static int returnNum(int n) {
     System.out.println(n);
     return n;
}
```

Let's go ahead and dissect these methods.

-***Ruby***

`def self.return_num(n)`

**def**- just lets Ruby know we're beginng a method declaration.

**self**- defines this as a class method.

**return_num**- the name we're assigning to the method.

**(n)**- the variable representing the data we will pass to the method as an argument.

`puts n`

**puts n**- prints whatever follows (n in this case) to the terminal output.

`return n`

**return n**- the return keyword is what your method actually gives you after being invoked. This also escapes the method so any code following between return and end won't be executed.

`end`

**end**- closes the method definition.

-***Java***

`public static int returnNum(int n) {`

**public**- access level of the method. Public allows pretty much anything to access/invoke the method.

**static**- defines this as a class method.

**int**- defines the return type of the method. This method will return an integer.

**returnNum**- the name we're assigning to the method.

**(int n)**- defines the type (integer) of the variable representing the data we will pass to the method as an argument. This restricts us to only being able to pass integers to this method.

**{**- opening bracket to the code block of this method. All code between this and the following } will be executed when this method is invoked.

`System.out.println(n);`

**System.out.println(n)**- this whole line performs the same things puts does from Ruby. It prints whatever follows (n in this case) to the terminal output. This is a little more in depth as I'm not breaking down each thing between the dots. Quickly, System is class, out is an instance of PrintStream which has a println() method we can access. println() is a method that executes code just like our returnNum() method.

**;**- statements in Java must end in a semi-colon to inform the language the statement has ended.

`return n;` - again this is the same as with Ruby. The return keyword is what your method actually gives you after being invoked. This also escapes the method so any code following between return and end won't be executed.

**}**- closing bracket which gives Java the boundaries of the method.

I don't know about you, but one of those is much more readable to me. I'm sure this has a lot to do with the fact I was taught Ruby first. 

I can see benefits for the way both langauges are structured to function. Ruby's version is easier to read and far more flexible in my opinion. Flexibilty and modularity are both huge selling points for me. 

Java's version is both more explicit (if you know what you're looking for) and clear to what the purpose of the method is. It's also more rigid with the requirement of a typed return and typed parameter, but that also makes it less prone to bugs. I'm arguing it's less prone to bugs because the Ruby version (in its current implementation) has no control to stop us from passing something to it other than a number. Whereas if we tried to pass a string to the Java method, we'd get an error and we wouldn't even make it into the method body. This is important because if you're counting on the method return_num/returnNum to actually return you a number, only one of these two methods currently guarantees that's what you'll get.

I think that's enough for today. I'm really enjoying Java at the moment so I'm going to ride this motivational wave for as long as I can and keep pushing into the language. It has a lot of potential to set me apart from other bootcamp grads that haven't explored another language yet and as one of most widely used languages out there I know it isn't a wasted effort.

If you find yourself interested in Java go ahead and check out Codecademy's [free course](http://www.codecademy.com/catalog/language/java) on it (I'm super enjoying it so far) or head over to [Udemy](https://www.udemy.com/courses/it-and-software/) and see if you can find something of interest to you there!


