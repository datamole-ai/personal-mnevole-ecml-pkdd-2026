### Speaker 1

Okay, I'm going to do this instead: multi-uh, multi- multi-positional data.

 Um, and in this one we— we— the naming need to be a little bit complicated, complicated, I should say. It's just like we put several agents in on the client, then we wait on our— on our— on what topic the reference is, so that it's— that it's confusing what we're doing.

 So we start with the problem: many tasks actually involve multi-conversational jobs, uh, conversational data, such as meeting summarization, argument management, stress detection, and, uh, as written, there is also personal analysis and model behavior analysis. But there are problems.

 So first, the real conversations are quite expensive to collect, and, and all the existing meeting summarization datasets are kept old. Then there is a compli— a compliance issue involved, so it's very hard to collect the real, real person meeting, uh, meeting data.

 Uh, then people generate the, uh, the data right now with the LLM, which is exactly the conversational dataset, but the result are quite shallow. So action services goes from: the first one is a cognitive net reflectives.

 It means the agent is just an answer to the previous message. Uh, the agent has no idea who in the room believes what.

 And then second, the strategic, uh, strategy. Property.

 It means every turn is either I agree or I disagree, and the more we repeat the question, the more we try to build a coalition, or— and nobody knows, no, what the body means. Nobody knows, um, when to take the right moment to, uh, to concede.

 And the last one is a dynamic rejecting. So basically we're saying the existing framework is a jigsaw, fixes big events, and nothing unexpected ever happens.

 And all these three problems are actually connected. What you say depends on how you read the room, and the way you speak depends on how the discussion is going on, and what you say changes what everyone else thinks.

 So this is actual workload, and. Means a single prompt right now we cannot read something, so we need an app.

 So here's another one. Uh, it works in three things: first, the word generation.

 Uh, we have a model to set up the scenario, and the participant and what each other think about the topic and the genre and the name and the background argument and facts, uh, and also the subtopic that we are going to cover in this conversation. Second, the simulation.

 We have each agent take turns while the agent is watched and serve as a termination phase when the discussion has run its course. Inside the simulation, there are also three layers.

 The first one is cognitive cognitive layer. It's inside the.

 It is inside each agent. This is to say how the agent thinks about the others and decide what to do next.

 And the second is structu- uh, structural layer. And manage to manage the group.

 Who speaks next, whether the topic has been covered, and also provide the facility to, like, share the whole conversation. And then the third is a bottom layer that is always on.

 We provide a guide that checks, uh, every turn and decides whether to, uh, continue, redirect, or to stop. So here in our experiment, uh, we— we do, uh, our setup is a lar— is a large model that does the same thing as small models.

 I mean, so here we provide a 2025 72B or 2025 orchestrator, and when the agent are trying, um, to do the role-play, we are actually looking at the first rejection.

 So, uh, let's go inside one agent. The core idea of this, uh, paper is, uh, stereotype.

 This is a psychological term, uh, meaning, uh, meaning our ability to imagine what is going on in someone else's head. When you argue with your colleague, you actually have a picture of it.

 Are they open to persuasion? Are they getting frustrated?

 Or, uh, really they are argumentative? We give every agent exactly that.

 For each other participant, it gives a small mental picture, uh, what actually your position is, how firmly, uh, your position, uh, how firmly your beliefs, whether they trust you, your re-arguments, whether and what I expect you to do next. So before each turn, the agent gets this picture in pointed language as a quick read of the promise evolution.

 And then this picture, this information, is updated af- after every turn, just like how you people, uh, update the information during the day. In the real context, in, in the gen- uh, generated, uh, situation, um, the agent rarely can see.

 So if you can see a point, that tells actually much more than just a non- non- non- non- non- non- non- non- non- non- disagreement or agreement. Once the agent know what he thinks about the others, they decide how to act.

 Not just agree or disagree, but actually want a strategy that people will, uh, people actually will even face. So we have, uh, a best attack approach with a prompt evolution, and then a C, propose a compromise, green and grey evidence, or change the topic, or build on what someone else just talked about.

 The last piece is perception training. Here we set each agent has a thinking, uh, on the topic, from strongly against to strongly in favor of.

 And secondly, I'm sure it is. When, uh, when it can see the point, it becomes less sure, but it's a thinking that can't really flip right away.

 So that is how people really behave, uh, when you wait for a while before you actually change your, change your mind.

 So here is, uh, one of the examples that we extracted, uh, from one generated conversation that actually we can see from the, from the three actors, `<name>` and `<name>`. We see that `<name>` probe, uh, works.

 Uh, has a, uh, personal that's supported, and Marian is on the interface. But as the conversation goes on from the, uh, turns 28 to turns 32, we can see that Marian, uh, Marian actually got frustrated.

 So this is a step change.

 Then the second layer we're going to, uh, implement is to make sure the whole thing stays, uh, conversational, not just on the phone. Who speaks next?

 In a real meeting, people jump in when they, uh, have something to say, or when they have been quiet for a while, or there, there is someone attack, uh, attack the coalitions. So every agent has such a, as we call, urgency score that goes up in the, uh, in the situation and down after it has spoken.

 The most urgent agent speaks next, but we also introduce a little bit of language so- so that we can make sure it never turns into a cue, a fake start. Then has a point in it, a subtopic tracker, uh, follows each subtopic from untouched to exhausted.

 It helps to move the discussion on when the subtopic is used up and end the conversation with another mark. Three judges.

 We also, uh, w uh, as we said, they are always on standby, watching all the watching the conversation the whole time. They are, uh, they look at, uh, three, uh, three levels: definites, progress, and, uh, group dynamics.

 And we also have another module called voter that decides whether to continue, inject, uh, inject a new fact, or redirect off-topic. And there is a facilitator who will take an action from the signal that we create, that, uh, it's a revolution that will invite people to, uh, people in to summarize and close when they when the facilitator receives a signal from the voter.

 So each speaker has a number and a participant will react to it in the moment, just as we'll do in the, in the real meeting.

 With this framework, we build a dataset, uh, it's a preliminary dataset. We release 1,100 conversations across 11 professional domains.

 Uh, each conversation has four participants and, uh, 20 to 50 turns. And every turn comes with a, with a whole cognitive annotation, what the agent believes about others, and which move it choose, and how its position evolves.

 We evaluate then the dataset at three levels. First is a quality weight.

 We sample one we- we sample 10% of the conversation, and then score by the GPT-4, as LLM as we love, and also by 3DQ manipulators. Then we compare with a demo of a well-known model agent framework.

 Second, which part of the module really matters. We, we then, uh, run a controlled ablation study that turns components off one at a time.

 Then third is a data reading, uh, actually useful. We, uh, to answer that question, we run three months small model only, and then some on three months re-test for the, uh, to, to see the observability on the real, uh, real interaction.

 So the first one is, uh, is what we compare with, uh, with demo on the same 110 scenario. Score the same way on full dimension from 1 to 5.

 Um, so here we can see Marian is the head, uh, is the head of four, uh, dimensions, and the big gap are actually measurements. And the interaction, uh, and the interac- uh, interaction dynamics.

 We see that these two, uh, these two is more than a 2-point or 5-point scale. That is exactly with a stillness framework as demo results.

 The conversation does not mean sometimes people actually talking to each other, and the final part are much tighter, so it, the body is, uh, quite consistent from one conversation to another. And, uh, to answer one question is why demo help?

 The reason is simple because, uh, demo is a framework, and the framework itself, it forgot it, it's short memory jobs. Turns, so.

