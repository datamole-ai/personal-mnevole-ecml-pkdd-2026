### Speaker 1

I'm hiring by 740 dictation and 238 for post-production.

### Speaker 2

 Thanks, everyone.

### Speaker 3

 Hi everyone, Roberto Benitez here from American University, with a finger crossed HEH University. Hello. Today we're presenting PyTab, our library in framework for continual anomaly detection.

 So let's start with the motivation. If we look at the landscape of available software libraries for anomaly detection, let's consider two particular issues: adapting to new conditions.

 So we have static models, and static models think about a scenario with three concepts: C1, C2, C3. And so we have the first occurrence of C1, then new normal counts, and then we have C1 again.

 So static models will detect on the first concept, then they will flag the new normal, C2, as anomaly, so they wouldn't adapt to C2. And then C3 comes back, and they will perform as expected on C1 and C3.

 The online model will adapt, but then as the recurring concept C1 appears again, they will forget. And the continual model has this disparata of performing well on the new concepts and dealing well with the recurrence when C1 reoccurs.

 So let's look at the landscape of available software libraries. They consider two axes: anomaly detection and continual learning.

 So we realize that there are many libraries for continual learning, mostly for RL or research education, and at the same time there are libraries for anomaly detection. Very popular ones are PyOD, Anomaly, PySAT, but we found nothing at the intersection of these two.

 So essentially we have models that are really good for continual learning, but they don't deal with the challenges of anomaly detection, and very good anomaly detection models that don't deal well with continual learning challenges. And so we sit at this intersection, try to work on continual anomaly detection, propose scenarios, strategies, and a modular library to deal with this type of scenario.

### Speaker 2

 Okay. So our framework focuses on continual anomaly detection, and our goal was to make it as modular as possible, because I think we all know that sometimes it's very hard to use research software. So basically there are four concepts here, four ideas.

 One is dataset, which defines what arrives and in what order. So usually a dataset is a stream of concepts, tasks, where each task is a distinct normal operating regime.

 So for example, one type of behavior, human behavior, or one server that we are monitoring in intrusion detection. Then you have the scenario.

 So scenario answers the question, what does the model get to know? So does the model know whether there is a change of task?

 Does the model know what task it is currently processing? So does it know whether it's jogging, or walking, or sleeping?

 Or maybe the model has to find out on its own. Then we have strategy and model, which defines how so strategy defines how should the model be updated on the new concept.

 And model can be mostly just anomaly detection model. So thinking about example, we can have autoencoder, which is standard anomaly detection model, and then we can have strategy, continual learning strategy, that is supposed to ensure that the model doesn't forget, but it can adapt.

 Because all of this is about decision between forgetting and adaptation. And then we have callbacks and metrics, which follow the similar idea from PyTorch.

 So we want to monitor the run. We want to, for example, monitor the time, we want to monitor the metrics across the time, we want to monitor transfer and retention.

 So here is an example. So first we start with creating the dataset.

 And concept dataset means the dataset that is divided into multiple tasks. So what can be the task here?

 Let's say, for example, in intrusion detection we can have five servers that we monitor at first, but then along with the time we get another server, and another server, and another one, and our detector has to adjust and learn how to monitor more and more servers to detect anomalies. Then we have model, which can be simple autoencoder or something more advanced.

 Strategy, here we show EWC strategy, so Elastic Weight Consolidation. Callbacks that define for example, in this case we define concept metric callbacks.

 So we are monitoring specific metrics across the time. And we have time evaluation callbacks, so something that monitors the execution time.

 And finally we create scenario. In this case it's concept incremental scenario, so the model knows that the task changed, but it doesn't know what task it is.

 And we just provide dataset strategy and callbacks. And we do scenario run.

 This is the example that is enough to run the whole pipeline to get the results, and then you can just change one specific thing. You want to devise your own strategy, you can just change the strategy.

 If you want to try another dataset, you just change the dataset. So this library is focused on modularity, components, and making it easy for everyone to use.

 That's what we are aiming at, and you can assess on your own whether we are successful. And the most important thing that we are trying to measure is forgetting.

 So here we have performance heatmap, and C1, C2, C3, C4 are the tasks. So at the top here we can see the performance on task one after learning task one.

 And here we can see, for example, that when the detector learns task three, C3, then the performance in the first task drops significantly, from 0.94 to 0.59. And this is what we are aiming at.

 So showing forgetting and then preventing forgetting.

### Speaker 3

 Okay. So we started with tabular data, and now we're trying to incorporate more and more modalities. So vision is very popular in continual learning, so we're trying to deal with vision, but from an anomaly detection standpoint.

 So we are starting to incorporate model backbones, continual strategies, and so on, and datasets in this domain. And then also time series, and videos are on the roadmap.

 Still, they're not included in the current release, but we're aiming to release it soon. So here is a Python notebook if you are interested in starting, and with a very simple scenario.

 It just shows you how you can package the dataset, the strategy, the model, and then run the scenario. It's very simple, and it's a great entry point, and then you decide if you want to install the library or not.

 And we're making a lot of effort into trying to publish real-world benchmark datasets. We started with cybersecurity datasets in a popular domain, and then we're slowly adding more datasets.

 As I mentioned, industrial manufacturing, sensor data, invention, and so on. But we have an organization in which we are adding these datasets that are pre-slated into concepts.

 And sometimes we have curriculum learning scenarios, easy to hard, hard to easy, random, and so on. The advantage of hygiene phase is that you can import the dataset as a one-liner.

 Then we're also raising awareness on this topic by organizing workshops. This is the second edition of our workshop at ICDN conference.

 It's too late to submit papers this year, but anyways. We're going to stream the event, which is going to be in November, and we're going to post about this on LinkedIn.

 You're welcome to submit your papers next time. So this is all.

 Thank you for your attention. If you would like to get in touch, here is a link with the most relevant resources if you are interested in this topic, and if you would like to contribute, we're always open to new contributors to the library.

 Thank you so much.
