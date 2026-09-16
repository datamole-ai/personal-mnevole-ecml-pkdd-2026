### Speaker 1

Is `<speaker>`, and did he present a different enterprise chart for us than the one we're looking at here? So, my name is `<speaker>`. I'm here to talk about the roadmap for developing Wispr Flow and Wispr.

 Let me start off with one more thing: there were exactly 22 minutes of talking in one and the other one was being interrupted. So, I'll present to you an idea of mine.

 We have the business of—

### Speaker 2

 Is this the outlet?

### Speaker 1

 Is it okay now?

### Speaker 2

 Yes.

### Speaker 1

 Okay. So, we have the business of 9 people from one base in Wispr, and today I'm here to talk about one of the problems that we're facing within our own ecosystem and how we're solving for it.

 So, I'm sure a lot of you would have faced this problem and before that, let me ask you a quick question. How many of you have used Slack, or Codex, Kaggle, any of these?

 Possibly all of them. If you're not using them, probably you should.

 I know I'm not using them, right? So, one problem that we keep on facing now is there is a modeling knowledge set of A that all these models, fancy models of the world, have.

 And all these related things that we're using for very large teams, different softwares, let's call them enterprise, they keep changing. We use TypeScript, we use Java, we use Python, or whatever, right?

 And there's a good amount of salient gap that we've got before we start targeting the SEO simplification, right? So if, let's say, you end up using our something today, and there was a new version that ended up coming out for TypeScript, then there are a lot of chances that your code would go through a hundred previous scans, there would be a lot of issues that it would go through, and lots of other different things, which none of the enterprise is going to like.

 The problem is, although the code is going through the technically possible work, it's conveniently wrong. Conveniently wrong from the point of view of the new languages that are coming out there, the new assets that are coming out.

 We were also going to go based on this particular problem, and that kind of forced us to think about what are the possible ways of solving all these different salient gaps that we have. So, we stumbled upon these two things for solving all that salient gap that I just talked about.

 So first one, we'll look at context first. So context first.

 Think of it this way: the fundamental thing is you want to reduce all this salient gap, and you can think of this as a librarian who is trying to fill out this context set with the right context. So with context work, what we're doing is we are literally just down-selecting out these different library versions that are coming out of the libraries and the frameworks that we're open source by entering it.

 And think of it as a team; in a community effort, you can just downsource out all these API documentations that are coming out. You can just do that, and finally, you can just have a ready-to-insure context set that you can feed it out to these large language models.

 The other approach is context serving, which is a little, I would say, a little different way of solving problems. It's where you start to get a sort of a system that can literally keep on looking out to all the different versions that are coming out of the libraries.

 It can pass all those different documentations, generate certain vectorizers, and then distribute it, right? So these are little ways of solving problems.

 What we ended up doing was, we did this experiment on test 10 software packages that you've seen in the doc, and version migration prompt where the idea was, if you want to just migrate out one piece of service of a particular large number of software to a different version, and you know, these are the two interview systems that I just talked about.

 So there were 16 different implementations that we did. So the phase one, so there were two different phases that we were evaluating out all of this one.

 So phase one was context working, which was mandatory for all the evaluations that we did, and phase two was code reviewing, and that's how we talk about both of these things, right? From a generation standpoint, we were using GPT-4.1 because that was the oldest model that we were able to find on at this point in time, and we specifically ended up selecting on this 10 package because there are a lot of these changes that are happening within these libraries and everything, and GPT-4.1 gave us

 a lot of, you know, it was able to kind of sketch out all those things there, right? For quality, we ended up using Claude also 2.6 as a vision model. So the idea there was, what are those 16 different versionations?

 We wanted to look at our context quality perspective and the code quality perspective. For context quality, I already talked about that when we were used to do the evaluations for code utility, we used JSON, and since we were using LLM as a judge, we were not just relying on an LLM to do it.

 What we ended up doing was we ended up just sampling out 15% of all the code that was coming out of the systems, and we manually ended up looking on JSON to find out what it was for the evaluation. So the interesting thing that we figured out was, from a context service perspective, it was good in accuracy and clarity, and this reminds you of the simple case of the context quality.

 And context service was very long on the components' perspective. So, you know, I'd need to start thinking about it that, hey, on the context quality score card, context helps us read the benchmark, but that was not true the moment we moved over to the code quality.

 And what we saw was, the mean code quality of the context help was like 3.2% lower than the context service. And from a prediction-based standpoint, context service was very on context service.

 So, and this probably is not good. So, this is just a, you know, key takeaway of what we ended up trying out in this experiment, that it's not just one super build that's solving out for everything, rather it depends on the night problem that we're trying to solve.

 Because one cool thing that we saw was that context helped very late when it was reading out some of the context quality perspective. But OpenAI and PyTV, which are very seen on the common types quick tasks, it was still performing better.

 And of course, I think I can even summarize the test that we did. So what we are proposing, so, you know, what we are proposing is a kind of a routing mechanism where, you know, you can classify all the tasks, select the context, and get the generated data of the code, and then generate the information out of that.

 So it depends out on, you know, which sort of underlying API packages that we're using, whether it's TypeScript and lots of the different things, and, you know, whether those, you know, how frequently those releases are, because once a day, twice, or multiple times a week, or whatever. But it depends out on all of this.

 So there is no, what this experiment suggests is there is no super build that context is always going to win. Rather.

### Speaker 3

 I'm reaching for.

### Speaker 1

 So just to summarize, you know, of course, the limitations of this approach that you might ask is that the opposite is pretty small, like 30 pounds, and we're already out on, of course, maybe a little bit. This is still working from this work that we're still doing out from, you know, the second box that you see between the two at this very soon. Right now, of course, we're not comparing apples with apples, right?

 Because context quality and code quality are two different variations, you know, from the system that we're solving. And another judge, of course, we just chose like 15% of all the language generated code packages that we can add to the context service.

 And there might be some distributions that could add to that. And of course, these packages will keep changing from time to time, so this was a fixed one, so we can use fixed architectures that we ended up using out all this experiment.

 So I just want to leave open this, you know, context quality is not the code quality that we just talked about. And from a future work perspective, you know, we wanted to just.

 Quality of these code inventory applications, we want to increase our developers, and we want to continue to keep on working on the quality, that would be the future work. Thank you.

 I don't think there are any questions.

### Speaker 4

 Questions?

### Speaker 1

 Thank you.
