`<speaker>` presented a tensor decomposition + foundation model framework for forecasting multivariate time series (crypto, EPS, retail sales, rideshare), outperforming standard TimeFM and CP baselines, especially on sparse data.

### Problem & Motivation
- Forecasting multi-entity, multi-feature time series as a tensor (e.g. cryptocurrencies × features × time)
- Foundation models like TimeFM treat variables independently, losing cross-correlation; tensor CPD has limited rank/parameters

### Proposed Architecture
- Encoder/decoder tensor decomposition into entity, variable, and time latent factors
- Frozen/zero-shot TimeFM forecasts latent temporal columns, then reconstructs future tensor
    - Eliminates look-ahead bias and memorization since latent factors are data-reconstructed
- Stochastic gradient descent training handles sparse/masked observations

### Experiments & Results
- Tested on EPS earnings (160 quarters), retail sales, NYC rideshare (400-500 months, 150 locations, 15 features)
- EPS: 82% R-squared vs baselines; first to beat analyst consensus (~86%) via simple ensembling
- Stress tests 10-90% data: baselines degrade, proposed method holds R-squared; loses edge at 100% dense, low-correlation data