Igor from Zalando presented a cross-modal recommendation system that reuses fashion-store interaction data to power a new video/creator pilot, showing strong A/B lifts.

### Problem & Approach
- New video/creator pilot had no interaction data (cold-start, new modality)
- Reused fashion-store data via fine-tuned CLIP embedding videos and products into shared space
- Videos: sampled frames, embedded, averaged; users: EWMA over embeddings of items they interacted with

### Modeling Choices & Evaluation
- Tried SigLIP 2.5: good for taxonomy/classification but embeddings lack structure for ANN
    - Chose fine-tuned CLIP; inference = dot product + Elasticsearch vector search
- No ground truth, so used LLM-as-judge plus internal similarity metrics vs baseline

### Results
- A/B test: +80% video play rate, +50% video completion rate
- Fashion store engagement unaffected; framework is zero-shot, cross-modal, popularity-bias resistant

### Q&A
- Frames currently sampled every ~10 frames randomly; smarter selection (e.g. brand-containing frames) is a future idea
- Videos 2-4 minutes; user history spans ~10-15 interactions