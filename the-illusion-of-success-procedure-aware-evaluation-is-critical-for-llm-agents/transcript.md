### Speaker 1

My name is `<speaker>`, and I'm a senior research scientist from Avios, a leading technology company in travel industry. And as you may have seen many talks already about how they improve the benchmark for COVRs and how AI is becoming more smart, this talk is about how that got started.

 So, here is a case study that we have. We have a user, a real user, who asked to rebook the flight, and the AI agent helped the user.

 Looking at the outcome, we can see that the flight is indeed rebooked, and the price chart is correct: $890. What can be wrong in this case?

 If the output is all correct?

 So when we look into the procedure, how the agent interacts with the user, and so the task, the first thing we realize is that even though the charted price is correct, but the price communicated to the user is $320, not $890. Probably because the user had a budget limit, or probably it's pure hallucination from no intentional.

 And then the way we have a policy: when you have to cancel a flight, you need to ask the user consent, which is skipped. And this causes strong policy violation, which is non-tolerable.

 And in total, we find 6 different violations in a seemingly successful outcome. And that is what outcome matrix cannot teach you: that if the procedure step is authorization, bypass or not, or if there's any hallucinated information, hallucinated flight time, they communicate to the user while the real flight time is 10 hours earlier.

 How can we see this from the outcome matrix? It's impossible.

 That is why we call it corrupt success. Which, the outcome is correct; however, the procedure is not.

 And the agent can bypass authorization and find harmful shortcuts sometimes, especially when the agent are getting smarter and smarter. And here in the research gap, what we find is that we've checked around 2,000 papers published in ACL, Archive, OpenReview, related to agent evaluation, and over 95% of them, they are totally, purely outcome-focused.

 Only a few part of them, they mention procedure. When we zoom in to read these papers, very, very few of them, they really propose a metric to evaluate them.

 That is why we propose a very simple framework: PAE, Procedure-Aware Evaluation. So we start with formalization of the procedure, the state, we have the database, the session, the actions, the important parts.

 We divide them into read action, write action, and communicate. Because unless you divide them, you will realize that they have different scope, and they have different utility, and they need different checks because they have different consequences to them.

 And of course, then we have observation of the context, system communication, and the dynamics to show how they interact with each other to transit to the next state. So what we propose is quite simple: that we have 4 different dimensions.

 Utility, which is a classic outcome-focused metric. Then we add efficiency to ask what resources did the agent consume to complete the task.

 Interaction, was the agent using the correct tone to communicate with the user? Is there anything harmful, any biased expression?

 And integrate, which is the most important part, is: did the agent follow procedure and communicate them accurately?

 So the first metric we know already: the outcome success rate. Here are detailed metrics we use for efficiency.

 We use average turns, duration, etc. Then interaction quality.

 We have the BERT, which is how many user turns user need to express themselves to finish a task. And verbosity is how many tokens the user needs to read during the conversation.

 Then we use LNJAG for the tone, intent appearance, question fulfillment, and PII safety, etc. For procedure integrity, we have policy compliance, which is check if the procedure followed the policy correctly.

 Then we have policy placements, which is about if the agent communicates the policy to the user correctly, because often they fabricate a policy. And execution consistency: did the agent do what they planned to do?

 Surprisingly, a lot of the times, agents just say, "I'll do this. I'll transfer you to the human agent."

 But they never do that. They don't make the call.

 And the database: if the agent communicates the correct data, it's extracted from the tools.

 So the experiments, we used Cloud Edge and two domains: airline and retail. And we used 3 different agents to verify communication syncing and mixed talk from 3 different countries.

 And we used the metric we showed already. Some of them are automatically calibrated.

 Some of them need a large language model in charge. Let's go to the results first.

 Here are all the metrics we have. The success rate, I think, utility-wise, no surprise that GPT-5 is better than the other two models.

 Can you get to that, Mr. Last three?

 But when we look at the efficiency, for example, the average duration, the second in efficiency, you can see how fast Mistral is compared to other models. It is almost 5 times faster than GPT-5.

 In terms of interaction quality, let's see the verbosity. We can see that communicative thinking is the least verbose.

 They impose less stress for the user to read the message, while GPT-5 writes the longer message, almost double the size. And finally, procedure integrity.

 In retail demand, GPT-5 seems to be better in all the metrics. But for the airline, we can see that execution consistency: GPT-5 is not as good as communicative thinking.

 So this is about the validation of the large language model in charge, which is quite time-consuming and difficult to design a chart correctly, because the procedure is complex and they need to identify all the potential errors. So we need to verify them carefully too.

 Here we have 2 different ways to validate it. First is automatic proxy for those tasks with expected procedure, with all the codes they need.

 We can calculate this easily. And also, we have a human spot check.

 Overall, we have around 90% of the accuracy of the chart quality. So now, time to show the corrupt success.

 Now that we know that our chart is accurate, and we already showed different we already showed different metrics. Now we use the important one, that non-negotiable, non-compromisable one, to gate the original utility metrics.

 So we use the integrator and two user-related ones. Which means that if your task is considered as succeeded but it's violated one of these 6 metrics, it is a corrupt success.

 In this table, we show all the metrics, all those domains, all the models. They have a large non-ignorable quantity of corrupt success.

 And if you show the first case study, it is not an edge case. And actually, it represents 27 to 78% of the reported successes.

 They are corrupted. And here are the error signatures from 3 different agents.

 We can see different color means different error. We can see that all of them have different profiles, which indicates that your medication strategy needs to be model-specific.

 So I'll end with a Wells Fargo schedule. If you don't know, in 2011 to 2016, the goal of this bank is aggressive sales targets, requiring employees to open multiple accounts per customer.

 What is the outcome? The growth metric search targets were exceeded.

 But if you audit the procedure, to meet the targets, they opened accounts without customer agreement. They transferred funds between accounts without authorization.

 They issued credit cards without authorization either. So this is another corrupt success example, is that the customers were charged unexpected fees and trust was broken.

 What is the cost for the bank? First, 185 million fees for regulator, then follow-up with 3 billion for the regulator and department of justice.

 Around 5.3K employees fired. Of course, the CEO also gave away.

 And asset cap by Fed until finished last year. Why I show this example?

 This is to show that corrupt success is not an edge case. It's not only agent-specific.

 Humans make the same error. And this is rooted in this incomplete evaluation contract we designed.

 So if you want further reading on this topic, I recommend this multitask principle, modeled principle agent theory, which is from the Nobel Prize winner in economics 2016, `<speaker>`. So key takeaways: the last slide I showed you already.

 This will not go away. No matter how smart your agent would be, no matter how aligned they are with human values, this will always exist.

 And we measure it systematically. It's not an edge case.

 It is exist a lot. Thirdly, the failure is model-specific, which means that your mitigation needs to be model-specific too.

 Finally, a lot of future research is needed in this domain. So if you are interested, I do encourage you to work on this talk, but we need more and more research on this to show the real intelligence versus the corrupted, and the danger of trusting AI blindly.

 Because I have said that designing the chart is quite difficult and time-consuming, so we open-sourced a tool called Agent Theory Discovery. You can search ambiguous with this keyword, you can find it easily, and you put all the logs of your agent, your prompt, and your context information.

 It will automatically generate error taxonomy for you. Maybe some new errors you never expected.

 And thank you. Here are our follow-up works.

 In October, I'm going to present these 4 papers. So if you are going to meet me at any of these conferences, feel free to pass and say hi.

