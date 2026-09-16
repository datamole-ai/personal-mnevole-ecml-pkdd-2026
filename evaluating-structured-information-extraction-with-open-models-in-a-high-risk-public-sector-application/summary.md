Talk on using open-weight LLMs and VLMs to extract transcript-of-records data from data science program applications under EU AI Act constraints, showing VLMs outperform OCR+LLM pipelines.

### Motivation & Constraints
- Data science program at Manhattan University gets ~550 applications for 20 seats, manually reviewed
- EU AI Act classifies public-sector application review as high-risk; data cannot be sent externally
- Work led by `<speaker>` (absent); little training data, only open-weight models viable

### Approach & Results
- Task: extract tabular transcript of records (subject, grade, credits) from long heterogeneous PDFs
- Compared OCR+LLM pipelines vs. vision-language models on exact-match precision/recall/F1
- Best OCR+LLM: MinerU-like library + Qwen; VLMs beat OCR+LLM overall in zero-shot
- Higher parameter count did not consistently improve results
    - OCR often loses table structure, hurting downstream LLM accuracy

### Takeaways
- Call to action: scientists should collect, annotate, curate and share domain data for public-sector AI
- Everything open-sourced except the data (anonymization destroys signal)