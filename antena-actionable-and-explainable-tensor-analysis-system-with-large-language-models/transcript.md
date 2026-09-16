### Speaker 1

Hi. My name is Laura, and I'm a PhD student studying computer science and CR. And today I'm going to present our work on Tena, actually with a multicultural analysis system regarding neurals.

 So when you reword datasets, include multiple interaction aspects, such as user interactions or multivariate measurements. And these type of dataset can be naturally replaced into less sensors, which is just an end-to-end sort of way.

 So, for example, the social network dataset includes the interactions between users and their interactions evolve over time. This can be represented as a third mode tensor, where each mode represents user and user in time.

 Tensor decomposition is a fundamental method to discover hidden patterns in tensors. One of the most popular methods is canonical collateral decomposition, or CCD, due to its interpretability.

 So in this example, movie rated dataset, which where users rate the movie at some specific time, can be represented as a small random tensor. And each random tensor represents the hidden patterns.

 And if you look at all these columns, you can see the spectrum these matrices, which represent the related patterns for each movie. And then to understand each related patterns, we usually use metadata or labels, and they are variable.

 So for example, for each random tensor, we look at the timecape values, and then we explain that all the 20s usually do a lot of movies, and then we rate them usually around midnight, something like that. However, usually those metadata and labels are not available, or might not be the source of truth, so this explanation can be used to address this problem.

 Our main idea is to leverage the knowledge of large language models and then explain that those later patterns be in natural languages. So we proposed our system called Antenna, and it includes the two main models.

 First one is tensor analysis, which extracts related patterns using tensor decomposition models. And in the explainer model, we use LLMs to explain those related patterns.

 Also, we have a validation test, which is a request to evaluate whether the model understands the related patterns. So here's the explaining about our motivation to produce these validation tests.

 If models understand this related concept, then they can so for example, for movie examples, if the model understands the genre of these movies, when we ask what kind of movies should belong to this cluster, or shouldn't belong to this cluster, then models can identify those items.

 So this is the overview of the system. So we use the DBMP dataset, which is a DBMP dataset where each mode represents speakers, authors, and conferences.

 And then we can choose the different type of tensor models, and then we have two optional interpretability constraints to better understand the spectral entries. And then this is the decomposition output.

 So in the top part, this is the decomposition error, and then at the bottom we visualize the vector matrices so users can take a look at the vectors as it is. However, just looking at which entities are important in these vectors, this cannot be really obvious.

 So we are going to explain these patterns using so we have two submodels, which is test agnostic explanation and test specific explanation. So the first one is for general explanation, which is you can consider it as a summarization.

 And then, for example, at the first component, the first related patterns, there are these patterns seems clustered in terms of the DB area. And then the test specific explanation, this is usually defined by users depending on their interests.

 And then you ask, what's the trend? What's the trend of these?

 What kind of trend can be discovered from these patterns? And then predict the future trend, something like that.

 And finally, we have a validation part that we for this class, we inject the authors who are not really relevant to this research area, and then the models can predict which authors are not relevant. And the other one is we ask the model to predict the authors who are most relevant to this research area.

 It seems a little bit harder because usually there are more people who can index multiple research areas. So that's it.

 Thank you so much for your participation.

### Speaker 2

 Thanks for your contribution. Any questions from viewers?

 No questions from the table? Then we will.