### Speaker 2

 Why?

### Speaker 1

 Okay. So, so, so the same argument comes back as a new one here. So there is, uh, archive level of, uh, uh, repetition.

 And in, uh, in, and, uh, demo is a framework only have, uh, two agents, so there is no correlation, and there is, uh, no team up, and, and, and so, uh, that's why we're demo for short. Then the second.

 Without evaluation. Evaluation, we want to, uh, we, we provide a full version of the system.

 We have four arena. Arena without facilitator, arena without cognitive module, and, uh, battery span just as in the model is, uh, is not so valid.

 So the common part, it tells the result are actually mostly eligible. Removing cognitions that may not change what the agent talked about, uh, the topic, but from the engagement score, we can see it drops.

 With, uh, uh, the same as, uh, definites. So it needs to see the cognitive module do not really help generating content, but it makes agent engage with a specific person about a specific claim.

 Uh, facilitators is quite different because facilitator is not really trying to improve the quality of the, of the content, but it's trying to, uh, uh, to reduce repetition, and it, uh, let, uh, let, let the facilitator know when to stop to improve, uh, to improve the overall, overall bar definites and engagement.

### Speaker 2

 Okay. Thank you very much.

### Speaker 1

 Okay. Sorry.

### Speaker 2

 Uh, this is an example of, uh, the disability of the RTC manager, as a key note. Uh, questions.

 Let's see. Uh, I have one question.

 If you take time to present a certain example, what would you consider?

