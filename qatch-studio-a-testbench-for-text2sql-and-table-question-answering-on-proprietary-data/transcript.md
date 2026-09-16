### Speaker 1

Okay, so, hi everyone. My name is Simone Carpentier, and I'm a PhD student between Polytechnic Torino and UW France. So today I'm going to present you this demo; it's called CAP Studio, and this is a framework that automatically generates text to sequel and tabular response with benchmarks, starting from any kind of tabular data.

 For the folks that are not familiar with this task, these are, in theory, pretty simple. So you start with a natural language question and a database, and the output is a sequel query in the first case, so for text to sequence, for text to sequel, or the actual answer in the case of the second task, so the tabular response framework.

 So what is the problem that, like, builds, like, this work? So the main idea is that if you have a company, I guess for example, and you want to build, like, some agents that works for text to sequel, what happens is that you go on the, um, most famous benchmark for this task, like Spire or Verve, and you get the top ranking models.

 And in theory, these are pretty good models because you get, like, 80, 90 percent of execution accuracy. But then what happens is that you use these models on your data and everything breaks, so you're going to get a lot of complaints by, by the customers.

 So these have, uh, several issues, but the one that we're going to see in this demo are the unfamiliar schemas. So what happens is that the schema are different from the schema that the model is seeing during training.

 And the second one is that it's specialized for tabloids, so usually you get some domain expert jargon inside, inside the table. And also, this is, uh, usually in, in the literature, you'll usually find text to sequel models, but what happens is that the customer gets the query, but usually it's not an expert of sequel, so it would be nice to have the direct answer instead of the query as output.

 So what we come up with this framework that is, if I have to summarize in one sentence, is a dynamic benchmark generator for this task. So basically, the user provides the database, actually it can be any kind of, any type of tabular data, so this demo will also use CSV file for couple.

 Then you tune some parameters of the framework in order to specify which questions you want to get. It provides also the models that you want to test.

 And what happens is that this framework automatically generates the benchmark, executes the benchmark, and then evaluates it with the most common metrics in, in this task. And the output of this framework is a nice dashboard that anyone can actually go through and check where the model are actually failing.

 And you get a ranking of the models that now is not based on stuff benchmark, but is based on actual data.

 So why not just use, like, some common datasets? As I said, I mean, the beauty of this work is that now you can have a dynamic benchmark, so you can test actually any kind of data, so also medical data, also some data that was not billed for text to sequel or tabular response for any kind.

 So this framework is based on three type of steps. So we have generation, execution, and evaluation.

 So the generation is based on a previous work that is called CATCH, and in the generation is a template-based engine that automatically generates given the table schema and the table values, the natural language questions, and the sequel query.

 The second step is that is the execution, and all the framework is, uh, gathered. I mean, for this demo actually we use some API, but the idea is that the company and the user will use their local models to test whether they are actually working on their data, and this is done for privacy concern.

 Because the main idea, the main concept of this work is to work with some data that cannot be released outside the company.

 And finally, we get also the evaluation. So the evaluation is based on, is based on different types of, different types of metrics.

 So on the left you can see a workflow where basically we use Claude to, to check the distance between the forms. So on the left there are the corporate data, on the right there are, there are standard benchmarks with Spire, and the longer the distance, the longer it's the different performance of the models.

 So now you can actually appreciate what is the answer there. In fact, second call, you get a roundabout where you can, you can actually go into detail in which part of the query are actually breaking the model.

 Okay, so you can try yourself. I think we will also be here around 5, but if you want to try it, this is on hiring days, and we're just having a little bit of a change soon after.

 So if you have any questions, I'm open.

### Speaker 2

 So can you show me the question?

 So we can do test the query, we can go through the last.
