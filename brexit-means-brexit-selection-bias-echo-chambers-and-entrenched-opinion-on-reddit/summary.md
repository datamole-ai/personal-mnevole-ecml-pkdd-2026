Conference talk on the "Brexit means Brexit" study of Reddit stance dynamics: engagement with opposing camps does not shift opinions, and survivorship bias plus echo chambers explain most observed polarization.

### Study Setup
- Research question: does engaging opposing camps on Reddit change political opinion?
- Dataset: ~871K Brexit submissions, Nov 2015–Feb 2021, split into 27 political periods
- 5,000+ posts crowd-annotated (pro/anti/neutral) via Amazon MTurk, inter-annotator agreement 0.8
    - Filtered malicious workers using majority-agreement proportion
    - Dropped posts lacking 5-annotator agreement

### Modeling Stance
- Best classifier BERT_ready (in-domain pretraining + fine-tune) reached F1 0.55
- Introduced continuous user polarity measure in [-1, +1] to avoid naive 83% neutral
- Bigger models (graph attention, BiLSTM, stance-closure) gave no lift: signal ceiling is social, not textual

### Key Findings
- Survivorship bias dominates: 70% post in only one period, <1% span 3 consecutive periods
- Returners more often polarized but less extreme in magnitude; extremes get pushed out
- ~40% of interactions cross camps, yet strongest predictor of next-period stance is current stance