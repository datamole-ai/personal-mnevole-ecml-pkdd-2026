### Speaker 1

It's a notebook.

 So I'm convinced that explaining transformative language models will be a central challenge that us as a research community will face in the near future, and why. Let me try to convince you.

 All of us, researchers or not, are using transformative language models, maybe in the form of chatbots, on a daily basis. But we don't worry too much about their inner workings; we just give them some prompts and see what the output looks like, and we're happy with it.

 Well, that's bad, because transformative language models are being deployed very often in high-stakes applications, for instance in medicine or in the judicial domain. And even worse, research shows that models can really be harmful with such phenomena as jailbreaks or hallucinations, and sometimes the harmful behavior even occurs in really unexpected ways, like research on emergent misalignment shows.

 And if I didn't convince you yet of the importance of explaining transformative language models, we can also look at more authoritative voices, also outside academia, that are nowadays calling for the importance of interpreting such models. And this has also reached general audience news outlets that are covering the topic.

 So, given the importance of this challenge, we wanted, as in our research lab, to get into this topic, and we started to study in depth different explainability methods for transformative language models. But especially, for example, me, that my background is not very heavy in model language processing, we found ourselves a little bit lost in this maze of different explainability methods that were being developed at a very fast pace, and the resulting landscape of methods was really becoming harder and harder to navigate.

 So we started wondering how could practitioners or newcomers identify the methods that would match their needs so as to actually adopt transformative explainability for the models, instead of just using them without worrying about what's going on inside. So this is the reason why we built the Virgil Navigator.

 This is a subset, a portion of the interface of Virgil. Actually, the default one looks a bit nicer, but anyways.

 You have, on the left, a column where users can submit queries describing what they need in terms of explainability. In the center, Virgil shows methods, explainability methods, that match the user needs.

 And in the right, the users can select particular methods that are of interest for them and play with them, look at their capabilities, and so on. Each of those columns, left, center, and right, corresponds to one of the core components or pillars of the Virgil architecture, which we call the knowledge base, the retrieval engine, and the exploration engine.

 And now we are going to see each of such components a bit more in detail. The first component is the knowledge base, which is just a collection of manually curated method cards.

 Each method card corresponds to a method, an explainability method, and it contains structured metadata, an overview of the method, capabilities, so what it can do, strengths and limitations, as well as useful links to references and available implementations. Then we have the information retrieval component, which processes the queries posed by the user.

 The queries can be in the form of constraints, for example, the architecture of the model under consideration, or the macro task that the user is facing. And Virgil filters the explainability methods based on their constraints.

 But then Virgil is flexible and it also supports soft constraints or preferences, such as the level of expertise required to understand the explanation output, and free-text queries. And Virgil uses the preferences and the free-text queries to re-rank the output methods, for instance, based on the similarity between the free-text query and some relevant field of the method card that are of interest.

 For example, the overview will be the field that is given more weight in this similarity search for re-ranking the output methods. Finally, we have the execution engine, where the user selects particular methods that Virgil has retrieved as matching their needs, and the user can inspect them interactively, can compare different alternative methods side by side to see their difference, and can also execute selected methods on custom examples to see, for instance, what the output is in some particular example, so they are able to explore the methods

 also on some toy and custom examples. So for now, we have seen the architecture of Virgil, however it is formed. Now we are going to see how can we actually use it in practice, but also who can use it and who should use it.

 Well, Virgil is designed primarily for newcomers, practitioners, as well as for researchers, but for conducting preliminary analysis. Also for teaching, it can be very useful, and for collaborative teams to facilitate the discussion of explainability methods for transformative language models.

 And finally, also for users who need the library to perform extensive analysis on their own data and models. Now, that's not true.

 This is not the case, so I would like to emphasize that Virgil is a router that maps a user request to some explainability methods that match the user's desiderata, so what they're looking for in terms of explainability. But it's not a library that you should use to perform in-depth analysis on your own trained models on your own data.

 We also conducted some very preliminary user studies to get some initial feedback, and 7 out of 10 participants agreed that Virgil's explainer description are useful. Out of 10 agreed that Virgil is intuitive.

 And finally, 9 out of 10 would recommend Virgil to a colleague. To conclude, let's walk through a nice, complete illustrative example.

 We consider a very basic task, which is a sentiment classification task, where the user inputs the movie was good as prompt to a transformative classifier, and unsurprisingly, the classifier predicts good sentiment. First of all, the user starts to wonder which input tokens drop the prediction.

 This is a classic question in explainability, and Virgil retrieves 21 explainability methods that are local attribution methods that can be used to answer to help answering this question. Then the user selects a couple of them, a couple of classic methods, and inspects their characteristics, and then runs them on the custom input to see what the output looks like.

 Then the user gets a bit curious and starts to search for other types of explanation. For instance, they ask, what could be a minimal change to the prompt that fits the prediction?

 To answer this question, Virgil suggests using counterfactual explanation method, and the user selects one of them and sees some sample outputs of counterfactual explanations. The user goes even further, gets a bit into a bit research mood, and starts to think, okay, attribution tells me that the token would matter for the prediction, but what features does good activate?

 And to answer this question, Virgil recommends looking at some example of interpretable features through sparse out encoder. And so the user in the platform can look at, inspect some features that really activate strongly for the token good in the input, the movie was good.

 And finally, the user leans even more into the mathematics and starts actually looking at what latent space looks like in geometric terms, using some matrix decomposition techniques. This is the end of the example of the presentation, so thank you.

 If you would like to contribute to Virgil, feel free to do it. We welcome you adding your favorite explainability methods or your own explainability methods, and you can also try Virgil online in a few spaces.

 Thank you.
