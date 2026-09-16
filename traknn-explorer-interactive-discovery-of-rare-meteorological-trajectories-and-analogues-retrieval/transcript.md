### Speaker 1

So we're just getting started with the next product, and it's our attempt to sort of be a forever good product for the client's needs. So first, for the context, please take notice that this is a product that is easily attributable to the probability of occurrence of epidemics or of infected sickly diseases.

 And when we later do such analysis, we can analyze role of atmospheric circulation as a role of pressure. So when they used to come out specifically with that pressure maximum data, and we can simulate our pressure max in the data we have in the base, in the data, so we can compare with similar pressure configuration what was the temperature before and what is the temperature after.

 And in this case, in addition to this statistical testing, we can try to attribute the role of climate change to the specific events. So what they would say is they would get a similar pressure map using methods like this.

 But we use this zero using signal maps, so they only look at a specific date. Like today, it's a lecture, let's say, that we're going to do, but we don't make any events according to our separate dates.

 For instance, wind storms or hurricanes transitions take place in several days, three or five days of specific pattern pressure, and it doesn't take into account the circulation. So the question of the demo group was like, can we interactively find and explain to us unusual atmospheric evolution in decades of data, especially 70 years of data?

 So to give the core idea of the algorithm, if we consider the atmosphere as a complex dynamical system, which is represented by the low-end spectrum of terms, which is very high, and what we want to do is look at the trajectory within this dynamical system. So we got the state-space trajectory or phase-space trajectories, and to analyze them, we will consider them since the atmosphere is a spatial data, we will consider a sequence of spatial data for delays, and we will analyze them with a

 signing window of delays, and we will build the space of the trajectory into points, and we will assign a score to each step of the trajectory. We will use a simple K-Neyn method, which was an obstructed trajectory with a lot of close neighbors. We have a lot of trajectory with many distant neighbors with a high score.

 And we will do it in exhaustive search. By note, we will compute the neighbors of the poor trajectories to an exact score.

 So it's quite an extensive algorithm. So to make the exhaustive search possible, we have several optimizations.

 We have high performance, less risk of routine to compute the distant routine maps. We also have optimized distant computations with recurrency.

 We are computing over a signing window, which computed the distance over a delay and decided by one day. We still have to reduce the previous computation as a classical signing-based computation, which allows us to have a trajectory length independent.

 So no matter the length of the trajectory, we want to analyze, we always have the same computation cost. And we also have CPU or GPU execution with a fatal share of the algorithm.

 So the goal of the algorithm is to have an exhaustive search, which is to have exact scores, so we can have a really fully interpretable analysis. But we want it to have a robust enough so practitioners and climatologists can try different parameters and do the analysis in a matter of few minutes.

 So to give an idea, we built a streamlined interface where the user can input the terms and it's like an. This is a parameter from many neighbors I want to compute, but with these trajectory maps.

 They can also apply a special filter where. Since we have spatial data, they can rotate those listening fields.

 They can apply a temporal filter, like which year in which they are interested. They can also apply optional hypotheses, such as removing the seasonal cycle, or they can apply a dimensional reduction, or they can also do some cosine standardization to take account of the size of the grid in the rotation.

 And then we have four different types. The first one is the low scoring, so we will score for each trajectory and compute the score.

 So we can represent the distribution of score, we can also represent the trajectory of score to find which dates are more abnormal, and all the visualizations are interactive with 20 minutes and 40 minutes, so the user can zoom in to see more details. We have a second type, which is the anomaly explorer, so the user can select, for instance, the top 10 anomalies, and we can look at the atmospheric maps that correspond to the anomalies and the specific data and the specific scores.

 We can also perform clustering. Let's say we want to take the 100 dates, and we are interested in whether we have different atmospheric regions.

 For instance, high anomaly atmosphere, or low pressure anomalies, so we can try to find different regions of the pattern. This is a blocking pattern, which is a large-scale anomaly, and we have a small-scale anomaly.

 And the fourth type is the analog search. It's what we use in event experiment attribution, which the user can provide a query like, let's say, August or June, and we will provide all similar trajectories of the atmosphere or the data you're looking at, so you can perform the analysis.

 So during the demonstration, the user will be able to interact with the world data and from the data upload to the parameter selection, implementing the algorithm, and also visualize the different maps and perform different queries to find the similarity for example dates. And the main example will be from the phase of European sea levelation.

 This is the example of the clustering. You can see high pressure anomalies or low pressure anomalies in the different bases.

 So to wrap it up, we have Proclaim Explorer, which is a proclam algorithm to perform the exhaustive search of rare trajectories, which allows us to move the two analog methods from snapshots to analog, which are only a single attempt to face this trajectory of a single data. And we have a 2-1 workflow from the data upload to the retrieval of the score and the different visualizations.

 And we have a jittery acceleration, which makes the exploration feasible. For instance, from the 70 years of daily grouping data over 50,000 routes, and this is the two or three minutes from the top, which is the.

 So you can try the algorithm and experiments. And last comment is that the demo is built for atmospheric analysis, so it's partial thing, but the algorithm itself for phase-based trajectory works for any data in the system and can be also applied to routine high-enthalpy size analysis.
