### Speaker 1

Good morning, everyone. I'm `<speaker>`, and I'll just jump in quickly. Today I'm looking at a small work on signing and leveraging medical reality to arts and literary appraisal in manifested language.

 Our culture of concentrated observation says that art recommended doesn't simply inherit the popularity of eventual items; it inherits the ones of unlearning. Popularity has grown through thematic relationships and amplified the cultural obtaining attitude.

 He'll address this method of vapor plus EST, which is the semi-schematic exposure and reference the training system.

 So let me pair with the feminine form of popularity bias. The figure shows that the variation distribution of the cities and choice insight, which write the title, can be divided into 5 groups according to historic popularity.

 We have G1 as the most popular clinic set. The blue box represents the test distribution, while the green box represents the output after the device component.

 In both insights, SFT strongly increases the share of G1. In the most strict case, the top 20% of adults received about 16% of the recommendations.

 So commission of popularity bias earlies survives, and it can even be amplified when we fine-tune it and pair them for recommendation.

 However, item frequency on the balance is where the impact affects. `<speaker>` asks where the popularity after only the popular item itself.

 To test this, we first remove the top 30% most popular items. With that group of all remaining items by the NAMA embedding distance to the popular set, G1 now provides the earliest semantic labels, while later groups have progressively less label and similarity.

 Even after the alleged popular items are highly securely, SFT still assigns the above-rated size order to G1. This pattern appears on both insights.

 We call this phenomenon semantic popularity bias. Exposure is amplified not only for popular items, but also for items noted and used in the model semantic space.

 This reveals a limitation in conventional item-wise bias. Traditionally, Wispr IPS methods usually treat every item as independent.

 An item's personality is imagined meaningfully only for its very item. But an LM operates in a conventional semantic space.

 A popular item is surrounded by many related items, and exposure can diffuse along this semantic age. As a result, it becomes only 3% regarding semantic popularity.

 Meanwhile, the PLM can assign an inappropriate space. The key requirement is therefore to model item-to-item semantic inference before applying FDS.

 EST models popularity attribution is correctly during SFT. EST combines three statements: first, we construct a multi-view semantic graph, combining key semantic tests and collaborative information; second, we propagate the observed item popularity over the graph using a baseline style process.

 This gives a semantic agreement for us, which reflects both an item's own popularity and the influence of its neighbors; third, we use the invoice of this semantic process in a self-normalized weighted SFT objective. In short, the pipeline commends raw popularity into semantic popularity, and then commends semantic popularity into stable training weights.

 I will now explain these three compliance in model detail. This semantic graph combines three components to reduce: the first is key semantics, where a NAMA item embeddings capture contextual meaning; the second is surface-level textual information.

 TFIDF features a threaded textual overlap with titles and metadata; the third is global field behavior. Subtract item embeddings for similarity in user interaction patterns, which we compute an item-to-item distance method to normalize its scale.

 With that, some of the scale normalize distance to obtain the field distance shown below. Finally, each item conveys it to its top-kind nearest neighbors, which larger vector widths assign it to closer items.

 This solution avoids relying on a single, potentially noisy combination of semantic similarity. With this graph, we can explain how popularity spreads.

 We model semantic popularity progression using personal interest in the updated equation. Observe the popularity X as an item-inear preference, while the objective symmetric represents influence from semantic neighbors.

 Lambda controls the balance between these two sources. Repeating the update produces a standard rate distribution to boost up each region interact as a semantical proportionality and useful analogy social media information.

 Each item represents part of its alleged popularity, but also absorbs influence from real-world item and reveals its reach. This graph smooths into a small amount of bias, but for sparse high items, it subsequently reduces bias and provides more reliable biases for FDS.

 The final step is to turn this problem proposition into a stable learning objective. We assign training examples and FDS with items with high semantical frequency receive smaller weights, while under-exposed items receive large weights.

 Directly reverse weighting however can create extremely large gradients for real items. EST therefore excuses double label smoothing reduced over-confidence in the target group, and as an FDS self-normalized weights within each need batch.

 In this way, EST targets the semantic high result, allowing a few sparse scale examples to dominate optimization.

 We evaluate this method under a composite protection. We use three Epsilon code for cities, kingdom, and twice, which differentiates as per diversity labels.

 Every best file is split into training, validation, and testing using an 8:1:1 ratio. We prefer full-rating evaluation rather than simple re-rating.

 Importantly, all semantic evaluation across cultural items is proctored from training only, so future information cannot leak into the model. We evaluate both the recommendation quality and exposure behavior using accuracy, popularity, and diversity metrics.

 The main comparison shows that biasing doesn't require satisfactory accuracy. Figure 2 presents the overall comparison.

 The best results are matched correctly to the original paper table. EST actually strongest inference and assertion on all three insights relating to the best company baseline.

 The reported biases are 15.38% on cities, 16% on kingdom, and 6% on twice. The improvement is therefore consistent across domains rather than driven by a single insight.

 At the same time, EST remains competitive for all best exposure and diversity measures. This is the key comparative results.

 Modeling semantic proportionality draws the accuracy biasing balance instead of meaning training one object for the other.

 Here, items are grouped according to the estimated semantic proportionality, with G1 representing the most exposed semantic tag. Compared with the test distribution, standard SFT pushes too much recommendation mass into G1.

 After applying EST, the G1 share increases, and exposure is redistributed toward G2 through G5. The pattern is reversible on both cities and twice.

 This result is important because it verifies the mechanism introduced earlier. EST doesn't only suppose historically popular item edits; it corrects the broader semantic concentration created by the LM.

 In the validation study, we remove one semantic width at a time, removing the terrain view which is conflicting with meaning. We remove TFIDF loss with exact electoral evidence, and we remove subtract which has a connection to real user behavior.

 Every removal that is. Okay.

 This proves that the previous chart configuration rather than redacted.

 The sensitive growth shows an embedded new pattern. If Lambda over the neighborhood size changes, most semantic influence is unpredictable.

 Okay. Let me conclude with three main messages.

 EST graphs the mechanism, not just the symptom. First, popularity biasing and recommendation progress through semantic labels.

 Second, EST models this mechanism using a multi-view semantic graph. Third, the experience shows semantic improvements in recommendation quality and exposure balance.

 Thank you very much.

### Speaker 2

 Thank you, China. And do we have any questions? We have time for one or two questions.

 I can start. Do you see the applicability of this also in different domains like engineering, or like NAMA engineering, aerospace engineering?

### Speaker 3

 So we're using Epsilon test side and not using it in a real-use system. One is to create a multi-view semantic graph. It's very.