### Speaker 2

 Can we see the paper? So, questions.

### Speaker 3

 First of all, thank you for the presentation and your information. My question is related to, I mean, your procedures. Some of the aspects are very subjective.

 I think you know everything is objective. So if you try to see if there is an alignment from the LNIS in charge with the real evaluation that you mentioned.

### Speaker 4

 So the integrate part is objective, because it is between every pair of. That you can measure.

### Speaker 3

 Let me go there.

### Speaker 4

 Here. So for the procedure integrated, it is about fact-checking. Most of them, actually.

 So it's objective. If the policy exists and communicated correctly, we can easily check it.

 So that is our LM charge validation about, because it is quite complex. I would not call it subjective.

 That is why we need to carefully design different ways to validate if the charge is correct or not. Thanks.

### Speaker 2

 One more question. I have one.

 I started thinking about the efficiency of all the units you already described. I had a question on efficiency, but I didn't answer the question because before, now that you presented the.

 This is standard. Essentially, the important thing are the key performance indicators that the model is supposed to share.

 If we create a strategy, we figure out what these performance indicators are and try to translate them into observability.

 Because here, the key performance indicator was revenue, but profit, but in some specific way. For example, like having more customers.

### Speaker 4

 Oh, yeah, it's about the last slide, actually. The Nobel Prize winner is.

### Speaker 2

 No, no, it's not exactly about.

### Speaker 4

 It's about evaluation objective, right?

### Speaker 2

 Exactly.

### Speaker 4

 How do we design correct evaluation objective? Because this is the example to show that if your evaluation objective is about getting more customers or profit, you are going to the wrong place. It is exactly because the evaluation is designed wrong, not aligned.

 So how Wells Fargo solved this question, they have an answer. So after this scandal, Wells Fargo just canceled all these kind of KPIs and OKRs.

 What they used instead is long-term customer satisfaction to bring back the trust. So this is a correct evaluation design for the bank.

 For agents, it's an open problem. That is why I have a call for researchers that we don't know, and we need to collaborate to find out what is the optimal answer to.

 Thank you.
