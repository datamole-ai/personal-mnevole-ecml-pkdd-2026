### Speaker 1

Hi. I'm Evan Marshall, from the marketing side. For Marek, today I will talk about my subject matter: a Siemens supervised retention plan for low-acuity chair accessibility.

 So basically, I worked with wheelchair navigation, and there are certain rules of, like, a detailed parallel ETA that is for such that minimum clarity for a hallway should be clean to be wheelchair accessibility compliant, and also there should be cars for each 200 meters in a hallway. And there are different such regulations for accessibility, but most of these regulations are on paper but not always implemented.

 And sometimes these regulations are implemented, but there are some temporary barriers that are this types of, like, this specific sidewalk is accessibility compliant, but this specific barrier actually hampers accessibility for wheelchair navigation.

 So we also see different types of barriers. Those are all on our window environment.

 If there is a snowfall, those sidewalks become wheelchair non-accessible. And also, if there are stairs or there are broken sidewalks, those sidewalks are not wheelchair accessible.

 And especially in the urban environment, you see there are lots of sidewalk and roads. Even in Italy, there are lots of roads; those are completely blocked with rocks.

 Those are not wheelchair accessible. And sometimes these types of roads are actually impossible for wheelchair users.

 It is impossible for navigating on these types of roads.

 So our team actually did approximately interview 17 people and established with all them what are their needs and how to solve, like, how they would like to solve this problem.

 And we picked people from different types of nationalism, and we interviewed them. And our team came up with these three types of this problem.

 One is types of wheelchair. What types of wheelchair are actually used by those users?

 Like, there might be manual wheelchair or lift wheelchair. And also the environment, that is, like, the building environment, sidewalk, and there are different buildings.

 And also, like, there are different difference of the difference of different users, like, based on the different strain and the different types of, you know, cars and wheelchairs.

 So based on these studies, our final goal will be to create a navigation system. So basically, we would want to describe the problem.

 The problem is people want to, like, if we want to go want to go somewhere on a specific building, let's say today there was a team of talk on a developed building, and I was trying to go there, and there was even I have been directed by some people, and there was a stair for the way. And there are also alternative ways.

 So what if you think about that, like, I'm a wheelchair user but I want to go there. If someone directed me through a road that contains a stair, I won't be able to, like, go there on that way.

 I need to be here from down. And this type of information is not very available.

 And also, like, it is for Google Maps. A wheelchair can go somewhere using the Google Map that provides information for pedestrian, but not for wheelchair users.

 And also for Apple Map and also Open Street Map. All these maps provide directions for pedestrian, car, or artificial car, or wheelchair users.

 But we need the both.

 So for this specific paper, our contribution will be wheelchair dataset that is we collected data throughout the USA and also in Vietnam to make our dataset diverse. And we trained our model to, like, classify different types of surfaces, like what surfaces are there.

 And finally, like, that is part of our other project that is finally we published an application that provides wheelchair accessibility navigation.

 So our target for our implementation strategy will be addressed mobile phones on different places of the wheelchair.

 And using mobile phones, I will make sure that it's accessible. That is from an information data.

 And we collected those datasets.

 So our dataset is available on this specific dataset that is 183 hours of data and more than 52 videos straight from our IoT sensors. And we have just collected and divided it into different categories.

 So these are the different variety data, types of different surfaces. Here, you can see this is a this is a lot of data on specific surfaces.

 Most likely it's not possible. That is on the tiles, individual tiles.

 So those vibration patterns produced by different vibration are different from the captured by the external sensors. And these are our data, which is across all over the world: Germany, then Germany, Austria, and also Vietnam, and also in the USA.

 So these are different types of sample surfaces that we have, like, came up with. And later we will develop our model to classify those surfaces using our data.

 So first step is pre-processing. We firstly we print our data, then apply different types of features.

 Like, here we see that handheld filter, then we did a straw removal. And also we had to resample based on, like, different models of the phones to make those data safe.

 And then we doing normalization to make those data trainable. Then we did texting speed.

 And then, like, then we found that after some investigation, we found that there are some, like, common types of vibration patterns upon different types of surfaces. Let's say concrete and, like, concrete and small big block that kind of, like, similar types of vibration pattern.

 So we had to match them and we came up with seven different common surfaces that we can classify.

 And then we tried to train our model but another problem we faced that, like, all of our data was not limited. Limited means we didn't collect our data.

 If we are collecting on a big surface, we reported that, like, this is a big surface. But we have other data that those are not reported properly, that this surface is big.

 So some of our data had labels and some of our data didn't have the labels. So we used the same supervised clustering approach, where some of our data, like, training data was labeled and some of it was not.

 Then we trained our model. We used GXS data.

 It's on a G-axis. And we split the data into different layers.

 And on the layers, you see how we used, like, transformer architecture. And, like, on our like, you see the MSCB, MSPCB, and the XP space, and then the CAN space.

 They are being emptied of those emptied of those types of data. And then we applied our enhancing mechanism to classify those data.

 And finally, we combined our loss function with two different types of loss functions. That is, one is reconstruction decoder for the modeling of the surface type.

 And also we had to call the label data. We used cluster edit and we combined by labeled categories.

 And finally combined with the loss function to train our model for our models. And this is our result.

 So our result is not perfect, but here you can see that on our surface encoder, encoder it can actually on the right side of the surface encoder, that is, it can differentiate different surfaces. Labeled space.

 Though those line are those points are not, like, clearly separated, but it can separate. But what you can see on the right side, there are those existing model cannot actually separate those points.

 Those are actually sensor data. The existing model cannot actually really separate those vibration patterns.

 And here, that was for, like, the whole dataset. And our model's performance on the labeled data.

 So those are, like, carefully collected on different fixed surfaces. And we can classify and, like, push away those different types of surfaces.

 So if you're interested in the architecture, you can, like, visit our YouTube pages. Our posts are uploaded there.

 And finally, what we're doing in our work. Our current approach has some limitations.

 Like, try to collect data using those using those wheelchairs. But wheelchair was slow-moving with people and, like, it is, like, kind of impossible to manually see using the wheelchair.

 So we're collaborating with a team which takes us and develop a system for that. It works continuously.

 We have built in sensors and different other sensors. And we can collect data much more faster than wheelchair.

 And using those sensors, we can actually train the surface function and, like, how to apply surface. We also have cameras so we can also, like, come up with a wheel or other parts of the accessibility of the surface.

 And this is our, like, final product that we were developing from. So currently, it is only available for, like, Ohio, Wisconsin, and Madison.

 That's the different states of the USA. But soon we will, like, make sure the whole world.

