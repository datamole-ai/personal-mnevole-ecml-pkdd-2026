Conference talk on benchmarking real-time monitors for safety-critical vision systems, arguing that current accept/reject handling of correctly-predicted covariate-shift samples distorts monitor selection and should instead be ignored in benchmark scoring.

### Framing & Sample Taxonomy
- Real-time monitors decide whether to accept or reject a model's prediction; benchmarks needed to compare techniques for safety.
- Five sample types in vision datasets: in-distribution, OOD (new classes), and covariate shift (same classes, shifted features).
- Existing frameworks (e.g. full-spectrum OOD on VO2) map sample types inconsistently, especially around covariate shift.

### Handling Correctly-Predicted Covariate Samples
- Three options: reject, accept, or ignore correctly-predicted covariate-shift samples in benchmark scoring.
- Small vision experiment: forcing reject pulls threshold left (drops valid ID); forcing accept pushes right (lets unsafe through).
    - Neither extreme preserves safe rejection of dangerous samples
- Larger-scale study: accept vs reject choice changes which monitoring technique ranks best (e.g. shifts on CIFAR, VO2).

### Takeaway
- Current benchmarks distort optimal thresholds; proposal is to ignore correctly-predicted covariate samples in scoring.