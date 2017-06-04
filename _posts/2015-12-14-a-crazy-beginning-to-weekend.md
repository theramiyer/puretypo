---
layout: post
title: A crazy beginning to the weekend
date: '2015-12-14T04:11:00.000+05:30'
author: ram
tags:
---

Let me start off with a fact: I’m lazy. Yes, I’m lazy to do repetitive tasks, I’m lazy to go pick a new t-shirt, and sometimes I’m lazy to get outta the bed even though I know that’s going to be the cure for my backache caused because of lying in the same position for eight hours. So we get the point.

Another fact: I’m crazy. Yes, I’m crazy about riding my bike in the rain, I’m crazy about gadgets, and most of all, I’m crazy about things that I learn through experimentation—PowerShell has become one of those things of late. So yes, I’m crazy about PowerShell. One major reason for it is that it enables me to be lazy; it takes care of things that I don’t like to do, but have to do.

One such recent thing was getting a list of versions of System Center Endpoint Protection (SCEP) definitions. Now, with the jargon, you would’ve realised that I’m an IT guy in case you didn’t already know. Yeah, yeah, I know: so mainstream. Well, Intel didn’t want to take me in, so I got stuck with this. But hey, an engineer is an engineer put anywhere. I thought of giving IT Infrastructure a shot back in 2010, and I don’t regret the decision.

It all started with a startled waking up from my sleep, just four hours into it on Friday night—which means I slept by 04:00 on Saturday morning (IST) and woke up around 08:13. Why? I don’t know why. This generally doesn’t happen, but this time I got up to write a PowerShell script (I know!)—I’d gotten a small idea and that woke me up from the middle of my sleep.

One of our clients uses SCEP as one of the security solutions in their environment. Like everything we maintain with respect to security, we create a compliance report for SCEP as well. Turns out, SCEP doesn’t have built-in capabilities that are similar to Forefront Client Security (FCS) which gave you a neat list of definitions received from Microsoft and the ones installed. Well, either that, or we still have to work on that—SCEP is not really my department. Yet. So the last time we tried to create the compliance report (which is the first of the kind we’re doing that is similar to the ones we had with FCS and one that we could send across to the executives rather than just circulating among us geeks), we had a tough time getting the version details from the Microsoft website—the whole thing felt really clumsy.

So I fired up www.followthatpage.com and fed it with the URL to the What’s New page for SCEP. That was nifty—Follow That Page checked the SCEP page every hour and sent an email if it found any changes within the block of text that I’d specified. But I didn’t want to give it my official email address because it’s not a good practice, so I gave it my personal one and set up my personal mailbox to forward the notifications to my official mailbox. But that sent about three to eight emails a day, and I had to copy that text and maintain a separate Excel for reference. I didn’t like that—that was something I hated. So I thought of writing a script that could read my inbox and then do something with it. By the time I could figure it out completely, it was time to leave for the day.

Now I admit that the idea that I got isn’t all that cool, or maybe it’s common sense, but being new to PowerShell, this was exciting to me. So I thought of getting it to read my emails and then configure it to maintain a version table. The problem there was that to use Exchange Web Services, the script needed my credentials, and worse, to make it run non-interactively, I had to feed in my password in plain text! Heck, NO!

I slept off after trying to break that apart. Four hours and I got up and was like, “You moron, the data comes in from a web page. Why can’t you make the script read a web page instead of doing all the crap that you’re doing? What were you thinking!” Of course! That’s sheer stupidity! But wait, was it possible to get a script to read a web page? Ideally it should be, but then, how? I follow this G2G thing when I get stuck—Go to Google. LOL. Some kind gentleman had put up a whole post about how to make your script read a web page. Possessing a basic understanding of HTML, it was child’s play for me to get my script read a web page. The next part was tricky: to get it to select just the version and the time of release, which were placed significantly far from each other on the web page, among other things that I don’t really care about in this context.

StackExchange came to the rescue. I put up the query on the site and a couple of guys commented on it with the solution. It’s some RegEx (Regular Expression)—something that apparently is different in different languages. But the idea being the same, I just had to copy the solution and paste it to retrieve the version. I constructed my own RegEx for the date—I’d by now learnt that, so no issues there. The next step was to create a hash table and feed it with these values and then append a CSV file with that. No big deal, especially after the “PowerShell for Beginners” training that I attended. Finally I was done with that. A little teaser on Slack and I was dandy. Gloating about it, I looked at the clock—10:35. Not bad at all! Oh wait, I had to call my friend so we could prepare to start from Kathriguppe to Kalyan Nagar (across the city—or halfway around, in this case).

Oh, and here’s the code if you’re into that kinda stuff. PowerShell gods, please forgive the trespasses of this mere mortal—I’m still a beginner, so the code might be a little dirty.

<script src="https://gist.github.com/theramiyer/a09444caaa60bb64b48c.js"></script>

All set, we got a bus from Kathriguppe at 11:45—bus services suck in Bangalore, sorry. One of our friends, Karubé, was treating all the team members for her new job. So after a 270-minute ride, we reached Kalyan Nagar—pretty close to my workplace. Lunch done, I called another friend of mine, Veena (a Blogger friend, who owns and writes [this awesome blog](http://www.merakipost.com/)); she had invited me over for a poem recital at Koramangala (that’s too many K’s for a day—Kathriguppe, Kalyan Nagar, Karubé, Koramangala). Dr Neal Hall was reciting. It was interesting to see someone being so angry about something in such a channelised way, and boy, the clarity in his thought! It was an amazing experience—it was the first time I saw a real-life established poet in my life. Veena then invited me over for her farewell barbecue party.

So from there, we rode to Indiranagar. I knew no one at her workplace, so I was like the kid on his first day at school. I just watched them talk—and for the first time in my life I did that—usually I’m the talker and the entertainer. Again, something really new, but interesting. Oh, Veena’s boss’s mum had made some great marinating sauce—the barbecued paneer tasted just amazing. It’s a shame I didn’t have enough space for it since I had a heavy lunch, that late. I’m really bad at remembering names, but I remember Muzamil (the boss guy who has a Kawasaki Ninja, by the way), Komal (I could borrow some of her energy myself… LOL) who is perhaps the female version of me: the talker and the entertainer, free of all inhibitions; Alicia, and the girl whom I’m not going to name, that I got a crush on (for her wonderful smile). Well, that’s all I remember at the moment. Really bad at names.

What was next, the ride back home! You’d think, for a city whose public transport pretty much shuts down by 22:00, it would be difficult to travel at 22:15, but you’d be wrong. This is the time transportation is much better (unless luck isn’t favouring you for some reason). Forty bucks and I was home, 18 kilometres away, in an hour. Yes, I had to take three cabs back to back, but I was home in one piece.

Overall it was a crazy day, but crazy good. I enjoyed every bit of it. Thanks to Karubé for taking us to the restaurant that served one of the best pastas I’d tasted on that side of Bangalore (because our cafeteria pasta sucks), and a hat tip to Veena for the wonderful, wonderful evening. Yeah, I missed on my labs and had to rush through them on Sunday, but I promised her I wouldn’t blame her for that. So… :p

Ciao, people! Have a good day!