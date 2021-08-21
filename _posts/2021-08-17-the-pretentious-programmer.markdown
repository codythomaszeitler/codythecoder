---
layout: post
title:  "The Pretentious Programmer"
date:   2021-08-17 18:43:02 -0700
categories: jekyll update
---

### The Pretentious Programmer

Bloodletting was considered the defacto practice [for about a span of over 2,000 years][bloodletting]. For a long time, doctors would treat sick people by cutting them and letting the "illness" spill out of them. A signficiant portion of the population at the time took this as a truth, influenced by nothing only be sometimes someone would get better by doing it. This was our assumption about the medical profession and caused humanity a great deal of harm.

We have describe the medical system stuck in the dark ages by its own ignorance. Now, let's talk about another human dicipline that is in the dark ages, and could be argued to be just as important, programming. 

Humanity has only been doing programming in any real sense for the past sixty years, and let's be honest, we are still pretty bad at it. Late software projects with bugs that are rigid to extension are the norm, not the exception. 

How we "do" programming is most likely going to be drasticaly changed in the next centenanial. Most likely, how humanity currently thinks and does programming is going to be different, quite different! Thus, what you are doing today is most likely wrong! By the way, if you do not believe that things are going to be drastically different, note that [about one in three software projects fail.][atlas-code] Someone, somewhere, is going to get this right (there's a definite market incentive for it), so things will change.

So what's going to be in this article? We are going to be discussing some of the pervasive ideas that are alive in software today and how they are currently articulated. They are articulated poorly, without any objective way to truly measure if what you are doing is helping or hurting. We are going to show how we can take these statements and truly transform them into something that is helpful and not just dogmatic. We are going to seeing how we can transform the pretentious programmer of today who can offer real value in terms of code quality for tomorrow!

So the following comments are commentary that you hear *today*. This commentary is most likely incorrect because of the immense amount of failures that we face as an industry. The question is *why* are these comments wrong?

`Good lord I hate language X. Obviously the best langauage is Y. I try to do one simple thing in X and I need ten lines, but with Y, you know what, I get it done in three. Three lines are obviously smaller than ten, thus, Y is better. For this project, I will now use Y!`

`Ha! Library X! Nobody uses library X anymore, its all about library Y now. Anyone worth their salt is going to use library Y!`

`Ugh this code is so old and terrible! I mean look how long this function is! Someone quite bright told me that functions should be small, and not just small, but smaller than small. But dear lord, this thing is 30 lines long! This is why our project is late! I can't work with this!`

While all of these statements can have their merit, I am going to make quite the blasphemous statement. I firmly believe that the majority of programmers who state things like this have absolutely no idea what provides value to a stakeholder in terms of their code quality.

Let me clarify, because I firmly believe this statement is going to be drastically misrepresented. I am not saying someone who has uttered the top three statements has never provided anything of value to a stakeholder. They most definitely have. However, in terms of how their code they are missing what gives it an immense amount of value then just doing what the customer asked.

There is one almost one universal value that allows two pieces of code (maybe *implementation* is the better way to word it) to be compared objectively, which is something that we do not do as an industry. I swear all of our arguments are based off of emotion, not objectivity, which is odd since we are using little logic machines. (I hate anecdoctal evidence as much as the next guy, but every piece of code I have ever been described as being "bad" always somehow gets that credit within seconds of looking at it. You would think it would take years of working with something to truly know if it was bad, and measuring that can be oh so difficult! But nay, it normally is decided within a few moments time).

The definition of good code is as follows. This is the definition **because** it saves your stakeholders money:
: Given two implementations, A and B, the objectively better one is the that is easier to change with respect to future user requirements.

> The *with respect to future user requirements* is crucial to understand. You can make tons of statements about an implementation being better than another implementation, however, many of them end up being mute since they don't provide any value in context of your stakeholder. For example, so many people blindly apply design patterns without any consideration if there is any change their stakeholder would ask for that utlizes that design pattern! Most of them are just empty complexity that do nothing but shine the ego of the developer implementing them! Complexity is our greatest enemy! You add it at your own peril! 


So now we have three statements that *maybe* most of have heard (I know I sure have!). But let's see them in a different light, a light not normally undertsood by many programmers. Let's see them in the light of being *easier to change*.

`Good lord I hate language X. Obviously the best langauage is Y. I try to do one simple thing in X and I need ten lines, but with Y, you know what, I get it done in three. Three lines are obviously smaller than X, thus, Y is better. For this project, I will now use Y!`

> This statement could have merit *if* choosing langauge Y over langauge X truly gives your more flexibility in terms of how your user talks. Let's say you are comparing Java and C for a stock trading app. In this app, microseconds literally count in terms of getting a trade before someone else. Thus, you need to be in complete control of items like when the execution of your thread is removed and boot up times are critical in order to react to new information about the market. When you are explaining your choice to the stakeholder, your choice should explain that you have the ability to now get execution times below all competitors *if* you were to choose C over Java. Thus, a future change (how fast can we respond to the market) is now a factor into why we choose our language. The statement above about numer of lines is fine for doing simple scripts, but in all honesty, when you have programs that stick around for twenty years or so (which happens for business specific applications quite often) I find no issue adding seven more lines if in the future more lines can be added without a large headache!


`Ha! Library X! Nobody uses Library X anymore, its all about Library Y now. Anyone worth their salt is going to use Library Y!`

> This statement could have merit *if* library X truly gives your user more flexibility over lanaguage Y. For example, let's look at vue.js versus react. Both are UI libraries that utilize javascript. However, they seem to be the same thing in different clothing. If someone really tries to argue for one over the other, I would love to know how that choice really corresponds to it being better for their end user. The general rule that I follow is *if* you have heard of a language, it's probably pretty good, and most likely can accomplish anything that it's competitor can in terms of your specific domain. People might lose their cool over their comment, but it most likely is true. **This does not mean that there is not a time and place to actually choose one over the other, but most of the time programmers don't even know enough about each to even make that distinction**.

`Ugh this code is so old and terrible! I mean look how long this function is! Someone quite bright told me that functions should be small, and not just small, but smaller than small. But dear lord, this thing is 30 lines long! This is why our project is late! I can't work with this!`

> This is one of my favorites. Robert C. Martin wrote a book called clean code. In the book, I would say the central argument is as follows. Every function can be broken down into very small parts (around 1 to 4 lines, where every comment is a failure!). Each of these lines should state some level of abstraction of the problem being broken down (and this concept is what is so butchered by most programmers). However, there is still no empirical evidence that such small functions are actually productive, and if you talk to management of the programmers who are partaking in this practice, they will notice no discernible difference in defects, and more importantly, productivity when someone asks you to add on something (asking for a change!) Now its normally good to have smaller functions, but sometimes, breaking them down to a fine grained level can actually make things *harder* to work with!


**So when we are making decisions about how we are going to construct our system, we should look in one general direction: how does this affect how our user's product is going to evolve over time? Which is not that surprising of a statement! I mean if you look at the thing we working with "software" it literally means malleable (soft) product (ware)!**

But wait, Cody, where in the world are you picking up these ideas. How do *you* know that what you are saying is correct!

Good point. I have two credible sources, (one I already stole a quote form above) about why I am right. You may have heard of these two names before:

The first is Robert C. Martin. Uncle Bob's book about clean architecture is a great read, and I highly advise you to do so. Actually, I would almost recommend it over clean code! However, in the opening of the book, he states the comment I may above, that software really means malleable product. Every architectural choice that we make should be making our software as soft as possible! (e.g. as easy to change as possible!)

The second is Dave Thomas. If you do not know Dave Thomas, you are definitley missing out. He wrote an amazing book called the *pragramtic programmer* which any aspiring programmer should read. In the book, he goes through any tips and tricks that programmers can use to give the most amount of business value to their stakeholders. In one of these sections, he talks about what makes a good design, and more importantly, how one compares two design choices. The way one compares two designs is which one is easier to change (does that comment seem familiar! It should because it was where I first learned of this principle!). However, I believe I tacked on the fact that it should be easier to change with respect to future user's requirement.

So why should you care about any of this? This just shows that we as a community need to be much more open about *why* we are right, and not just use dogmatic assumptions instead. The dogmatic assumptions are killing us, and our probably the leading problem behind why almost 66% of all software projects fail. 

I can't tell you how many times even *senior* engineers will come at you with statements that have no merit on the easier to change mantra. Actually, most of the time, when most programmers discuss things I see no relevant objective measure as to which to judge their statements! If no such objective measures exist, how can we ever grow as a community, as a profession?

This is going to keep biting us for decades to come. With how hard it is to actually objetively measure software engineering productivity, this is going to get worse before it'll get better. We need to start measuring code quality effectively and have real conversations between developers if our pratices and tools are actually helping us. Good code and bad code can so easily be swept under the rug, we need to bring out these discussions about what makes things good and bad into the objetive, non-dogmatic sphere. Looking through the lense of being *easier to change* 

And with that, I leave you. Thank you so much for reading through my first blog post! Hopefully I'll be making one of these every week, so make sure to tune back to see my rants about software engineering!

[atlas-code]: https://www.atlascode.com/blog/why-software-projects-fail/
[bloodletting]: https://en.wikipedia.org/wiki/Bloodletting