### Speaker 1

Uh, good morning, everyone. My already English is a little poor, so I need to look at my speech drum. Okay, let me— I'm `<speaker>` from the University of Science and Technology of China.

 Today I will present Relief 100K, a real-world dataset with over 100,000 battery sales, together with a comprehensive benchmark and a lightweight model for retired battery facility estimation.

 This talk has 5 parts: background and motivation. The Relief 100K dataset, our benchmark framework, the KPCLR model, and finally the mean results and future directions.

 Let's start with motivation. Retired batteries still have substantial usable capacity, so second-life applications are promising.

 But before reuse, we need to know their remaining capacity accurately. Global electric vehicle sales exceeded 70 million in 2024, and the number of retired batteries will continue to grow.

 Many retired batteries can still support applications such as low-speed vehicles and energy storage. Therefore, accurate capacity estimation is essential for safe reuse, fair pricing, and avoiding resource waste.

 However, three major challenges remain. First, existing public datasets are usually small, so they cannot capture diverse agent patterns.

 Second, different studies use different datasets and protocols, making fair comparison difficult. Third, high accuracy often comes with a large model, which is inconvenient for BMS and age deployment.

 To address the first challenge, we built Relief 100K. Our first major contribution: it contains 100,000 battery cells, covering 8 nominal capacities from 15.5 to 105 Ah.

 The scale is much larger than existing open datasets. Battery Life, for example, contains 990 cells, while Relief 100K contains over 106,000.

 Our design is also different: each cell contributes one complete charge-discharge cycle. This emphasizes inter-battery variability across real-world conditions, rather than long-term degradation within a single cell.

 The dataset also covers a wide range of health states. The 67Ah, for example, contains 25,000 retired cells with SOH below 80%, while the 105Ah group includes 6,850 cells above 95% SOH.

 The charging curves also show clear shape differences between low and high SOH batteries. These differences provide the basis for capacity estimation.

 Now, how is the true efficiency obtained? The battery is charged in constant current and constant voltage mode, then rested and discharged at constant current.

 The discharge capacity gives the FCC. Our key idea is charge-to-estimate.

 We use only the voltage and current from the charging phase to predict FCC. So full discharge is not required during estimation.

 Next, we established a unified benchmark and evaluated 11 time-series models under the same experimental settings. The benchmark includes traditional models such as MLP-LSTM, PCN, and CNN, as well as recent architectures such as Time Snags, High Transformer, Bivinear, HTST, SparseTSF, and Time Mixer.

 We use the same pre-processing and data splits for all models, and all charging curves are downsampled to 512 points. Our main method is KPCLR, a lightweight capacity estimation model.

 Its key idea is to use contrastive learning to learn useful battery health representations before regression.

 KPCLR has 2 stages. First, a lightweight 1PCNN includes the charging curves, and contrastive learning pulls batteries with similar SOH closer in feature space.

 Second, a 3-layer MLP predicts capacity, while the encoder and regression head are fine-tuned together. The complete model has only 1.68 million parameters, about 1/11 of Time Snags.

 Now let's look at the results. KPCLR achieves the lowest average MAPE, 1.83%, across all 8 capacity groups.

 Time Snags follows at 1.91%. Interestingly, HTST reaches 4.73%.

 This suggests that models designed for general time-series forecasting do not necessarily transfer directly to battery capacity estimation.

 The accuracy-size comparation is especially important. KPCLR achieves 1.83% MAPE with only 1.68 million parameters.

 Time Snags uses about 19 million parameters, roughly 11 times more. This shows that contrastive pre-training can help a compact model learn highly effective repetitions.

 The ablation studies further explain why KPCLR works. CNN is the best encoder, achieving 1.82% MAPE.

 More importantly, removing contrastive pre-training increases MAPE to 4.38%, more than doubling the error. So the main performance, again, comes from learning meaningful health representations before regression.

 To conclude, we make 3 main contributions. First, Relief 100K provides over 100,000 cells across 8 capacities.

 Second, we established a unified benchmark with 11 models. Third, KPCLR achieves the lowest average MAPE and only 1.68 million parameters, offering a strong balance between accuracy and efficiency.

 There are several promising directions ahead. We plan to collect multiple cycles per cell to model temporal degradation more deeply.

 We also want to explore future and future estimation for new battery types, as well as transfer learning across different battery chemistries. The dataset and code are publicly available on GitHub.

 That's all from me. Thank you very much for your attention.
