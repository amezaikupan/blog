---
layout: post
---

I've been interested in looking into my productivity on the computer for a while. It spark from my encounter with Andrej Karpathy 's [uLogMe](http://karpathy.github.io/2014/08/03/quantifying-productivity/). I was completely amazed, so much so I switched from using Window to Debian 12 to run the program. And... it was buggy. It's understandable since the code was written like 10 years ago, and because I didn't have the skills back then, I couldn't update the code. (Still a undying project idea till this day)

But I still keep the question in mind. Slowly, I learn to break down ideas. From:

> "I want to know what I do on the computer"  

(Notice the idea is extreamly vague. With a prompt like this, I wouldn't know how to start with anything at all. What do I mean by 'on the computer'? Like screen time? How many app I use on the PC? How much time I spent on Youtube and go work and come back for a short but last for at least 45"?)

> "I want to know how I use the web browser"   

(Now I know the objective is the web browser... But what is next? I spent at least a year fiddling with this so call idea in the back of my mind until I realize that I won't be able to do anything with ideas that don't have a direction - that is to say, **make everything a question**)

> What can I know from analyzing 1 week worth of my internet browsing history?

And this is the result of that assignment

## 1. Methodology 

I used `Export Chrome History` extension on Chrome to export my browsing data (I tried exporting with Google Export but it takes like 3 days to get the data). The data only go as furhter back as 6 months. 

Browing data only record website visited and time stamps. There are other features such as `visitCount` and `typeCount` but I don't undrestand how that data is collected so I didn't use them. 

## 2. Questions and answers 

There are several interesting insights that is quite intersting. 

<!-- Picture of top 10 websites  -->

This is the **top 10 websites that I visited in the week**. There are some websites that I visit **everyday** of that week, and some only a few days. It seems that the websites that I visit everyday are more likely to be a general website where I would hop in and out daily (so... I guess I visit messenger and youtube everyday... I didn't notice that)

If we take the *you visited this website half of the days in the week* metric, I am a regular of 7 websites.  And if we take the *you visited this website everyday in the week*, I'm a sucker for 3. 


<!-- Heatmap of time online  -->
<!-- 
It seems I wasn't online a lot of the time this week. Look closer, there subtle details that I noticed:
- I stayed up passed midnight on ... day. Must have been working on something. (I often go to sleep by that time)
- I usually start the day at around ___ 
- There are gaps in the day indicating breaks - it seems like my *computer attention* lasts about 3 hours. 
- There are also gaps in the week - some highs some lows between the day. This may represent my osilation between desk work and other stuff in life (maybe errands to go to/people to meet).  -->

Next, **when was I online during the week?** 

Looking at the graph, I am also reminded of how each hour is associated with some kind of feeling. I think the most sensitive time of the day is sunrise and sunset. The sunset in around 5-6PM here, and I am often AFW then (there is always an urge to go outside). Or at 10-11AM - which is lunch time to me. Or midnight - which is bedtime for me (though I sometimes stay up late if I got carried away)

This result in a pattern on my online activity. I suspect there might be a similar pattern for days of the week - as to me there are also certain associative feeling for each day of the week. 

At this point I was face with 2 option: exploring more closely what I do in a day vs exploring my usage of certain website. 

I find it difficult to code a good graph that represent **daily browsing**. In the end, this is the graph that I end up with. 

There isn't much to comment upon this graph other than *oh, so that's how that day been*. 

For the by website graph, using the heatmap in combination with a line graph give you more insights into your activity in certain sites, with just some simple filtering!

## 3. Final thoughts 

Before this exercise, I thought doing this would help me solve every problem I have regarding my *bad browsing habit*. I thought I would find some bad patterns in my behavior and stop them. But I was wrong. Mid-way through with the project, I fall in a pit of hopelessness as I often do. 

*What is the point of this anyway?* - I asked. 

I realize I can't change my behavior like this. If anything, I was just climbing the first rung of the *Causal Ladder* - observation, and I am aware now that I can't find any definative truth just from seeing more. 

Though in the end, I did find value in doing this project. I made my history into something tangible that I can reason about clearly and communicate with my friends (it's suprisingly useful because it help me remember the last week on my Saturday review - I forget A LOT). 

For further development, I think making a web app for visualizing my history is a **solid good idea** (I would paid for this service if software is good) even with just the above graphs - but more pretty of course. It will be really good for when you have to check what you have done a specific day or when you're doing review. Further further maybe someone will make an LLM agent that can read people history and spot their pattern, but maybe that's a bit crossing the line in term of privacy. 



