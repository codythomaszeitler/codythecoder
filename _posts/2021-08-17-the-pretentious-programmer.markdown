---
layout: post
title:  "The Pretentious Programmer"
date:   2021-08-17 18:43:02 -0700
categories: jekyll update
---

Bloodletting was considered the defacto practice [for about a span of over 2,000 years][bloodletting]. For a long time, doctors would treat sick people by cutting them and letting the "illness" spill out of them. A signficiant portion of the population at the time took this as a truth, influenced by nothing only be sometimes someone would get better by doing it. This was our assumption about the medical profession and caused humanity a great deal of harm.

We have describe the medical system stuck in the dark ages by its own ignorance. Now, let's talk about another human dicipline that is in the dark ages, and could be argued to be just as important, programming. 

Humanity has only been doing programming in any real sense for the past sixty years, and let's be honest, we are still pretty bad at it. Late software projects with bugs that are rigid to extension are the norm, not the exception. 

I am sure there are going to be revolutions about how we think about programming in the next hundred years, and the way we are doing software now is going to be completely different in one-hundred years. Most likely, how humanity currently thinks and does programming is going to be different, thus, what you are doing today is most likely wrong! By the way, if you do not believe that things are going to be drastically different, note that [about one in three software projects fail.][jekyll-docs] Someone somewhere is going to get this right (there's a definite market incentive for it), so things will change.

So the following comments are commentary that you hear *today*. This commentary is most likely incorrect because of the immense amount of failures that we face as an industry. The question is *why* are these comments wrong?

`Good lord I hate language X. Obviously the best langauage is Y. I try to do one simple thing in X and I need ten lines, but with Y, you know what, I get it done in three. Three lines are obviously smaller than ten, thus, Y is better. For this project, I will now use Y!`

`Ha! Library X! Nobody uses library X anymore, its all about library Y now. Anyone worth their salt is going to use library Y!`

`Ugh this code is so old and terrible! I mean look how long this function is! Someone quite bright told me that functions should be small, and not just small, but smaller than small. But dear lord, this thing is 30 lines long! This is why our project is late! I can't work with this!`

While all of these statements can have their merit, I am going to make quite the blasphemous statement. I firmly believe that the majority of programmers who state things like this have absolutely no idea what provides value to a stakeholder in terms of their code quality.

Let me clarify, because I firmly believe this statement is going to be drastically misrepresented. I am not saying someone who has uttered the top three statements has never provided anything of value to a stakeholder. They most definitely have. However, in terms of how their code they are missing what gives it an immense amount of value then just doing what the customer asked.

There is one almost one universal value that allows two pieces of code to be compared objectively, which is something that we do not do as an industry. I swear all of our arguments are based off of emotion, not objectivity, which is odd since we are using little logic machines. (I hate anecdoctal evidence as much as the next guy, but every piece of code I have ever been described as being "bad" always somehow gets that credit within seconds of looking at it. You would think it would take years of working with something to truly know if it was bad, and measuring that can be oh so difficult!).

The definition of good code is as follows. This is the definition **because** it saves your stakeholders money:
: Given two implementations, A and B, the objectively better one is the that is easier to change with respect to future user requirements.

> Just one point of clarification, the *with respect to future user requirements* is crucial to understand. You can make tons of statements about something being better than another, however, many of them end up being mute since they don't provide any value in context of your stakeholder. For example, so many people blindly apply design patterns without any consideration if there is any change their stakeholder would ask for that utlizes that design pattern! Most of them are just empty complexity that do nothing but shine the ego of the developer implementing them! Complexity is our greatest enemy! You add it at your own peril! 

So our above three statements, let's review them, but under the context of being easier to change.

`Good lord I hate language X. Obviously the best langauage is Y. I try to do one simple thing in X and I need ten lines, but with Y, you know what, I get it done in three. Three lines are obviously smaller than X, thus, Y is better. For this project, I will now use Y!`

> This statement could have merit *if* choosing langauge Y over langauge X truly gives your more flexibility in terms of how your user talks. Let's say you are comparing Java and C for a stock trading app. In this app, microseconds literally count in terms of getting a trade before someone else. Thus, you need to be in complete control of items like when the execution of your thread is removed and boot up times are critical in order to react to new information about the market. When you are explaining your choice to the stakeholder, your choice should explain that you have the ability to now get execution times below all competitors *if* you were to choose C over Java. Thus, a future change (how fast can we respond to the market) is now a factor into why we choose our language. 


`Ha! Library X! Nobody uses Library X anymore, its all about Library Y now. Anyone worth their salt is going to use Library Y!`

> This statement could have merit *if* library X truly gives your user more flexibility over lanaguage Y. For example, let's look at vue.js versus react. Both are UI libraries that utilize javascript. However, they seem to be the same thing in different clothing. If someone really tries to argue for one over the other, I would love to know how that choice really corresponds to it being better for their end user. The general rule that I follow is *if* you have heard of a language, it's probably pretty good, and most likely can accomplish anything that it's competitor can in terms of your specific domain. People might lose their cool over their comment, but it most likely is true.

`Ugh this code is so old and terrible! I mean look how long this function is! Someone quite bright told me that functions should be small, and not just small, but smaller than small. But dear lord, this thing is 30 lines long! This is why our project is late! I can't work with this!`

> This is one of my favorites. Robert C. Martin wrote a book called clean code. In the book, I would say the central argument is as follows. Every function can be broken down into very small parts (around 1 to 4 lines, where every comment is a failure!). Each of these lines should state some level of abstraction of the problem being broken down (and this concept is what is so butchered by most programmers). However, there is still no empirical evidence that such small functions are actually productive, and if you talk to management of the programmers who are partaking in this practice, they will notice no discernible difference in defects, and more importantly, productivity when someone asks you to add on something (asking for a change!)


**So when we are making decisions about how we are going to construct our system, we should look in one general direction, how does this affect how our user's product is going to evolve over time? Which is not that surpsising of a statement! I mean if you look at the thing we workg with "software" it literally means malleable (soft) product (ware)!**

But wait, Cody, where in the world are you picking up these ideas. How do *you* know that what you are saying is correct!

Good point. I have two credible sources, (one I already stole a quote form above) about why I am right. You may have heard of these two names before:

The first is Robert C. Martin. Uncle Bob's book about clean architecture is a great read, and I highly advise you to do so. Actually, I would almost recommend it over clean code! However, in the opening of the book, he states the comment I may above, that software really means malleable product. Every architectural choice that we make should be making our software as soft as possible!

The second is Dave Thomas. If you do not know Dave Thomas, you are definitley missing out. He wrote an amazing book called the *pragramtic programmer* which any aspiring programmer should read! In the book, he goes through any tips and tricks that programmers can use to give the most amount of business value. In one of these sections, he talks about what makes a good design, and more importantly, how one compares two design choices. The way one compares two designs is which one is easier to change (does that comment seem familiar! It should because it was where I first learned of this principle!). However, I believe I tacked on the fact that it should be easier to change with respect to future user's requirement is what I tacked on.

So why should you care about any of this? This just shows that we as a community need to be much more open about *why* we are right, and not just use dogmatic assumptions instead. The dogmatic assumptions are killing us, and our probably the leading problem behind why almost 66% of all software projects fail. 

I can't tell you how many times even *senior* engineers will come at you with statements that have no merit on the easier to change mantra. Actually, most of the time, when most programmers discuss things I see no relevant objective measure as to which to judge their statements! If no such objective measures exist, how can we ever grow as a community, as a profession?

This is going to keep biting us for decades to come. With how hard it is to actually objetively measure software engineering productivity, this is going to be even harder in the future.

And with that, I leave you. Thank you so much for reading through my first blog post! Hopefully I'll be making one of these every week, so make sure to tune back




So what's the relationship between these two ideas? We are in the genesis of humanity messing with a largely new engineering dicipline. I believe that much of the metaphors that we have used to describe other engineering principles are not applicable to programming. Anyone who has tried to construct a piece of software like you would build a house would be quite sad at the end of their late project.

I mean just look at the amount of dogmatism that surrounds programming languages. Here's a controversial fact. If you have heard of a programming language, there is quite a good chance that there is something good about it. You think javascript is just oh so bad? Well it must have some use given the fact that the entire internet is ran by it. 

You know how Linus Torvalds hates C++ and says that C is better is nearly every single way? If you haven't, you should check it out. Also. check out this intereview from Linus and see how much his programmign 


We are starting to learn that A large amount of the programming population must be wrong, however, it seems that the majority of the programming population is much more dogmatic than what was currently stated by 

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[atlas-code]: https://www.atlascode.com/blog/why-software-projects-fail/
[bloodletting]: https://en.wikipedia.org/wiki/Bloodletting




So cody you been trying to come up with a good starting point about what to write about. Let's see if we can come up with a good one about people being more dogmatic then ones who actually think critically about software and what makes it actually better than another piece of software.

KEEP IT IN THE ABSTRACT AND THEN GO INTO THE DETAILS. MAKE SURE THE STATEMENT MAKES SENSE IN THE TOP LEVEL.

So first we are going to state that humanity when it first starts an endeavor it normally is really really bad at it. 

Okay, so state what the problem is. Why are we talking about what we are talking about? Programmers think they are better than they are, and it's having an immensly negative impact on the industry. 

Now our examples are going to be anecdotal. 

    - There seems to be a common problem of good code getting criticism.e

A long time ago, I was trying to understand what the model-view-controller design pattern. In my search, I happened to stumble upon a very interesting article 

https://blog.codinghorror.com/understanding-model-view-controller/

Now what's super weird about this article is that it seems to be on another planet from what I was able to reconcile what MVC is.

I'll try to give my best shot about what MVC is.

In my mind, there are three parts to MVC. There is the part about why the stakeholder asked you to build the application, this is known as the model. There is the part where you show your stakeholder something pretty to look at it. This is the view. There is another part called the controller which takes events from the view and model and has them communicate.

If you have done MVC properly, the following traits are going to be present. 

At any time, you could switch to a completely different implementation of the view and controller with the model being non the wiser.

For exapmle, if your front end was done 


We could also discuss why in the world we as programmers have such a hard time talking about things.
There seems to be a large issue with proving that another programmer is wrong. You know what would be good to quote here? That Jim? Coplien talk where he states that the person presenting does not know what MVC is.
You know what? This is something that I struggled a lot to understand, and I'll quote someone who I know is almost 100% wrong, but I have no idea. Most programmers don't know how to do MVC. How in the world could I ever know if I am correct?

This was an interesting quote from Robert C. Martin I heard a while back. It simply stated that if a programmer was doing somethinig that was working for hime


You know what would be interesting? The fact that we as programmers do not have a proper 



So now go through some comical examples of this in action. 
nope don't go into too much detail here. keep your argument abstract.

Now you are going to state how we could "rectify" all of these comical examples. You are going to add the following statement:

    - Something, something make it easier to change.
        - Now here is the thing. I would not just state this outright. 
        - We are going to need to cite some sources to make this argument.
          - I believe there are two sources that we are going to have to quote from
            - The first is from pragmatic programmer.
              - I believe the quote is something of the form "How do you know which design is better? It's simply what is easier to change."
              - I believe the second quote is from Robert C. Martin. It is something of the form that software really stands for soft product. If you give me something that works, but I cannot change there it sucks. If you give me something that is easy to change, but is wrong, I can fix it and keep going. 

Okay so now we have asserted what we really want and what the objective measure is. Now, let's get into it. 

- Go in and add the easy to change to the end of all of the examples that were found. Boom! Now we can see that all of those examples do not necessarily lead us to 


