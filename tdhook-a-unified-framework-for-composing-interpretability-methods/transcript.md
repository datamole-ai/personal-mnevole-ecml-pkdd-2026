### Speaker 1

So we use my phone for computing interpretability method. So, uh, a quick motivation: I'll be talking about really interpreting a deep neural network in CI/CD, and how you can, from a high-level perspective, really compose different methods for interacting easily with them. As you might know, the shift in the modern interpretability went from previously single attribution maps to more complex pipelines where you are, like, activating you use them later on to estimate dimensions, and you use them to infer interventions.

 So it's become more of a complex orchestrated pipeline. And so, I'll be—this is why I'm motivated to do it.

 Let me just walk you through the building blocks of TDU and the basics, really. So the idea is to transform your PyTorch module into a TensorRT module in a way that it's easy to interact and add multiple layers of computation in addition to your model.

 And in addition, all the inputs and outputs in different Tensors will be really easy to access in a TensorRT. So this is the main high-level API.

 And depending on the method you need, if you need, like, for example, storing activation, TDU will automatically register PyTorch clips to your model, and it can also be used to compute attributions. Also could be used by your method to, for example, make interventions and then store the outputs.

 So it's really about composing everything in the single API that is high-level, and then it can support a wide variety of different methods. And so, to illustrate that, we have really various methods.

 I'll encourage you to check the library. We have attribution methods, representation methods to manipulate and use the latent spaces.

 We have weight methods to really modify and intervene on the weight. And we have also many more methods to come, to, for example, evaluate the explanations or also the more complex methods.

 And as I mentioned before, a lot of the recent work has shifted from single methods to orchestrated, really, orchestrated different methods. So here is an example that's really Oscillo-GPT, a model that is trained to 8GB of Oscillo.

 And in one of the experiments, they really have this multiple steps where they capture activations, then they have 2 to 5 floors and train the replacement of the activation in order to get the desired output. And then they get the logits and compare the prediction.

 So this is really multiple steps. And in other recently published models, they have, like, this capture activation in order to do later circuits in interpretability, identify contributors, and later on cluster all the circuits together.

 So again, multiple steps. And this is what motivated TDU and the Wordsworth notion.

 So here is the high-level overview of how you can combine, really, the different methods in the library. So the first thing, for example, you might want to store activations.

 So they will be in this TensorRT. Living in the TensorRT, they are easy to access for later applications.

 For example, you might want to do dimension estimation or latent clustering that you will get also as a Tensor. And later on, you might want to reuse activation in order to compute, for example, LFP attributions.

 And this attribution could be used to do relative patching, so patching the model and analyzing the outputs with you. So this is really an example of Wordsworth, but the key idea is that all these artifacts that come from different methods are easily retrievable by all the methods and can create a really combined flow that is easy to use.

 So here is the first notebook on the Oscillo-GPT. So I invite you to dig into the notebook to understand a bit the results.

 These are the crucial factual activations that you get from Oscillo-GPT. And you also have other notebooks to illustrate this kind of Wordsworth notion.

 For example, on the circuit analysis, where you can see the different features, the contribution to an output, and how they cluster together. And so the library also has many more different notebooks to walk you through the library.

 And I just wanted to give you a quick overview of the roadmap for the next few months. So obviously, it will be about stabilizing the library and making it more robust in terms of compatibility between methods, and also user-friendly interfaces, for example, with native protocols.

 While this is supposed to be a method catalog, it's about, like, maybe you want your new method or other methods, like auto interpretability or really explanations. And then I invite you to contribute a little bit later.

 And one of the key points of TDU testing is that it can integrate with other great libraries that exist out there, NNSI, TransformerLens, or Interpretor, or you name it. They do an amazing job, and maybe TDU can be here to combine all of them.

 And finally, I'll be also focusing on deep neural work, so if it's something that interests you, feel free to reach out. So thank you again, and here is the details, and feel free to connect on the email.

 Thank you.

### Speaker 2

 Questions?
