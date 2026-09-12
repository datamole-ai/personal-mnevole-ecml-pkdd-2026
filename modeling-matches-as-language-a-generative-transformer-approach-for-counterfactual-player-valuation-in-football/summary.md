Conference presentation of SoccerGPT (SpotGPT), a GPT-style transformer that models football matches as event sequences to simulate player transfers, followed by audience Q&A.

### SoccerGPT Approach
- Treats a football match as a language: sequence of tokenized events with context block plus play tokens (10-dim tuples, max 100 events).
- Key tweaks: player IDs in input but not target, role input masked, auxiliary value head predicts score/concede within 50s (VAP metric).
- Two constraints keep counterfactual simulations trustworthy: reverse model matching and locking player/role IDs to current lineup.

### Results
- Outperforms baselines on next-event prediction; outcome token F1 ~0.86; retrieval top-1 accuracy highest with role-mask + player ID setup.
- Transfer simulation on 1,000 players: mean error 1.25 vs 1.84 for naive VAP carry-over; 26/40 example players closer to truth.
- Case: Jensen moved to FC Seoul, real VAP 11.007, naive predicted 7.0, SpotGPT predicted 11.663.

### Q&A
- Better performance attributed to learning player quality as context-dependent reactions, not fixed skill levels.
- Extending to other leagues (Brazilian, Russian) needs tracking data alongside events; event data alone insufficient given tempo differences.
- Player embeddings differentiate within same position because role-mask forces model beyond lineup role info.

### Next Steps
- (<@speaker:1>) Fuse tracking data with the SpotGPT event-based method.