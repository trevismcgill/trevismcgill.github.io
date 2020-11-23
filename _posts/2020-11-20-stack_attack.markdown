---
layout: post
title:      "Stack Attack"
date:       2020-11-20 23:00:00 -0500
permalink:  stack_attack
---


It's hard to believe that we're at the end of module 4 already. About a month ago we began our journey into Javascript and to say it was a frustrating experience would be an understatement. After 3 months of Ruby, moving onto another language was difficult, though not as difficult as I had anticipated. Fortunately, we had an established foundation and certain things carried over very easily. Terminology and "how-to" do things were similar enough -functions execute blocks of code, arrays contain multiple elements and are iterable, and objects/hashes contain key: value pairs.

Those basic principles made it easier, but we also faced the pitfalls of the differences. JS is less standardized than Ruby. You need to learn to read and write functions in a handful of different ways. There are multiple ways to declare variables, all with their own subtle differences. Then there's the nightmare that is the whole fetch/promises/.then/await/async cluster of confusing. This was also the first time I've tried to learn/experiment with HTML and CSS more than the minimum so I needed to learn that too. Even all of that doesn't account for the transition that this was our major endeavor in working with multiple stacks. 

Oh... I almost forgot about the whole JS functional vs. object-oriented programming paradigm. Yay.

I guess at this point it makes sense for me to quit whining and TRY to discuss something useful.

I suppose I'm going to attempt to go over promises. I don't really even want to try to explain them, but asynchronous JS is probably what I've struggled and wrestled with the most during this project so here goes nothing.

Let's begin by tackling the difference between asynchronous and synchronous. 

In my usual method I'll give you the detailed documentation [here](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing) and give you my short and sweet summary of it.

> -Synchronous code fires off, finishes in order, and then moves on.
 
> -Asynchronous code fires off, moves on, and comes back when it's finished.

For me, this has been a double-edged sword. Asynchronous is convenient because it helps spread out the work of your code and allows things to "process" while JS goes about completing other tasks. Which sounds great right? And it is for sure. It alleviates the problem of your code hanging on a time consuming request. However, in my case it was too fast.

Wait --too fast?

Indeed! 

The issue I ran into multiple times were when my functions were attempting to use some data, but when they went looking for it, that data was nowhere to be seen. I had functions that were fetching to my backend database for data and then using that to instantiate JS objects from that data. My functions following my fetch call were then using those newly created JS objects to add HTML elements to the DOM. That's quite hard to do when the JS objects you're looking for haven't don't exist yet.

I'll show you a little more of what I'm talking about. Take a look.

First let's declare a variable for a new array at the global scope.

```
const newArray = []
```

We're going to want to do something with that array. Let's now create a function to manipulate our array.

```
function populateArray(array) {
    array.push(1,2,3)
}
```

The plan is to pass newArray to our `populateArray()` function with the end goal of `newArray = [1,2,3]`

This is where we can take a look at promises.

A promise is JS' way of performing asynchronously and what allows it to escape a function, move forward in the code body, and return to that function once that promise resolves.

Let's make one of those now.

```
const newPromise =  new Promise((resolve, reject) => {})
```

I don't really care about the reject in this use case so let's get rid of that and give some actual use to our promise.

```
const newPromise = new Promise((resolve) => {
console.log('Promise Initialized')
setTimeout(() => {resolve(populateArray(newArray))}, 5000);
```

Here we are artificially creating a response time using `setTimeout()` (just to delay things) and then it will fire off our populateArray function which we are passing our empty global array. The promise will be fulfilled and resolved after a delay of 5 seconds. The `console.log` is just so we can see when the promise starts.

With that done, let's create an async function (a function that obeys the whole asynchronous/synchronous paradigm) and can utilize the await keyword. We're also going to pass it a promise when we call it.

```
async function testPromiseAwait(promise) {
  console.log(newArray)
  await promise;
  console.log(newArray)
}
```

The await keyword, as may seem obvious, tells the block of code following await to wait until the code to the right of await returns a fulfilled promise. That was kind of tongue twistery. Sorry :/

You can see we are console.log'ing' our global array before and after the promise. 

Now let's finally go ahead and call our async function passing to it the promise we created and stored in the variable `newPromise`.

```
testPromiseAwait(newPromise);
```

Watching our console we get

```
Promise Initialized
[]
```

And 5 seconds later

```
(3) [1,2,3]
```

Awesome!!! Our function is reading newArray as an empty array, waits for the promise before looking at the array again, and upon a fulfilled promise, executes the rest of the code block where we saw that our same `newArray` variable now has data in it.

The implications of this is that we can allow JS to be asynchronous until we really need it to perform synchronously. An example here is if we want to do something with the data in `newArray` we need to make sure that array has data in it, otherwise well, we won't find anything. And that's exactly what would happen if we were to do 

```
console.log(newArray)
newPromise
console.log(newArray)
```

expecting JS to act synchronously.

*My console here reads out Promise Initialized first (and also in the previous example) despite console.log(newArray) being called first. I'm assuming JS sees a promise and runs it first expecting it to take longer than other code. Further investigation necessary*

```
Promise Initialized
[]
[]
```

However, as we can see, `newArray` is empty at both calls even though the second call follows our variable of `newArray`. This is because JS 

-looks at newArray, it's empty
-reads the `newPromise` variable which executes, but since we are creating a new promise, it escapes and moves to
-our second console.log, which is now called before `newPromise` resolves the promise we created.

If we were to check `newArray` 5 seconds later though, we'd see that data populated the same as before.

So, there you have it, a real quick summary of how asynchronous JS performs and how we can use promises to properly order our code. Hopefully it can be of some use to you and potentially save you much of the headache I experienced!


