### Speaker 1

Hello everyone, my name is Roman Yanis, I'm from Spirit DNS. It's a small company, a small startup-like, it's well connected with the Spirit State University, and so we usually make a lot of research tasks. And today I will speak about large language models, but not very large.

### Speaker 2

 For Russia. I don't understand why Russians from Russia are allowed to be here. Sorry.

### Speaker 1

 Sorry, I don't understand your opinion. This is research. You're allowed to be here.

 This is no politics, okay?

### Speaker 2

 But researchers create prompts that kill people in the internet.

### Speaker 1

 Yes.

### Speaker 2

 This company makes prompts.

### Speaker 1

 Yes, and this is—

### Speaker 2

 This is what your company produces to be—

### Speaker 1

 No, that's what—

### Speaker 3

 It's using these prompts to the CEOs, to the conference CEOs, but I would like to allow the presenter, because the presenter, right or wrongly, it might have been wrong, but the presenter did get permission to present, so we must serve his friend. And this is something which I would greatly appreciate if you bring forward to the community meeting. Okay, so we are done with this presentation.

 Of course, feel free to leave, but don't blame the presenter because the paper was accepted. It might be that it was the prompt that it was accepted, but it has been accepted.

### Speaker 1

 Thank you. And to be clear, I'm telling you now that I'm standing about large language models in the context of that practical task, using them as generators in the review of language generation setup of the CPU for large language. So, first of all, we had a practical task with some constraints.

 First of all, documents cannot leave the device. Secondly, we require—well, we use them for GPU, because not every device, for example, laptops, has it.

 And to constrain it more, we wanted some minimum requirements, like 16 gigabytes of the RAM. And my research question that we studied is about how much quality we can boost when a generator in the product setup shrinks to 1 to 8 unit parameters, and specifically on the Russian language output.

 And the secondary question is which configuration can give us the best practical quality latency tradeoff.

 I need to point that we—I already said that we used models as generators, and to measure them equally in this setup, we frozen the first part of the review of language generation, called the retrieval, when we—when in the task the system needs to find relevant context. So we prepared relevant context and queries, and used models as a generation of generators in this setup.

 And we collected a benchmark consisting of the 500 samples on Russian language. We choose 4 open-source datasets and sampled by 100 examples from them.

 And also, we had one proprietary dataset for the task we needed to do, and it was lecture notes from a lot of IT conferences, and they were happening for years and years. And we had people who handily drafted questions for these datasets.

 And also, we sampled 100 examples from this source. You can see that tasks are different.

 And for the open-source datasets, we had a lot of factual questions, while on the corporate datasets, there are more prompts. And first of all, generation is a creative task, and to measure and develop, we decided to use a learning judge approach.

 And firstly, we decided to select the best judges that can fit in our task. For that, we collected another dataset.

 Based on, we mixed some documents and questions. So we had positive samples and some negative samples where context may be from the dataset itself, or even from another dataset that had a positive sample.

 And we measured how well the model finds scores for positive samples, how low it scores for bad samples with as much, and how well the models correlate with each other. We decided to choose 3 judges from the different model families.

 First was GPT-5 only. Second is Qwen 3, 8 billion parameters, and GLM 4.7.

 Then we proceeded to our task. In our task, we had 3 metrics.

 First was correctness. It's a learning judge measures which scores how good answer is compared to relative correctness answer.

 Second is answer relevance. It's about how well our answer addresses a user question.

 And third one is maintenance. It's how grounded the answer is to the provided documents context.

 And also, we benchmarked 17 different models from 1 to 8 billion parameters.

 We used them in one format, and it's GGUF, and it's LlamaCP backend. And I already told you about ground constraints.

 We tested each model on the CPU environment with each constraint. And for the quality, we used 500 samples.

 For the latency, we tested only 15 samples. There are some results for the models.

 It's full results in the paper. Here you can see that GPT-5 mini was appropriate for this line, which we benchmarked with context and without context.

 And the model we chose to use next was a Qwen 3, 4 billion parameters, construction version of it, and the quantization is 500, okay, M. And we chose this model because of the practical quality latency tradeoff.

 I told you about if you look at this picture, you can see that Qwen 3 with 8 billion parameters achieves a little bit higher quality score, but it has a huge time for the generation. Thus, we can trade a bit of quality for the latency.

 And there is comparison with these two Qwens and our GPT-5 mini baseline. You can see that our Qwen 4B is not far behind from the baseline.

 And the point we can continue to study is the effectiveness for the model, because it has more gap.

 And also, to check if the context is helpful and the benchmark itself is fine, we tried to benchmark this line with context and without context, and you can see that it's actually helpful. And also, from some observations, some model variants can switch in the other domain, with other language, from Cyrillic symbols to Latin, or even Chinese.

 It's mostly connected to the older model families, like Llama 2 and Mistral 7B. And also, for older Qwen, it sometimes switches to Chinese.

 Speaking about limitations, first of all, it was a generation-only setup, and the review part and the running part can be studied more. It was in a specific domain of the Russian language, and open-source datasets were the head.

 Also, our judges can be tested by humans more, and we tested different quantization levels and latency on a subset. But we do not report some other metrics like tokens per segment, because—but it can matter, because different quantizations and different model families can provide, like, wider answers, provide more tokens, and these metrics can be also helpful.

 So speaking about the results, actually, we found out that compact models can achieve competitive quality in the tasks. For example, our retrieval of data generation, where the model itself doesn't need to have a wide world knowledge, like very large language models have, but it can actually make well with the provided context.

 And our selected models achieved competitive quality to the baseline, almost as well as a great model. And with them, we can achieve a practical quality latency tradeoff in the systems.

 And the systems can be used in the task which require no data leakage, because, for example, review and image collection is connected to the documents, and not every company wants to send their documents to the cloud providers. And for the future work, we can focus on improving faithfulness, some human validation of the judges, and more of the profiling and other methods.

 So here is a link. We have an older version of the paper as a reprint, our quote, and the data we gathered on the example.

 I'm ready to answer your questions. Thank you.

