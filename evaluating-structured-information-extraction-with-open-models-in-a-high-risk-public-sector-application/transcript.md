### Speaker 1

So, um, I'm talking about something I did about Wispr and our university, and it relates to— we were basically following the idea that, okay, many things in the public sector have room for improvement. We've never tried to escort into `<name>`, or so many people have talked about, and I'll talk more about the details of the application, but to connect this to the, uh, to the ideas of the workshop— Ah, oh.

 Okay. Ah, yeah, right.

 So, uh, to connect this, let me start with an anecdote. One of my favorite anecdotes, and one of my favorite figures, from all various papers.

 I've been working in the industry for, like, 8 years, at some big tech company, at a diversity company, and when I stumbled out of academia, it was really like this: I'm teaching the data, I'm using machine learning, and we get some predictions, and then when they're in reality, it actually looks like this. So this is a paper around the group around `<name>` at Google, and they've been doing something similar without computing, and I'll show you on the screen.

 And I'm mentioning this because, so the boxes are proportionally time you spend on each of these tasks, and as all of you know, the machine learning part, which we were really behind for in the industry, we don't spend a lot of time on that. And also, in today's talk, and this is why I'm bringing up this figure, we have spent more time on this, this, this, and this, than on the actual machine learning part.

 We didn't train new models, we just, you know, we had this, we wanted to build a system that works. So what was that system about?

 So when I had this discussion about how we can build AI systems that helps to improve the public sector, there was one idea from a colleague who's sitting here, who suggested we should support our data science program. We did, we had one of the first data science programs in Europe, in Manhattan University, and we were getting, like, 550 applications for 20 seats.

 So that professor, who was running the program, needed to go through all these applications, and they looked very, you know, heterogeneous. There are certificates from all kinds of universities around the world, and everyone knows, you know, ChatGPT, it's like, well, this should be easy, right?

 I can go up and get ChatGPT, but you can't. So we had this European AI Act, which classifies this kind of application in the public service as a high-risk application.

 And it actually does make sense to, you know, treat these cases with care. As you know, we are, we are constantly, you know, we are higher force in our economy risk act some years ago, thanks to the people who are in charge of our systems.

 Not much did happen, but some hospitals were collaborating on that, and just last week the Berlin administration got back really badly, and, yeah, they didn't pay the, you know, 30 Bitcoins or what, and now a lot of really secret data from the Berlin administration is out there in the environment. So it doesn't make sense to, you know, follow these regulations.

 And that's what makes it extra hard, because the data for training these models is not there. So we have this data science program, and we wanted to check how well these open weight models work for that application.

 And we had only a couple, you know, open weight models, no training data, just fine-tuning, and very few data points that were time-limited for this use case. And it's also a very specific use case, which, you know, requires some dedicated metrics and workflows.

 So the problem today is the following. So this is one of the— so oftentimes these applications are, like, hundreds of pages, and we don't know what there is to do there.

 We're just interested in the transcript of records, which has this tabular structure. Each line is a subject that a, you know, whether you did it or a wrote an exam, and we just want to get some, you know, which feedback was, which topic the course was, grade this for, and the credits.

 So we can, you know, basically compare that and say, yes, it would be registered for the course. And there are, there's a lot of research on this, but the specific requirements that we have related to, you know, training data, and we can't send the data anywhere, so that makes it difficult.

 So that's the— and by the way, I should mention, all this was done by `<name>`, who unfortunately can't make it today, but all this, you know, system structure we also built and envisioned by him. So how would you do that?

 You can either just OCR the text out of the documents and then dump that into an LLM, or you dump it into a vision board, essentially. And those are the two options that we tried, and there are different OCR approaches that you can take.

 These are some standard options. There are many more, and in other, you know, some other research, we've also looked at many more of those.

 They have pros and cons, but the main difference is that some of them preserve the structure, and some don't. So some give you a table, and some don't give you a table.

 And these tables, sometimes they're open, sometimes they're not, so it's very heterogeneous. Then there are vision language models that we looked at.

 So `<name>` took the latest ones back then, I think in 2025, and now they're, of course, much better ones, with, you know, more parameters, but as we will see, not, you know, I mean, capacity is not the only factor here.

 So, yeah, let's jump right into the results. I'm sorry that in the first version that I uploaded, someone took off the header, but the header here says Precision Recall and F1.

 And it's a very conservative metric. We wanted exact matches, so we could have also written about, you know, hit distances or other kinds of metrics that are, that would make it look better, maybe higher.

 But here, what we see that in the best, we looked at all combinations of all OCR systems plus LLMs, and the best OCR system in our case seemed to be this minor Q library plus some WEN model. And also here you see that not necessarily the highest capacity ones, you know, they don't score a lot better here than, you know, compared to this 40B WEN model.

 So that's, that's the best OCR LLM pipeline. And here, we're good, right?

 KPLMs. The VLM models are, they work okay in a zero-shot setting, and if you compare them all together, you see that it's the VLM models here in Selmond, Cover, and, you know, they are pretty far up there compared to the OCR plus LLM sessions.

 So, and that's already all we have. I mean, there's more in the paper, and there's, I mean, everything is open source, except for the data, of course, because once you anonymize that, you know, it basically loses a lot of the meaning stored data.

 If you anonymize the PDFs, essentially. But this is something that I wanted to highlight in my summary.

 So, overall, these VLMs, they seem to be OCRs plus LLMs, and that could be due to the fact that a lot of the structure is lost when you OCR what you're interested in out of the PDF.

 And the structured information that's gathered from the OCR systems helps a lot for the LLMs to get it right, essentially. And what we found when looking at these different, you know, super-precise models, all parameters are not always better.

 And what the main finding that I would like to point out is the, you know, the requirement of data. I mean, all the systems that we are using, they make that task look so simple, because, you know, all our students screenshot our, you know, exercises all the time, and then, you know, that works, right?

 Why does it work? Well, I mean, these companies have a lot of data, and it is very highly regulated.

 For good reasons, highly regulated in our immersive public service. We don't have that data.

 What hours do we collect that data all the time? And I guess one of the callouts that I'd like to make is that there's a huge value in, you know, new scientists collecting, annotating, curating, and sharing that kind of data to improve these kinds of systems.

 Thank you.
