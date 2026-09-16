### Speaker 1

My name is `<speaker>`. I work at Salandra, and today I will tell you about what Wispr Flow is, and what is a codex dictation, and what we call codex in English. So Salandra is a large collection store across Europe, and traditionally we originally collect fashion items from the catalog used in Salandra.

 So you see a selection of various clothing in different categories, and even then you see some data and you can do some invention adjustment. But at some point, recently, we had a pilot of a new project where users could see images generated from other users, from creators.

 And that was a big challenge for us because that's a completely new modality. We don't have any leaks, we don't have any interactions, so it's a new setting.

 But we still need to work with some of our customers. So what we decided to do is we leveraged existing data from the fashion store, and we used a fine-tuned leak model to embed both videos and fashion store products into the same space.

 So now we can represent both videos and features within the same leak space. So for videos, we sampled frames across the region, we embed them in the modified leak model, and we average them.

 And for customers, those are Salandra customers, so they come into the new experience from the fashion store. And in the fashion store, they already interacted with the items, they clicked them, they asked them to try it, they purchased them.

 So we can create those historical interactions, we can create pictures of those items customers interacted with, and we can use exponential-to-eventual average of new embeddings of those items. So here's the interaction image in a nutshell.

 And the part of the show here really is the video folder, which we fine-tune on our own fashion-related datasets.

 We also experimented with innovation products such as Revit 2.5, and we found out that embeddings from Revit, they are great for taxonomy, for tags, for classification tasks, but they lose innovation when you try to do AML on them. They don't present any generated structure which we can work with.

 So for this specific task, we recommend the decision to use a video folder. In the end, inference is just the doctor of user and video embeddings.

 And we can do vector search very quickly using Elasticsearch. So for a single image, we can do a real time inference for seconds, and that allowed us to create sequences in the exploring module.

 For the innovation, we asked this from the video computer premise and for videos we have not yet explored. So we talked about how to explore for new customers, but that's the power of this platform.

 Right, so we didn't have enough ground truth data to apply innovation, so we decided to use a level of judge, which judge how quick and sensible inputs on a scale from normal to invasive judge. We also measured several similarity metrics using our internal item embeddings, and compared to the baseline, at the moment we observed significant uplifts in both similarity metrics and in LLM as a judge ratings.

 Then we went to an IDS with this, and results were great. Most importantly, we have plus 80% on video style rate and plus 50% on video completion rate.

 And we also observed significant measurement utilization. So while we observed increase of video watching in video premise, fashion store remained completely unaffected.

 We received exactly the same output of high innovation statement. So in the end, we managed to create this framework which allowed us to transfer existing data from our main premise to a completely new pilot premise.

 It supports zero-shot inference, it has an inherent user understanding, it is cross-model, and by definition of it, it is not susceptible to product bias control while remaining fast in use. Thank you for your attention.

 Please leave a video of the presentation. Also, you can find references to see our interactive panel.

 Thank you, `<speaker>`.

 Any questions?

### Speaker 2

 So how do we select the video frames? Is there some resolution skipped in front of this architecture, or do you randomly select these video frames?

### Speaker 1

 So in this work, it's selected randomly for me. So just every 10 frames, every 10 frames, right? But we also want to have more slide selection.

 For example, one idea was to put in some frames where you do not contain any fashion name, but some of them do contain it. For example, it shows fashion names and brands, right?

 So we can easily select from those frames and use them. And I think that would be interesting to us.

### Speaker 2

 For the small group of users, what's the length of the video?

### Speaker 1

 Our videos are usually 2 to 4 minutes per round, and the number of users except for the fashion store, we're talking about 10 to 15 minutes per instance.

### Speaker 2

 Other questions? Okay. Thank you.

 We can.