### Speaker 1

 Actually, the certain, uh, certain, uh, certain, uh, certain slide basically trying to say we produce, uh, the, the first two, uh, boundary class, one is public participation, one is, uh, uh, is a meaningful and crucial, crucial events that are, uh, that are not anybody's signal that it has the purpose of the, uh, the transferring into the real, uh, real world. Then the third one, the argument evolution and training. Actually trying to prove that, that the, the cognitive and the vision that, uh, extracted from our, uh, from

 our agent is, uh, is also learnable. So basically that's, uh, so with. Is that we said that we can achieve not bad score on the real world.

 This is when we say that, uh, this is a good, uh, synthetic agent framework.

### Speaker 2

 Yeah. Uh, let's see. Speaking of my next question, but I am looking at the audience, uh, and the customer's question.

 Uh, essentially, you start with the sky of humans, uh, uh, I play with the real RTC manager, but I'm not a real RTC manager. And I believe that among humans, there is a large variety of strategies.

 I think we must focus probably, um, the, uh, the speakers in the room would be, um, could have any kind of behavior or misbehavior. So, uh, how flexible is your empowerment?

### Speaker 1

 Actually, from the flexibility, it's really based on how the person, how the experience model is, uh, generating the whole scenario. And at the same time. But we know there are some things that we cannot do in our model, so that's why we try to run training on the model once in our events we will make.

 So we want to train on that, uh, uh, small, small task. So we can also call.

 It's not just, uh, it's sort of like a conversational RTC agent for a specific, uh, task or generated data.

### Speaker 2

 Okay. Final questions.

### Speaker 3

 Yeah. Thank you for the presentation. Um, so I have some, uh, uncertainty about how we can evaluate smart people.

 And we put several, um, areas like naturalism, etc. I'm using a lot of intentional.

 What are the usefulness of the result rather than just using some measurements or some judges.

### Speaker 1

 Yes.

### Speaker 3

 How do you prove that your dataset is better data set than the, um, uh, what is the other one?

### Speaker 1

 Uh, demo.

### Speaker 3

 Demo.

### Speaker 1

 Yes. So yeah, yeah. But demo is a, a module for that is not just bounded for the role play or for generating synthetic dataset.

 It's more for cognitive model to facilitate your actual, uh, task, uh, whereas role play is just one function that we provide. So, uh, and here arena, as we are not trying to do is, uh, to, to improve demo flow or to do other tasks.

 It is bounded only for generating the synthetic data that we role play. So here, that's why we are our team more perform at.

 With a better quality control demo. At the same time, to, uh, as we are generating proper generative data, we want our data to be useful.

 So here we use three task requests to test AC or generative. So this is a group, uh, that's, uh, cognitive and synthetic datasets.

 We can beat, uh, uh, with, uh, compare with the real dataset, uh, real dataset training, uh, and on the real datasets, we could achieve not bad score. So it proves thus the utility of the synthetic dataset.

 It has learning signals.

### Speaker 2

 Okay. Thank you very much.
