Laura presented Antenna, a system that uses LLMs to explain latent patterns from tensor decomposition in natural language, with a validation test to check comprehension. No audience questions followed.

### Motivation
- Multi-aspect datasets (e.g. social networks, movie ratings) naturally represented as tensors
- CP decomposition reveals latent patterns, but metadata/labels for interpretation often missing or unreliable

### Antenna System
- Tensor analysis module extracts latent patterns; explainer module uses LLMs to describe them in natural language
- Two explanation modes: task-agnostic (summarization) and task-specific (user-defined, e.g. trend prediction)
- Validation test injects irrelevant authors and asks LLM to identify relevant vs. irrelevant ones

### Demo
- Applied to DBLP dataset with modes for authors, papers, and conferences
    - Outputs decomposition error plus visualized factor matrices