### Speaker 1

Hello, hi, this is `<name>` from International. Today I'm here to talk about Wispr Flow, and we have two valuables in our product: Wispr Flow and the product called Wispr Flow. The main motivation of our work is that in existing data systems we use different propagation strategies to extend the knowledge-generated responses, uh, by estimating the context unit importance, but they completely ignore, uh, whether the Wispr documents are actually relevant.

 And by see- by passing the HRL documents to the model, we made the model, uh, is generating the responses with some, uh, less, um, confidence, less, less confidence. That leads to unreliable explanations, where we cannot determine if the generated answer is actually grounded in the, the Wispr documents, which we consider data as relevant or irrelevant.

 So this leads to our objective: when we establish an interactive framework, uh, to evaluate whether the Wispr documents are actually relevant or not by comparing between multiple Wispr flows. And we also compared multiple propagation, uh, strategies to identify which propagation strategy was better, uh, for the explanations.

 And we improved RAG answer faithfulness by combining this propagation with similarity scores and material relevance scores, along with model's token, uh, token model confidence. So this is our proposed framework using RAG.

 Here we have, uh, multiple modules and configurations, uh, that we can play with. So it contains three main components.

 One is the Jira Explorer tab, uh, which is for analyzing the Wispr documents and their relevance. And the next one is the Explain RAG tab for generating propagation-based explanations.

 And the, uh, next one is Comparative Analysis for comparing different explanation scores and their, uh, and their confidence.

 So in the, the Wispr Flow Explorer, we have, uh, different Wispr flow settings. We have multiple Wispr flow scores for, uh, let's say fast, dense, and high-throughput Wispr flows.

 And we can also configure different settings here, where we can take, uh, uh, custom, uh, data set of custom, uh, concave documents and pass them through the different Wispr flows. And in the, uh, mod in the models, we have tested, uh, from small models to big models, uh, where we have, uh, RAG, RAMA, GAMA models.

 And we also have, uh, uh, different generation settings, where we can also, uh, play with the comparation and, uh, the procurement of, uh, the models. And we have, uh, a lecture on two benchmark data sets, the Benchmark Cost and the GPS QA data set, where we also provide, uh, to configure on the custom data sets that we want.

 Uh, here the important thing is the explanation scope that we have, where we have multiple explanation levels. Here we refer to it as the explanation level that we choose.

 It can be a word-level explanation, or, uh, sentence-level explanation, paragraph-level explanation, etc. But, uh, if you choose the particular unit that you want to, uh, test, then based on the propagation strategies we have used multiple propagation strategies like, uh, uh, auto-manipulation, unveiling monologue, etc.

 So all these propagation strategies you can test, and here you can identify which propagation is, uh, propagation strategy is working better for the explanation level that you have chosen. And in the predicted, it basically compressed the answers, uh, that we, that were generated after proving the difference, and then identifies which one is, like, changing.

 And, uh, those pro- pro- prohibited is the most important, uh, token that the model has actually relied on in generating the response. And these are the three, uh, scoring strategies that we have worked on.

 One is, uh, uh, the propagation, uh, one is the propagation with similarity. The second one is, uh, the super-weighted, and the third one is confidence with confusion.

 So in, in here we check, uh, whether changing that particular unit changed the answer. That means the model is actually relying on that particular unit to answer, uh, the question, and we consider it as important for that.

 In the retrieval scores, we are adding the re uh, retrieved scores from the, uh, retrieval, where it kind of, uh, checks does removing that unit comes from the top relevant documents. So it basically combines propagation with similarity with the retriev- retrieval scores and, uh, those.

 And in the confidence drop, we are checking if removing that unit reduces the model's confidence answer. That means the model is relying on that unit, which is mostly important, and it is also coming from the top relevant documents.

 If the model's confidence drop, then there is something, uh, I mean, the model is not, uh, relying on that particular unit as important while generating its response. So this is the system demonstration.

 Uh, this is the system that we have. On the left side you can see the toolbar.

 There are multiple configurations that I have explained now. You can, uh, select whichever config configuration that you want to analyze here.

 And the main window contains only three tabs in the, uh, where in the Retrieval Explorer, for example, if you take a question here and you want to compare between several retrievals, you can, uh, add the question and compare the retrievals. Then you can compare all the three retrievals, uh, and then you can use all of the documents that each retrieval has provided, along with the scores that each retrieval has given to that particular document.

 Here you can understand if it helps us retrieving the document with that particular score, uh, but in the, in F-25 it's not retrieving the same document with the same score, it's retrieving something else. And in the handbook you can see the combination of the documents that it actually, uh, actually retrieves and then passes to the document.

 And in the Explain RAG tab, here we can, uh, get the explanation-based, uh, propagation-based explanations. So when we pass the answer and we select a different retrieval, for example, Dennis retrieval, it gives us the answer, and that kind of adds to the tokens here that on top of this particular unit the model has actually relied on to give that, uh, particular answer.

 But when we change it to the handbook retrieval, it changes the answer as well as the most important unit that it has answered. Saying that, uh, different retrieved units have different, uh, impacts and different, uh, confidence drop.

 Here as well. And in the, in the comparative analysis, uh, where we can compare these three scoring stra- strategies on propagation with similarity and, uh, adding propagation with similarities to the retrieval scores, along with the model confidence and confidence.

 So here if we see the unit between all these three, uh, scoring strategies is same on the, uh, on the particular unit that has been highlighted, then we can rely on that particular unit and consider that unit is actually, uh, the most important unit the model is relying on. So if you're curious to know more about our, uh, framework, please join the interactive lab.

 Thank you.

### Speaker 2

 Any question? Any question? Okay.