### Speaker 2

 What was your sampling rate?

### Speaker 1

 Sampling rate was, like, even the lowest sampling rate was 100 Hz to 250 Hz. So, like, sometimes for accelerator, I had to resample.

### Speaker 2

 Okay. What do you think is the meaning of the sampling rate that the company is sure to achieve this kind of classification test? Because often, like, you have, for example, commercial exposures.

 Then they are quite cheap IMU and with the storage, maybe they don't do it at more than 10 Hz scale. So do you think that that's okay or is it too low?

### Speaker 1

 So for this object, I would say that, like, I think there's a limit of how much higher sensitivity we can give. Like, I think it's 500 or something based on the machine. That's why I will say so it's very good.

 And also, for wheelchair, we can actually use lower sensitivity because it is a slow-moving vehicle. But, like, if we want to use, like, high-speed vehicle, like scooter, then we need to figure out that, like, which sampling rate we will want depending on the speed.

 Because we want, like, 4 hours sensitivity. We'll use manually.

 Like, we do 10 seconds of the walk and, like, if our goal station was 100, like, 60, 60, we chop it with 6, 10 seconds of sensitivity. So we actually that is the goal that we need to figure out what will be the best sampling rate to, like, even in policy that can, like, provide this specific window, like, 10 seconds or whatever the window.

### Speaker 2

 Sure. I want to get started on that question. But more particular on how you standardize your process of data collection.

 Because when you design this for wheelchair model and actually for real size of the suspension system, that affects your sensor.

### Speaker 1

 Yeah. So our current model, what we're using is, like, we're, like, we does this basic data processing that helps to handle all of this. But, like, for, I think, the suspension system or wheelchair vibration pattern differs, like, much.

 They might correct some of it. But.

### Speaker 2

 So last question. Give me some options. Information I already appreciated and I hope you will be able to drive that for which is for disabled people.

 I'm so honored to have you in AI for a couple of years in the industry. So this will be good.

 I have a question. Why did you place multiple mobile phones rather than buying the traditional IV device that you put in the middle of the chairs and you get a lot of speed?

 What was the motive behind that?

### Speaker 1

 Yeah. So, like, our initial plan is to, like, collect data using crowdsourcing. Crowdsourcing.

 So that, like, so like, if we use a mobile phone for a person, even part of wheelchair actually hides separate, like, different way where we can go through. So that is why I utilize different parts.

 And, like, finally, our goal is to, like, crowdsource the data. Like, crowdsource the data so that, like, any random user can download our application and install it on their mobile phone and, like, get up to somewhere on their wheelchair.

 So that, like, when they move, like, using our application, when they move from the city.

### Speaker 2

 So you use that to pull download and install it.

### Speaker 1

 Yeah.

### Speaker 2

 And then you actually push the data to the wheelchair.

### Speaker 1

 Yeah.

### Speaker 2

 Okay. Thank you for the question. So let's thank the speaker and.

 So we ended by providing experience using subjective data in our study.
