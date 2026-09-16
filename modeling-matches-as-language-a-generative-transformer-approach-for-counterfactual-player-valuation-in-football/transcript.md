### Speaker 1

Good afternoon, everyone. My name is Gideon Holm, from Transformer University of Seoul, and today I'll present my work, what I would like to mention as a brief, celebratory transformer approach for counterfactual play evaluation in football and in chill, SpotGPT. In summary, we treat a football match as a sequence of contents, and we train a GPT-style model to predict next events.

 Most saying the model can stimulate the player with the news, new context, or new system.

 Okay, and— And why is transfer simulation is— uh, transfer prediction is difficult because football is lost, multi-agent environment, and it has, um, it's a complicated environment because the football player's action on the pitch are never independent.

 They depend on the player's sector role, and teammates, and the opponent, and the match state. So, um, you cannot simply carry over the best performers into this new team.

 So, um, when a player hasn't changed his team, the whole interaction pattern around them totally changes. So, um, SpotGPT addresses this dist- distinctionship problem as a simulating a transfer, and inside the team he never played before.

 And how does SpotGPT model football? Football.

 So this is our data architecture, and we understand how to— we treat football match as a language, a sequence of talk to, and even it's like a sentence, and its core attributes are rewards. So, so basically— So to feed this data into a general transformer, we serialize the team-play segment into a serial, uh, sequence of talk to.

 And the sequence has two parts. The first part is context block, as you can see on the upper side.

 The context block has two team IDs and a line of, and the current match state, such as period, minute, scoreline, and current statement. And, and the second part of the sequence is play setup.

 We plot all the team-play events into a 10-dimensional tuple, including team IDs and role of player, action type, and starting event coordinates, event time, and the outcome. And we maximum— we limit each episode to a maximum of 100 events, and if the episode has more than 100 events, then we use a time window method.

 And, and SpotGPT is ba- basically GPT-based auto-reverse sequencer that predicts, uh, each field of the next event one by one. So this will show an example of the, an inference.

 SpotGPT predicts the next action likely to be a cross, and the definition is the current box, and it is likely to be fair. So for this architecture, we have three key modifications.

 The first is, uh, player ID remaining in the input, but are often excluded from the prediction target. It might be confusing, but, uh, it blocks the player embedding depending too much on team identity.

 So at inference time, we resolve the player ID from a predicted team and role. And second, we mask the role input.

 So this encourages the model to learn, um, player-specific behavior patterns beyond fixed position. Third, um, we add a key auxiliary value head, and at each outcome talk to, the head determines whether a new team will be will score or concede, within a 50 seconds.

 And this architecture allows the model to calculate, uh, each action by using a VAP. VAP is a standardized football metric, yeah.

 So this can be done by generation and evaluation in each event.

 And without constraint, the model can generate a counter football. So we therefore apply two constraints instead.

 The first is reverse model matching, and reverse model matching will be a minimal option if presented. Second, the overlap keeps the player and role ID to assign current goal area, so prediction cannot be put on a counter player.

 And together, these two constraints make our simulation more trustworthy.

 And lastly, our summary of latest step, we use a heavily South Korea heavily for five seasons, both First Division and Second Division, and it includes 2,300 matches and over 6.1 million football weekends, and 2,002 constraint, uh, 202 witness action about episodes.

 And let's examine our predicting performance first. And we as you mentioned, we use LSPM and test suites, and two varietals from Nigerian models, and from the contemporary varietal on the upper side, and SpotGPT leads on the last field.

 And especially on the outcome talk to, it reaches a network score of 0.86, which is far above the best baseline. And we have a continuous horizon of concerns.

 And for the end notation and the time, and the error increases to nearly half above the best baseline. And for the invest time, SpotGPT reaches a large scale of 0.71, and the best baseline are between 0.3 and 0.5.

 And this table evaluates how well our model predicts the goal scoring and goal conceding, the auxiliary value head, and we compare the baseline that serves only this test. And as you can see, SpotGPT has a case that you see for both conceding and for both goal scoring and goal conceding.

 Our model had lower stride score indicating that the most accurate probability is to make overall. Yeah.

 Unlike the specialized baseline, our model can run a generation evaluation within a single model. And through simulating a transfer, we ask whether the model can change the player sensorily when it changes the context.

 So we keep on episode we keep each episode up to the team's first event, then we change the context at small portions like period and minute, period and scoreline. So we let the model regenerate the reverse of the play.

 And as a result, only the second half the model played. More crucial, and it is most conscious of where the score is better.

 And on the other hand, late in the second half, the model takes more, and it is most obviously where the score is really high. So this suggests that SpotGPT can generate context-dependent strategy, uh, context-dependent sequences as a strategy focus.

 And let's examine our, um, how our model learns about the individual player. And so we plot the player embedding in two dimensions.

 And as you can see, over the role-confident mask, the player clusters more clearly, uh, clearly from position. And, and this means the role alone is not enough.

 So we conduct, uh, two we conduct, uh, additional distributor. The procedure distributor test is there, and we create two events for each player from a deconfusion group, and then we test whether one can be true to each other.

 So basically, the top one accuracy is how often the nearest nearest neighbor to the same player. As a result, SpotGPT achieves the highest top one accuracy, retrieval accuracy, and outperforming both statistically embedding and without rule, without rule-based rule matching version.

 So this suggests that SpotGPT can, can capture the player-specific pattern across the season and related context. So each model can represent each style of player consistently.

 This means the model can reason about a player in the field.

 And finally, this is just the full goal of our research. Can we predict how a player performs after a transfer inside the team in an evaluator group?

 To answer the question, we take 1,000 players from team lead to a transfer to a training and advisor system, and, and we calculate their post-transfer value in two ways. A 9 best note carries over their inserted VAP or just keep their play minute, and our method simulates the player with SpotGPT answer.

 So we compare both errors. We compare both estimates against roughs, which is what they really did in 2025 season.

 So there comes two errors. We plot the two errors between each other.

 On the left, you can see, uh, the diagonal line. The error point below the diagonal line is the player whose simulation is closer to the truth.

 So basically, 26 or 40 players are closer to the truth and below the line. And on average, our error is 1.25 against 1.84 for 9 estimates.

 And on the right. And you can see the plot.

 And this is by the, uh, spec. So you can see the Jensen key from the upper side, and it is a clear example of what our model because he moved from some team to FC Seoul and a quick FC Seoul transfer schedule because he was too slow and old.

 But indeed, in real life, he gets a 0.663, a 11.003, 07 VAP, and the 9 estimates predict him at 7.0. And our model predicted 11.663.

 So this means that 9 estimates really knows how well to fit into the real system. And overall, our model predicts more accurately than 9 displays.

 And to conclude, SpotGPT, and SpotGPT can predict next event very well and generate sequence by context dependent, and can value an action using a VAP method. So, uh, by combining these three capabilities, our model can enable us to evaluate how am I, how a player might perform as he was moving the team.

 So our next step is to diffuse the tracking data with the SpotGPT method, and that's all. Thank you and forward to.

 So standing at the Maradona stadium, I'm sure we have a lot of questions from folks. So yeah.

