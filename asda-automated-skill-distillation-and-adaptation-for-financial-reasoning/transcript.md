### Speaker 1

Hello everyone. Good morning. Um, I'm `<name>`, the lead author for this paper.

 This is, uh, ASPER: Automated Skills Displayation and Adaptation for Financial Risk, developed together with my co-author, um, at the University of Hong Kong. At its core, the idea is straightforward: we teach large language models to debug their own financial risk, one executable skill.

 So let me start with my motivation. We set out to find a generative alternative to fine-tuning, a way to adopt a model without touching its weight.

 Training free adaptation looks promising in general, but once we apply this specifically to our dataset, the gains barely moved. So we looked more closely, and while analysis kept pointing to the same issue, models were lacking general knowledge.

 They were misapplying financial concepts, or picking the wrong decision. That's a domain knowledge gap, back to generic prompting clients target directly.

 That gap is what ASPER set out to close. And the numbers make it clear.

 Take the acquisition. First, standard non-reasoning for team models, reach only 38% to 45% on farmer, a financial reasoning benchmark spanning 8 subfields, including corporate finance, derivatives, and portfolio management.

 In other words, regardless of the model, there is a hard limit of these kinds of tasks. Then there's the cost of all these things.

 Fine-tuning would help, but, uh, take an example like Bloomberg GPT required 1.3 million GPU hours just to pre-train. And prompt optimization, like Code 2.

 We test Keeper and ACE to reason training free model method, deliver only 0 to 3.3% point of improvement on the same benchmark. Meanwhile, agent skills are emerging as a standard way to extend large language models.

 That's the abstraction our work builds on.

 So what does that idea actually look like in practice? Every skills lives in a simple text file, in a format markdown, so anyone can open it and just read it like a document.

 No specific tools required. This file is organized into folders, some generic and some subfield-specific.

 You can see on the right-hand side, there's a common folder for skills that apply broadly regardless of subfield, like knowing how to read a charge correctly, or how to format an answer. And then there are subfields like, uh, derivatives, corporate finance, fixed income, containing the skills file relevant to the mistake that show up specifically in that area.

 Sitting above all of these is the skills.md, which is a top-level index. It is the file that looks at the incoming questions and decides which folder and which specific skills file are actually relevant.

 Then, inside each individual skills file, there are four components: a description of the knowledge gap, which addresses an explicit condition of when to use it, a step-by-step procedure, and a work example with code. This entire file format already exists; part of the agent skills owner's standard.

 What we automate is how it gets automated.

 So how do we actually populate all of this automatically without any human writing these files by hand? The point, right, once in three phases, shown here.

 So first of all, we do, uh, phase one, what we call the warm-up phase. We start with the training set and collect every cases where the student model failed.

 For each failure, the teacher model asks why. Was it missing knowledge?

 Concept confusion? Ignoring a constraint?

 It classifies the error, labels each failure by subfield and error type. This labeled failure gets clustered, and the cluster becomes what we call the skills library, the full collection of skills files the system will draw from.

 And then, by having this skills file built, the, um, the phase, uh, what we call the phase three is actually the inference phase. So the, uh, student models can already make use of this developed library.

 So first of all, when the questions come in, we have the, um, skills.md. A bit high here, but we have the skills.md file, which is an index and mapping table that allows us to retrieve the relevant skills files.

 And then, um, by inject-injecting this skills library into the student's model prompt, the student, um, can access the library and improve in this, uh, financial reasoning. And then in the middle, uh, is what we call the iterative refining.

 It is, um, almost like a backpropagation without, uh, fine-tuning the weights. So basically, um, we analyze, uh, uh, through comparing between using our skills library and without using the skills library.

 And for each questions, we will, uh, we will categorize it into the Q plus, which is our skills actually improve, skills, uh, Q minus actually we our skills regress, and Q gap, which the skills doesn't really have. And then, uh, we have two phases, which is called the, um, coverage refinement and the safety refinement.

 So the coverage refinement is basically to refine or to create new skills that addresses the gaps. And then the safety refinement is that, uh, we looked into why the questions actually, uh, regress and refine our skills.

 And both processes will get verified, uh, before, um, it's getting accepted. And if the ver-verification cannot pass through, then it will, uh, ask the, uh, teacher models to create the skills again.

 And there's a, like, an upper limit threshold that we set. So, um, so this is more like the, um, training, uh, loop that, uh, traditional, uh, machine learning, uh, adopt.

 And then here is a, um, skills in action. So this skills are a bit small here, but, uh, in essence, it is about, uh, calculating, like, a, um, a, uh, a spot, uh, price of a bond.

 And, um, the error is actually it's used as spot rate rather than a compound, uh, compound rate. So, uh, our, um, our skills here, uh, as you can see on the right-hand side, uh, uh, it specifies when to use, it specifies the, um, uh, procedure, how to use it, uh, and the, and the code template.

 And some, um, also some, uh, uh, limitation or alerts about, uh, when to use it. And, uh, for this particular skills, it actually fixes, uh, seven, uh, related questions.

 So basically, um, one error analysis comes up with a skills that can be, uh, reused multiple times within our training data. So, uh, this is, uh, how we set up the exper-experiment.

 Uh, we use a, uh, benchmark for farmer, which is, uh, a pretty, uh, complicated, uh, multidisciplinary financial reasoning, um, QA. And then, uh, we make use of the Claude family, uh, student and teacher.

 And then, uh, we use two training-free baselines. So, uh, there's a total of, uh, 100, uh, 1,378 questions, with, uh, uh, a portion of them is arithmetics questions and a portion of them are non-arithmetics questions, uh, across eight, uh, financial subfields.

 And the model we use is, uh, Haiku 3.5, Haiku 4.5, and we use only 4.5 of the teacher models.

 And, uh, this is our result.

 Um, so as you can see on the left-hand side, um, uh, using, uh, for the arithmetics questions, uh, the, um, the yellow is actually our, uh, warm-up phase, which already gave us an 8.67% increase. And after two rounds of epoch, uh, the, uh, uplift is actually 17%, compared to just a few percentage for the two baseline of Keeper and ACE.

 For the non-arithmetics, uh, categories, uh, the uplift is, uh, uh, is, is, uh, less significant. The skill, uh, 5.95%.

 So, um, yeah. So, um, and when we use the Haiku 4.5, we also get, uh, almost a 6% increase.

 So, um, what are the key findings, apart from the accuracy, uh, accuracy improvement? So, um, so first of all, we analyzed what does the gain come from.

 Uh, by using, uh, the same teacher and student model, Haiku 3.5, we were able to recover 75, uh, 73% of the gain. So, uh, no stronger model is needed.

 Meaning that, um, the, uh, the student model actually improved itself by analyzing the error. And on the other hand, uh, do the skills library being built, uh, can be transferred.

 From our experience, unfortunately, the skills are very specific, so every new model we need to regenerate. However, um, in our pipeline, the two generation, uh, only takes, uh, 162 million tokens.

 So it's actually a, a lot, uh, more, uh, cost-economic than, uh, doing fine-tuning, etc. So, uh, no fine-tuning is needed, and, uh, the, uh, methodology can also work on the platforms, uh, LLM APIs.

 So last is about the, uh, limitation. So, uh, we only use a single, uh, uh, models and a single benchmark.

 And, uh, in fact, for this benchmark, some of the, um, uh, OCR, uh, extracted texts, uh, it's have some error. And, uh, the model actually creates some heuristic to debug some of the OCR error, which is, uh, not necessarily what we wanted.

 And, uh, so our future work, uh, will be, uh, to see if this methodology is, uh, domain transferable, uh, what is it, expand to other models. And we also, uh, want to, uh, improve our, uh, methodology so that it can be finer-grained, uh, with, uh, better, uh, uh, uh, uh, better, uh, usage of the tokens.

 And, um, uh, during the, um, um, publication, uh, we already been, uh, working on this three directions, and, uh, all of these have, uh, pretty good, uh, uh, results. For example, uh, in healthcare and legal, we proved that the methodology is transferable.

 Uh, we also improved the workflow that the overall token consumption is significantly reduced. So, um, a skill library isn't a better problem.

 It is a new representation layer between a model and its deployment context, one that can be version-controlled, audit, and regenerate for whatever model comes next. So thank you for your, um, um, time, and, uh, happy to answer any questions if you have them.

