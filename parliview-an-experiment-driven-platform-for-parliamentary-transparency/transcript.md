### Speaker 1

Okay, it's great to be here with you today. We're joining you on the platform for the Wispr practice, and it's a collaboration with Rowan Huxley and Chair Ian Foster of the School of Computer Science and School of Politics and International Relations at UCD. And with today of our listeners who are joining for the practice of government and public policy at the University of Strathclyde in Glasgow.

 So I'll introduce a problem. In one week, the European Parliament—and we're very, very good at trying to make information available to the public—we'll live-stream about 40 hours of video on the internet, I think about 450 in the U.S. available to the public, and all of this is across 24 different official languages.

 All of the EU citizens in the room, you guys know this already: you are watching these videos and you're reading the PDFs, but some people don't, okay? So we need to—how do we get people to engage, right?

 So two things we're seeing: information overload and a demographic deficit. So people are not going to different sources for political information, social media now, they're extremely overwhelmed.

 And alongside this, we're seeing about 33% of citizens in the EU tend to trust the European Parliament, that was in 2023, and about 50% of EU citizens voted in European Parliament elections. So the challenge here is: how do we make the information which is being made available to people accessible to them?

 This is all going to be interesting, so transparency and accountability for the institution. So the answer, one answer, is something like this: this is part of the EU, it's a retrieval of entertainment in the chatbot, over the data in the Parliament, okay?

 So all of the data that's already being made available, you have a chatbot which allows users to enter queries, questions in natural language, get responses in simple answers, and they can explore the sources they're interested in. There will also be prompts and follow-up questions there to help them to, sort of, continue to engage with the platform.

 In 2026, building something like this in the kind of the basic way is relatively straightforward, and it sort of asks more questions than it answers. How do we build these systems in responsible and transparent ways that actually serve the user?

 And so our goal with this platform—and I'll describe the architecture now—has this in mind. So we have a sort of flexible architecture.

 It's not one defined process for asking questions. We have a kind of modular, over-the-line, diagnostic architecture, basically a graph, which handles requests from users and serves them with some information.

 So for example, a user question comes in, and we have a retrieval component. We can moderate the data that the retrieval component has access to by changing the tools that are plugged in there.

 And the founders they use, the information then we use in generation 7, so standards under RAG, compliant, which has access to another set of tools, and we have a post-processing step, and then finally the answer arrives in the user interface. So we've developed the system this way so that we can change the process, we can change the data that's being used, and we can change how it's being presented so that we can experiment with how citizens will interact with a tool like this and what impacts

 they have on them. To give you an idea of the systematic experimentation, we have two experiments here, 1 and 2, where in each one we have different tags assigned to different treatment groups. So essentially we want to explore the effect of changing the perception or the experience of users on the platform and seeing how it changes different outcomes of their perceived political efficacy or their ability to understand how the platform works or their understanding of the political institution itself.

 So the top one there we changed, for example, the data that the systems have access to, so it treats users differently based on that, or in the bottom one we change their experience on the content. We've launched these setups at the moment so we can comment on it in a deadline way.

 We can see different versions. The platform, we can make it more transparent in how we present the information and how we present the retrieval steps.

 We can make it less transparent. And we can also introduce new problems with the system, which is what I think is quite interesting.

 And here we describe an experiment. Treatment will take place between user groups, but when we introduce problems in the system that we might like to see how users can react to those problems, we introduce those problems across user groups.

 For example, we might bias the retrieval step to favor one priority over another or to only present one set of political views. How can we make that sort of retrieval problem more transparent to a user so that they can react to it?

 These are the kind of questions that we like to explore. And here's a brief view of what it looks like to log onto the system as a sort of an administrator or a social scientist who has to set up one of these experiments where you define the different user groups that you have, you click and drag, set up the different processes and the different experiences that users will have, and then you can sort of set up your own one.

 The example here is the effect of follow-up questions. So if when you ask a question you receive an answer, if we prompt you then with some follow-up questions to what you might like to ask next, how does this change the information that you're exposed to?

 For example, we could prompt you with follow-up questions that are intentionally trying to diversify your experience, or we could prompt you with follow-up questions that want you to sort of probe deeper or reaffirm what you're already looking at. This is an interesting experiment.

 We might like to explore how we can develop these tools to sort of better serve people developmental responsibility. So if you would like to follow the QR code there to help with the quiz, you can sign onto the platform now.

 You can have a sort of a goal of a general citizen's ease, which is all the bells and whistles, very transparent, right? We try to make it sort of transparent and just where the information is coming from, which I think.

 And if you come to find me later, you can try out the different versions that we've developed with the system to answer different questions. And these are experiments that we'll be rolling over the next kind of year with in different contexts, mostly in the higher-spectrum.

 Thank you.

### Speaker 2

 So okay, it's kind of set changing is there, right? Sure, you have a couple of user groups and so on. So do you add any kind of, like, added value on the top of it, right?

 So at the end, you know, me as a citizen I'm lost in all this information, right? So yes, if I have endless time, technically I can work through all of it, but do you provide something where I would get insights?

### Speaker 1

 Sure. So, I mean, the general intention is that you would ask questions in natural language. Who are the entities who represent me?

 How have they been? What decisions were made in the Parliament this week on this particular issue?

 And what, as you point out, all that information is available online. You wouldn't need to go where to look for it.

 How can you find out what's relevant for you this week? You get a natural language response describing the situation to you, which you can then interrogate.

 You can ask follow-up questions. You can explore the sources.

 So I think the question is about.

### Speaker 2

 Well, this is kind of an astute, right? But now, since you have all the information there and so on, and all this magic relevant tools, right, which I'm sure you're using, right, do you, let's see, if my setting would be I have exactly 3 minutes and I would learn something, I want to learn something, could you provide me the answer so that you spend only 3 minutes of my time?

### Speaker 1

 Yeah, I mean, that's very much the intention, right? You ask a question, you get a synthesized, summarized insights from across all of the data, which would not be accessible to everyone.

### Speaker 2

 Okay, I—

### Speaker 1

 You know exactly what it is. You can try it out.

### Speaker 2

 I already tried it. I've already tried it.

### Speaker 1

 Thank you.

### Speaker 3

 Any other questions? I'll say anything on this question, so we can move on to the next one. AN10A.

 Shall we go and explain what tensor analysis system in large languages?