### Speaker 2

 Yeah. Thank you. Uh, very interesting.

 Um, what do you think which information drives the better performance of the simulation compared to the naive support? Because, for example, your example receipts that you also showed very much better performance at team club, right, than previously.

 So what do you think, how, or what information does the model utilize to predict correctly that he was improving after the game? It's like the team quality that's implicitly more important to the, uh, prediction of anything, I think.

### Speaker 3

 I think player quality is, um, how to react to different contexts. So basically, in a player of our model, learn naturally while training. So, so, um, a player can learn a different quality whether, yeah, whether different situation, when, when different situation.

 So I think it is basically kind of the, to be better performance than the 9 experience.

### Speaker 2

 So basically, that you see in different contexts than before, and that varies differently at sports level, right?

### Speaker 3

 Yes. And varies context. Yes.

### Speaker 2

 Okay. Okay. Well, thank you very much, uh, for your paper.

 Uh, little que, little question about, uh, your data and events. I understand you use, uh, events from, uh, your Korean, Korean league, yes?

### Speaker 3

 Yes.

### Speaker 2

 And this is 40 events. You need to estimate the next token, yes? How, how much events you use in your data?

### Speaker 3

 Ah, yes. And we almost depend as, as a 6.1 million events. For our time season, we're clearly.

### Speaker 2

 Yeah. I mean, it's a pool, but, uh, it's a set, yeah. It's like pass, ball, time.

### Speaker 3

 Ah, yeah, yeah, yeah. And as I remember, I, I almost used 20, 20 to 25 events.

### Speaker 2

 20 to 25 events.

### Speaker 3

 Yes.

### Speaker 2

 It's, uh, it's a nice question. Uh, how we can develop this system to another leagues. So I mean that, that, that you have some methods how you can take this, uh, data for your Korean leagues, but another leagues, Brazilian leagues, Russian leagues, we have some another type of events and the data.

 How we can develop this out GPT for another data. Is it possible?

### Speaker 3

 I think we want to expand our data coverage in, I think, only event data is not enough. So we need to combine some separate data and because together, all the 20 player trajectory are needed. So yeah, that, that's quite challenging because the tempo and everything is different from different leagues.

 Um, yeah.

### Speaker 2

 So inventory, you need tracking, you think, yes?

### Speaker 3

 Yes.

### Speaker 2

 Very good.

### Speaker 3

 Thank you.

### Speaker 2

 Uh, okay. Please, last question. Um, so do you use the player position as one of the features in the context encoding side?

 So when you create the player embeddings, the player position is already being used as one of the features. So naturally, players from similar positions.

 From the same position would be closer. But how well does your player embeddings, uh, learn how to differentiate between players from the same position?

 You know?

### Speaker 3

 Yes. And actually, the role-confident mask is being improved. So the, the model actually can not be provided to be from the same context.

 As you can see, the context, there is a lineup, and the lineup has learned there's a role of player. So in some respect, the role, the role information can be, uh, can be improved from the same context.

### Speaker 2

 Okay. Okay. Thank you, everyone.

 Uh, so let's thank the speaker.