### Speaker 3

 Since I'm reporting this incident, I would like to ask questions, because I wasn't present for some moments. Are there questions? So this was just for the generation part.

 So what do you now think of how to get the retrieval part to work also with smaller models? So when you transform the documents into reasonable embeddings, could you also do that, just mostly with a container maybe with anything?

### Speaker 1

 Thank you. It's a great question. First of all, to focus on generation, because it requires a large model.

 In the theoretical part, we can use a lot smaller embeddings. And it requires a different type of data.

 I think a lot of benchmark already has tests, like Qwen 5. We don't know benchmark of the embeddings.

 And I think it's interesting to test more like an end-current setup. And I would like to prefer focusing on the well-rounded, condensed dataset with also quantized embeddings, for example, if we need it.

 So you should, I think, always start from the requirements you have for the system in a practical task.

### Speaker 4

 Do you think there's chance that building better models, more compact, is also critical to use the drones, to use less material, and make the drones more accurate?

### Speaker 1

 You mean less. Small models can be more accurate.

### Speaker 4

 Yeah.

### Speaker 1

 I think it depends. We found out that they can achieve the same quality with the provided context. It's known that the more the model is, the more tokens go through there, and they have a wider world knowledge.

 So large language models, first of all, have more generalization on a wide variety of tasks. But for a specific task, you can actually have a specialized model that can be even better for the task if you fine-tune it, for example, and achieve better results for the specific task.

 So yes, I think it can be.

### Speaker 4

 And do you have any way to ensure that your research is not helping the right time?

### Speaker 1

 I think it is more like I think this task is not connected to the whole process. And this research is open-source, so it can be used for everyone.

### Speaker 3

 We have done for this topic. I would like to make it clear that what I'm doing here reflects my assumptions and assessments here. I am also one of the generals here.

 I have not expressed anything in that role, and my personal opinion is not expressed here. This is something from the community meeting.

 Here, we have a presenter. This is not a sentence from the author.

 This is nothing written from the author. For example, I thought the paper has been accepted to help fill some difficult case and applaud.

 It seemed that it is not okay. It is not meant for all the sessions.

 I would like to thank you.
