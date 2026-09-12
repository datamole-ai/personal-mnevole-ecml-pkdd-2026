It's possible to try to finish in 30, 40 minutes, so we have 1, 2 questions for—

 All right. Thank you so much. My name is Marian D'Ruzzo, and I'm a professor of the data science at the University of Toronto, Sydney, in Australia.

 This presentation today—Brexit means Brexit—is a joint work with Christina Lajon from the University of Sandton here in the audience, and our two very good master's students from a couple of years ago. So what we're doing today: we are looking at the following question.

 Does engagement with opposing teams change political opinion online? So if you think a bit about this, most of the state-of-the-art—not most—of the research created work studies opinion dynamics and scam tradition in what we call broadcast platforms, so micro- or microblogging, things like Twitter, X, where there's a couple of—there's a couple of dynamics there.

 One: on these platforms, opposing camps actually cluster around clusters of hashtags, which—and their repeats—usually signal engagement and endorsement, which means then that users rarely encounter any resent. You can actually leave on Twitter, write a full opinion, or repeat to the other opinion in their account.

 However, Reddit is more of a structured discussion forum, right? So there, opposing users will talk in the same threads.

 They—Reddit is also pseudonymous, so the social cost of engagement is actually lower. So if there's any way where encountering and exchanging with opposing users has any impact, it should be Reddit.

 And, as spoiler alert, we don't find that, and I will tell you why. The reason is actually more—more structured than anything.

 So here's what—here's what I need to solve in order to address my problem. First of all, I need to—the first question is: can I reliably extract the stance or the attitude of a user towards a political discussion?

 So essentially, this is the typical stance we can choose. The second problem we need to solve is getting user-level stances from these dispute labels, and then avoiding the noisy labels.

 The third thing: I want to—I want to spend a bit of time around looking at the attrition, which introduces a selection bias when you're doing the long-term studies. And I'm going to show you why the third one is the most important one.

 What do we do this on? Our dataset is the Brexit dataset.

 There we have the title of the paper, Brexit means Brexit. We got about 871,000 submissions, posted between November 2015 and February 2021, which is the duration of the Brexit saga.

 We have manually split this into 27 distinct political camps. And we use offline events, things like, you know, a discourse by the Prime Minister's recent name, or some post, or a government.

 Now, in order to achieve the stance detection, the first thing we did: we did manual crowd annotation of stance using Amazon Event Viewer. So we have—we have labeled more than 5,000 items with three polarities: against Brexit, pro-Brexit, and neutral, with an inter-annotator agreement of 0.8.

 So how did we do this? First of all—first of all, we used 800 annotators for each post.

 So we showed the annotators an interface where we show them the full comment thread, the comments. We've done parameter sweeps of the—the hyperparameter sweeps, things like worker qualification, their location, country, prior performance.

 Now, one thing we didn't plan for, and everyone that works at Amazon Event Viewer probably by now knows: we had to fight malicious workers. There is an entire class of workers on Android whose purpose is to give false random quick answers, and they get their money and they walk away.

 So the way we detected these guys is by using majority agreement proportion. So we essentially looked at workers who, in average, their work was very far away from the average work of their—of their peers in the same job, and then we just took them away and we threw it away.

 And finally, we wanted to also isolate posts that were very intrinsically difficult. So we selected posts where—where we couldn't get an agreement of at least 5, 5 of our annotators, which then takes us to the final inter-annotator agreement of 0.8.

 I'll pause here for a second just to let you know that the dataset, the code, and the annotations are actually available for free on GitHub. So this is—if you want to—if you want to reproduce this or do some more work, it's available.

 All right. So the first question: how well can I get the polarity of the stance using—off-the-shelf?

 The first thing we did: we didn't want to do a lot of—we obviously tried what was already existing. We took a feature-strength stance classifier, we put it in our data, and we thought, we're just going to introduce this strictly random results.

 Then we tried slightly—slightly better. We—we—we classified classifiers as the end-ready attribute decision trees on top of a—of a vector representation of the text, and it worked a little bit better.

 Then we—then we tried encoder basis. So we—we created a dense encoding of the—of each message using the BERT core encoder.

 We tried BERT, the base cert, the—the version called BERT_lead, which is fine to the moment we do. And then where we got the best performing—there we got—was something we called BERT_ready.

 We started with BERT_base, we further pretrained it with one of our data, so we created an in-context BERT encoder, and then we added a final fine-tuning. And we got a—a final F1 of 0.55.

 This is a very difficult problem. This is a very difficult problem.

 That's why it's worth it. All right.

 But based on these very noisy message-level labels, we wanted to find the polarity of the users. Now, you could take—you could take a naive version where you just average all the messages and you get it, and then you'll find that 83% of the users are neutral.

 Now, that doesn't—that doesn't work. So what we did: we created a new—a new polarity measure, which now is becoming continuous.

 It is defined between minus 1, strongly anti-Brexit, to plus 1, strongly pro-Brexit, with 0 being the—the neutral. And then we find that it has a big mode in the middle.

 So 30, 50 percent of our users are neutral, but then you're going to find there's quite a number of users that are mildly polarized on both ends. Those are the ones that we mis-analyzed.

 All right. So now we are equipped to start attacking our problems.

 But before I show you dynamics, let me show you a huge confounder. The confounder is the following: whenever we're dealing with social media data, unless you are a social media platform—so hands up, Google and Amazon developers.

 So if you're—if you're not them, what you see is activity. You don't see learners.

 You see people that post, not people that do not post. So that introduces a huge selection bias, because most people are actually learners. 70% of all users post only once, in—in only one—so not only once, but in only one period, and less than 1% of the users appear in 3 consecutive periods.

 So what I'm showing you here in the middle is the retention cost, the likelihood that the user returns, based on the number of—when compared to the number of features. So when I calculate polarity, raw or adjusted, I get 0.

 I—I get exactly nothing. The way I read this is the following: the pro-Brexit and the anti-Brexit get exactly the same likelihood of returning in the same period.

 However, if I account for activity, I start—start having the strong results. The more you post, the more likely you are to come back.

 Also, degree. The—the if you interact with—start with a—with a high degree user, with a popular user, you're likely to come back.

 Right. So what does it mean?

 What's the connection between survivorship bias and opinion change? I'm going to take you all the way here to the right, and I'm going to show you, in this graph, the fact that the—that the—that the survivors, in blue, tend to be more—more of them tend to be polarized.

 So more of the survivors, the people that return, are polarized. However, their polarization, mean absolute polarity, is lower.

 So how do I interpret this? Again, look—look all the way on the left.

 The returners, in blue, tend to be less polarized in absolute values than the—than the ones that don't return, in red. But the effect is not statistically significant, as shown here by the—by the confounding figure.

 How do I read this? It is—it is getting—it's starting to get interesting, because it basically says: people that keep coming for the discussions, in average, more of them are polarized, but they are not as extreme as you'd imagine.

 The extreme ones don't really come back. So the real extreme ones, they get—they get pushed out.

 So now comes—now comes another event, another thing, which is called the ECO chambers. We computed the edge-average homogeneity.

 An edge-average homogeneity is essentially negative if people interact with negative polarities. So the pro-Brexit tends to—to anti-Brexit, and it's positive if they're having the same polarity.

 I'm showing you the—the cumulative density of the—of the edge homogeneity, and you're going to see there's barely anything under 0. How do I read this?

 40% of every single interaction in our dataset are between black and white people. People don't talk to the opposing viewers, only if they can.

 They select not. And then, just to give you the full picture, in here I'm doing a regression of the future polarity—so the polarity in the next period—based on a number of features.

 And what is the most predictable signal? Surprise, surprise.

 Your current stance. So let me read this back to you.

 You tend to talk to people likely, not to people of opposing views, and you tend not to change your stance at all. That means that your—that means that might be more of an explanation than what's happening.

 Now, I'm going to do something that people don't really do in publication. I'm going to show you negative results, because we tend to be too obsessed with the positive results and the hustle culture of publication in order to tell you what doesn't work.

 So I'm going to tell you in this one what doesn't work. We tried better models.

 We tried stance closing—diag—diag closure stances. We tried models that are based on graph attention.

 We tried by bidirectional LSTMs. We didn't try the new—the new LSTMs.

 Nothing really managed to push up the—the performance either. The reason is that the signal—there is no stronger signal to be captured by bigger models.

 The—the—and most of—most of the findings are actually encapsulated in the social dynamics of the interaction. In the interest of time, I've been—I've been booked with Greek.

 I'm not going to tell you, you know, who I'd like to tell for platform designers, and I've arrived at my summary. So what I showed you here—if you need to leave out of here with just a few messages, these are the ones.

 First of all, we created a—a Brexit dataset containing more than 5,000 annotated submissions of the 27th period of time. This is—this is a—a new dataset that we're making available for the community.

 We introduced a continuous polarization measurement that is between minus 1 and 1. And finally, I've shown you both that behavioral patterns and behavioral findings explain the dynamics of—of polarity more than—more than machine learning, or faster than even machine learning itself.

 As typical. QR code for the data and the code.

 Paper appendix, all of it is—is available online. Thanks so much.

 We'll look for your questions.

 Any questions? It's a very nice introduction.

 We've had some—thank you. Any questions from the audience?