### Speaker 2

 What questions do I have? Can I start with you? Because I'm asking my own questions.

 So, uh, what, what was the, the beginning actually question? Son, uh, this, uh, uh, big world, global, and go back there.

 Yeah, exactly. Uh, now the question was about, uh, it is about the warm-up phase and why did the student model say.

 Now we are talking about the ground truth, and I would like you to spend some words about the reliability of this ground truth.

### Speaker 1

 Uh, so basically, um, the ground truth, uh, came from the data set, and we have the arithmetics questions as well as the non-arithmetics questions. For the arithmetics question, uh, it's relatively straightforward. Its ground truth is numerical answers.

 And, uh, but of course, for the non-arithmetics one, it's more like open text. So we do use, uh, the Chandler model.

 For the, uh, judging. And we compared the result with, uh, because originally the, the farmer data set was using, uh, GPT-4.0, but the result is very, very similar.

 We used Chandler because of, uh, it's, it's a cheaper model to use. And, uh, so basically the ground truth is based on, uh, numerical answer.

 It's straightforward. Uh, the, the other is, uh, LLM as a judge.

### Speaker 2

 Yeah. Uh, I, I will help. Um, and essentially what I'm asking, my question is how, uh, would you use the ground truth when you talk about financial reasoning, which is your guiding?

 Do you take that, or what is your, where comes your confidence from that this ground truth is good enough for financial reasoning?

