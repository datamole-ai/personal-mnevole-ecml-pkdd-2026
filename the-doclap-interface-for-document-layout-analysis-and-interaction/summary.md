Presentation of DocLap, a document layout analysis and interaction tool for scholarly PDFs, using Claude for segmentation, an ontology for error correction, and an LLM for query classification.

### System Overview
- Architecture: Claude does document segmentation; LLM handles query classification and content/structure interaction
- UI shows segmentation on left with hover metadata (e.g. author name); LLM module on right with example queries
- Multi-page support; context trimming in element section, user can opt out

### Error Correction via Ontology
- Uses Document Component Ontology (University of Bologna); checks geometric overlap between elements
    - Allowed overlaps (author name in author section) vs disallowed (footnote in title)
- Overlap annotator perspective visualizes only boxes in error; correction performed by Llama VLM

### Pipeline & Evaluation
- PDF → TXML → human/element-readable key-value pairs used as trimmed context for classifier
- Segmentation aligned with state of the art; user-satisfaction test between success and partial, high duration
- Framework limited to scholarly documents; tested on PubMed and DENSE article datasets