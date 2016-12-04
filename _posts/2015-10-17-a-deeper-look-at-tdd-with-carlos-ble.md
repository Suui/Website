---
layout: default
title: "A deeper look at TDD with Carlos Blé"
---

On this year’s July, I was lucky enough to get into a 3 days TDD course by [Carlos Blé](https://twitter.com/carlosble) with my friends [Ronny](https://twitter.com/RonnyAncorini) and [Miguel](https://twitter.com/Groxalf_Esp). I cannot thank Carlos enough for giving us this opportunity, as it was an inflexion point and a total eye-opener regarding TDD for me. Even though I was already a TDD practitioner before, my way of doing TDD changed a lot after the course.

The way Carlos imparted the course was very practical and easy to follow, I also got to meet [Néstor](https://twitter.com/nestor_bs), [David](https://twitter.com/testrightnl) and [Jeroen](https://twitter.com/AngusVB), the other participants. The experience wouldn’t have been the same without them, we all together had really interesting debates, shared opinions, and took the conversation over to the restaurants where we had lunch every day. Everyone contributed to end up having some unforgettable moments.
But let’s get into some of the things we were able to learn!

#### XP Values and Practices
The first thing we got ourselves into was the **eXtreme Programming values**:

* Simplicity
* Communication
* Feedback
* Courage
* Respect

The whole point of the **XP Practices** is to obtain one or more values. **Pair programming** brings excellent and instantaneous feedback, communication and can contribute to respect and courage. **Test Driven Development** brings probably the best feedback available, and can lead to simplicity. PP and TDD are at the core of the XP Practices among many others and were the main focus of the course.

#### Clean Code
At the time I wasn’t as much into Clean Code as I am now and I was able to discover one of the principles I really believe has to be respected, which is **The Less Astonishment Principle**. Basically, it would be nice if the code that you read acts as you expect when reading it. **No surprises!** You’ll be applying this principle as long asthe reader of your code doesn’t run into surprises. Even though I’ve found It hard at times, I feel it’s worth spending the time trying to find a solution that respects the principle.
**Good Naming** is key to respecting the Less Astonishment Principle and making your code easy to read for others.
**Duplication vs Abstraction** was also mentioned: duplication is bad, but a bad abstraction is worse.

#### Pair Programming
A really interesting fact that Carlos mentioned was: “Navigators, don’t become the IDE”. I’ve paired with people who don’t let you think about what you’re doing while driving. As soon as you miss a comma or a semicolon they’re like: “Hey! You missed that one!”. That’s not bad, and I’ve also made those remarks at times. But that’s something the IDE will tell you as soon as you’re writing it.

The navigator’s role is different. Navigators are not there just to check that you’re writing your code without errors. Navigators should get notes, and be one or two steps ahead of the driver. While the driver is trying to pass a test, the navigator is thinking about the next one. He is also checking naming and taking notes on possible enhancements for the refactor step.

But he won’t interrupt the driver’s work! In fact, he will patiently wait until he finds the right moment to give his opinion and discuss the possible changes to the code the driver has just written. I now find being the navigator harder than being the driver, but anyways, PP is about ***flow***. It takes a lot of practice for a pair to get a really nice flow going on and taking the PP experience to its best.
Carlos wrote a [really interesting blog post](http://www.carlosble.com/2015/07/productive-pair-programming/) about that PP matter that is totally worth checking out.

#### Finally, Test Driven Development!
**The TODO list!! **I can’t stress it more! I never wrote a single TODO list back then. But this is for sure one of the **key elements **to get a nice and straight-forward TDD session. Writing a TODO list makes you think about what you’re testing, makes you understand the **Domain** better and gives you a general idea about the steps you’ll be following, the order of your tests. Spending your time in the TODO list will result in a better flow while doing TDD, as the questions that you may ask yourself between tests have already been treated before while making the TODO list.

**Baby Steps! **This is also a really important one on TDD, but it’s not that easy to achieve. Being able to get the right baby steps can be hard, but practice will help you on discovering the right baby steps. I was blown away by a word wrap kata resolution by Carlos in the course, which you may say magically resolved itself. All Carlos did was choosing the right baby steps, as he clearly stated and repeated a few times thereafter.

The **30 seconds rule** that can be extended to an **X seconds rule**, can help you determine whether the test you are trying to pass is the right one by setting up a time limit for passing it. You’re trying to pass a test, it should be done in less than 30 seconds, otherwise this is probably not the test you should be passing now, there probably is another or a shorter baby step you can make. Sometimes, there won’t be, but asking it to yourself will make sure you’re on the right path. You should be spending more time thinking about the right tests than passing them.

**Making sure the test fails for the right reason before trying to pass it **is quite the important thing, you may write a test and find it green before trying to pass it. What is going on? You should check that one. You also want to make your tests fail for a **single reason**, which leads to more simple, clear and easy to pass tests (I must thank **Ronny** for recalling this one for me as I usually forget it!).

**Red, Green, Refactor** revisited. Refactor means altering the code without changing its behavior. However, previous to the course, I didn’t associate refactoring with **generalization**. Passing the tests with minimum effort often leads to “not-so-nice” solutions. It is here, at that refactor moment, when you should generalize your various minimum efforts into a nice code that groups them all. If you’ve chosen the right baby steps, the generalization will come naturally. Something worth looking at is the **Transformation Priority Premise**, which was also mentioned during the course. You can check its whole in [this article](https://blog.8thlight.com/uncle-bob/2013/05/27/TheTransformationPriorityPremise.html) by [Uncle Bob](https://twitter.com/unclebobmartin), however I find it hard to get without some help from a mentor.

#### Afterword
Overall, a great experience. In about 20 hours over 3 days, I learned a **ton** of stuff and even though I tried writing about those here, this is just an overlook of what the course truly was, as the key to open a new world of debates and discussions between me and my friends, leading to a hell of a lot of enhancements in our way of coding.

Not to mention that the bowling game with Carlos was priceless, hahaha! A lot of coding, learning and fun, what else would you ask for!