### Speaker 1

 Um, so I think this we have actually evaluated more than 10 different data sets in the financial reasoning space. Uh, some are focusing on, like, visual model, visual understanding. Some, uh, uh, some other aspect.

 This one, uh, we believe is, uh, quite comprehensive one. At the same time, as I mentioned, uh, our future work already, uh, tests other, uh, financial reasoning, uh, uh, data set.

 Even though the, the results are all positive, but some have, uh, better res-uh, results, some have less. And, um, the methodology also is quite dependent on the models.

 So we also find that, uh, if the baseline model, for example, here we use Haiku 3.5, the result is very good. But if you use, for example, uh, Opus 5, there might be very minimal, uh, improvement, um, because there's, like, some opacity in the, um, uh, capabilities.

### Speaker 2

 Okay. Thank you very much. Uh, are there questions?

### Speaker 3

 So the skill market, like, is it, like, uh, provided by, by the model in the future?

### Speaker 2

 Uh, can you, uh, repeat the question? Uh, so that.

### Speaker 1

 Yeah, the question is more like what are the deliverable of what is being learned, right? So actually what is being learned is in this format. So it's the very typical agent skills, uh, template, whereas we specify what, what is the, uh, knowledge gap being addressed, uh, when to use, and what are the procedure, uh, of using it, and, uh, a code template, and some, uh, precautions.

 So basically, um, it's, it's compatible with the, like, a lot of people, like, OpenClaw or PAM, PAM, PAM-based, they use these, uh, skills to improve, uh, the, uh, model capability as well as, uh, allowing the, uh, the model to, um, perform tasks which is more predictable and, uh, following our procedure to improve the accuracy. Thank you for the question.

### Speaker 2

 Thank you very much. Um, I would, uh, sorry I have a little bit of a late in time, but go ahead.

### Speaker 3

 Can you, how can you be sure that the teacher understands why, uh, the student goes wrong? And my assumption is you're using the same model that was wrong in the beginning. So how can the model extrapolate the truth from the small errors that are there?

### Speaker 1

 Yeah, so, um, that is actually being investigated by one of our key findings. So, um, our primary assumption is that the, uh, teacher model is smarter than the student model. So that's why using the, uh, stronger model to analyze the mistake of the student can create skills that help the student.

 But effectively, for in specific Haiku 3.5, we actually find that even using the same model, it's almost like the, uh, uh, you know, modern days, like, deep, deep reasoning chain. So through this deep reasoning, uh, iteration, uh, the student can actually improve, uh, himself.

 Thank you.

### Speaker 2

 Okay. Thank you very much. If there are follow-up questions, please.

 If there are follow-up questions, I would like to go on to the answer, uh.
