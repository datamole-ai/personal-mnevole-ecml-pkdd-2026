This is Nadine Foster from McGuire University in Australia, and today I'm presenting, uh, the game of Flynt. Well, a larger push for lawbooks has been increasingly deployed in adversarial settings that include penetration testing, automated negotiation, and fraud prevention. And the power of these models really lies in their capability to evolve and adapt, because opponents are not static, and a strategy that's working today might be countered tomorrow, which requires constant and consistent adaptation, and which a training cycle cannot provide efficiently.

 Um, in this work we're studying the capability of large language models to learn from structured feedback without any training, and we base our study on, as can, um, attacks—uh, use cases—where malicious actors always adapt and evolve their strategies. Um, well, at scale attacks really pose very significant pressure on financial and, uh, systems and individuals.

 The Federal Trade Commission has reported $12 billion losses due to fraud, and, uh, Spontan remains the main buffer for that. Um, foreign defenses really are mostly reactive and attack-era, like, for example, blocking and blacklisting.

 Attacker knows how to evade those defenses in order to still reach the victims. Um, there's a different way to counter attacks than scam attacks, which is basically scam baiting, and it has a completely different posture because it's proactive and actually is able to defend scammy resources.

 Automated approaches do exist; nevertheless, there are used static responses and static heuristics, and therefore their efficiency is so limited. Um, a good scam baiting really needs to address three challenges: the conflicting objectives of prolonging the conversation while remaining credible; identifying effective strategies and applying them; and constantly adapting and learning from previous outcomes to evolve and improve strategies.

 Uh, in order to address these challenges, we use a game-theoretic approach in order to model this adversarial dialogue setting where the opponent is always evolving. The two players have conflicting objectives, opposing objectives, where the scammer aims to extract financial PII, or credit card information, or information, and the baiter aims to extend the conversation as much as possible in order to depend on the scammy resources.

 Um, each of them is assigned a set of strategies that we retrieved from documented scam approaches and adversarial research. Um, the game is zero-sum in the sense that the game of the one is the exact loss of the other, and each of them actually did not, um, commit to one strategy.

 They maintained a distribution over their strategies, and they select the appealing strategy given history of the game and current game setting. Um, our contribution—we actually got four contributions on this work.

 The first one is formulating an evaluation framework to assess—a game-theoretic evaluation framework to assess—a larger model capability of learning. Um, we proved that larger model models are not able to learn and adapt from structured feedback without fine-tuning or training cycles.

 We identified effective basic strategies. Finally, last but not least, we released a dataset of 300 scam baiting conversations, along with strategies and payoffs and utility—all of the effectiveness of those strategies.

 And this is an overview of our framework. Um, we actually have two players.

 Each player is based on two large language model agents. The first agent is the strategy selector, actually, and picks one of the strategies.

 One of the strategies is based on the history of the current game and previous games, and this history is in form of a pair: strategy and payoff, strategy and utility. Um, and then the other agent is the one that translates the response—the strategy—into a contextually appropriate response.

 Each turn runs as follows: first, the scammer initiates the conversation, which is what we call the real-life setting, picks a strategy based on the history, and then hands it to the response-generator agent, which then formulates a response. Um, and then comes the turn of the baiter; it takes as input also the history, um, in form of the pair of strategy and payoff, as well as the strategy selected by the scammer, in order to be able to counter that strategy with a proper response.

 And then, um, after selecting the strategy, it again hands the strategy to the response-generator agent. Finally, the two responses are sent to a third agent, which is the dialogue-analyzing agent.

 It actually assesses both responses and retrieves the information needed to calculate the payoff or the utility for that turn, such as financial PII retrieve, other PII retrieve, and so on and so forth.

 Um, this is the utility function, and it's actually calculated after each turn. Um, it's a zero-sum game, so the value of the one being the utility of the scammer would be negative of the utility of the other player, basically.

 This is the utility function from the point of view of the scammer. It's actually crafted to account for the opposing objectives, or the trade-offs between the objectives of both players.

 So from the point of view of the scammer, the first component is the financial PII. It rewards financial PII retrieval.

 The second component is the other PII. It also rewards other PII retrieval that are not financial, and these are basically what keeps the scammer interested.

 It gives him hope that he's going to get something. Of course, it gets less great than the financial PII.

 It penalizes the time expenditure. And last but not least, it rewards the game termination.

 Uh, and this is the last element: the game termination payoff, and only the attacker is able to terminate the game. There are two scenarios for that.

 The one is within the conversation that they realize that the conversation is not rewarding. They're not getting enough PII, and they've been penalized for the time, so they decide to disengage by assessing how the utility is progressing.

 Um, and the other termination possibility is where they retrieve the full PII, full financial PII, and they're rewarded a higher value for that. Um, this identity function is calibrated in order to induce strategies or practices that mimic the documented scam behavior.

 For instance, the utility for the time penalty is a dealer equation to create, like, a mounting pressure on the scammer to either terminate the game or, like, retrieve more PII. The wait for the termination is less for early or premature disengagement and more for retrieval of financial PII to give the scammer the, like, the challenge and the want to apply more pressure on the victim and to retrieve the full PII.

 Um, in order to assess the learning and whether the agent has been positively progressing, we calculate the benchmark representing the optimum play that's formerly called the Nash equilibrium. And this is the distribution of strategies that, like, would end up in the best outcomes for both players, and the distribution would get a better outcome for any other player.

 And we show that the state of the art play using linear programming, where the scammer tries to maximize the minimum payoff and the baiter tries to minimize the maximum loss, in order to calculate the optimum distribution of strategies for both players. That we use then to compare the final distribution of strategies that the players achieve and see how close or far it is from the optimum gameplay.

 Oh, one minute. Oh my God.

 Okay. To evaluate our work, we simulated 300 dialogs across three large language model agents, and we have a three-fold evaluation.

 We assessed dealer count and stats, and we also assessed the learning dynamics. Last but not least, we compared our adaptive strategy selection with non-adaptive strategy selection, which is a performing vector.

 This is the sum stats for the outcomes of the conversation. We've got deep—so we used three large language models: DeepSeek, GPT-4, and Mixtral.

 DeepSeek is outperforming other two models with average turn 42, which is around 20 minutes of conversation daily. 41% can win. And by looking at the parameters, we see that the worst one that's achieved is the Mixtral, which is the largest model, which really gives us a hint that adaptation is not depending on the size but rather on the architecture of the model.

 We also assessed the optimum gameplay—I'm trying to finish this—and we identified the best strategy effective for baiting. This is—okay.

 Okay, the conclusion. This is the learning dynamics.

 We can see that they converged to Nash equilibrium, and in conclusion, we actually proved that large language models can adapt and evolve using structured feedback without training.

 Thank you very much.

 Questions.

 Yeah. So—sorry. Which model was the third one?

 The model that's outperforming is the DeepSeek.

 Okay.

 And so related to that question, Marek, basically you just put GPT-4, GPT-5, which regions?

 Because now there are 10 regions of performance for Nash equilibrium. So you tested it with 4, but now there is 5, 5.6, 6, and so on, so you cannot see that on the slides.

 Yeah. So no. We, of course, large language models are part, like, that you adapt very quickly and they've got better models.

 But we just tested capabilities, and we—of course it can change, but we know that it's not depending so much on the size of the model but rather on the architecture of the model.

 Okay. What regions of the slide do you have a sense of the—

 Which one?

 The last one.

 The big one, the convergence.

 This is the convergence one. Yes. So for this we used two parameters.

 I think I've got—I'm still in the time. All right.

 So we've got two parameters: the cosine similarity, and it really checks whether models were able to identify the favorite or the better strategies as the Nash equilibrium. And we've got also the diversity.

 The Jensen-Chang diversity, which actually measures whether the distribution is matching the distribution of the Nash equilibrium. And this is really, like, checking whether the models were figured out to, like, a good percentage of frequencies to apply the different strategies.

 And those together, they tell us whether they identify the good strategy, the optimum strategy, or whether they know how often they need to use them. See that all models are doing convergence.

 So in order to test that, we divided the dataset into chronological batches and see, with more training, how often they—how much they are evolving and adapting. And we're seeing that most of them are converging towards the Nash equilibrium.

 And of course, the diversity is getting less and less across batches. Of course, with a few changes in the end, because some models still prefer to explore rather than premature locking percentages.

 But in general, the diversity is getting smaller, and the convergence is getting better. Yeah.

 Thank you very much. And thank you also for asking exactly these questions.

 Thank you so much.