### Speaker 1

Can you hear me? Okay. So, the doc like interface for document layout analysis and interaction.

 This is the architecture of the system, and it performs document segmentation through Claude, as you can see on the left, and it also works with a lot of documents. And the tool integrates post-documentology to perform checks among the three elements.

 And then it's present also an LLM, which purpose is twofold, because it performs a query classification of the user query to trim the context. And then it is used also to interact with the document's content and structure.

 This is a screen capture of the system, and as you can see in the left part, it performs the document segmentation, and also the user can interact with the document holding the mouse over the items that are retrieved by Claude. And it shows also the metadata that is provided with geometric data, for example, the name of an author is shown among the metadata.

 On the left, on the right, it's present the LLM module, which performs the context classification, and there are also examples of queries that can be made to the system. So this is the interactive segmentation.

 The error correction. The system also performs an error correction through the interaction with the ontology.

 So the interaction with the ontology is performed evaluating the geometric overlap among elements, which can occur, but it's not always wrong. For example, an author name which overlaps with an author section is an overlap which is allowed, but for example, a footnote with a title is not allowed, so the system finds it and corrects it.

 The system is also multi-page, and also performs in the element section a trimming of the context, which can be avoided by the user. So the multi-passification of the context can be avoided and chosen directly by the user.

 This is an example of an error visualization, because this is integrated in the system, but the system is also provided with a perspective which is overlap annotator, which visualizes only the multiple boxes that are in error. In this example, a footnote and a table, and obviously the footnote is wrong and removed by the system.

 These are other examples of errors, of overlap errors that are found by the system. As you can see in the top, there's a note within a table, and note and table are disjoint in the ontology.

 And in the bottom, there is a table and a lot of table labels, which the segmentation engine misclassifies, and the system is able to find and correct. The ontology used is the document component ontology, which is an ontology by the University of Bologna.

 And correction, the actual correction, is performed by a VLM, which specifically is the Llama VLM. And then the errors are proved.

 What happens after the scenes is this: this is an excerpt of a PDF which is converted to TXML, then converted in key-value pairs, which are human-readable and also element-readable. And these key-value pairs are used as context and trimmed by the context classifier.

 These results are not contained in the present work, but in a broader work that is written in the bottom. And on the top, you can see the segmentation capabilities of the system, which are aligned with the state of the art.

 And in the bottom, there is a little test which we have made to test the capabilities of the system and the performance, the time performance of the system, which has to be considered between success and partial, because they measure the user satisfaction in general. And the duration is high because it's tested on a computer, which we can also see together after this presentation, at 5:00.

 And this was the last slide, but it's not shown, where there was also a QR code. It's not shown.

 Okay, this is it. Thank you.

### Speaker 2

 Okay.

 Any questions?

### Speaker 3

 Yeah, just a few. You said the framework was for other kinds of documents, not only scientific papers?

### Speaker 1

 This framework works just with scholarly documents, because the segmentation engine that is provided works with scientific documents only. We tested it on PubMed, on DENSE article datasets, just datasets for scholarly documents.

### Speaker 2

 Okay. Thank you.

### Speaker 3

 We can move to.
