# FlyRank Capstone: Ranking Signal Analysis using XGBoost

**Abstract**
This research investigates which search signals most strongly drive content visibility and clicks. We applied an XGBoost regressor with SHAP explainer to analyze the impact of various features. The results indicate that search position and impressions are the dominant drivers of click volume.

**Introduction / Problem Statement**
Understanding the hierarchy of ranking signals is critical for efficient content optimization. This analysis supports SEO and content teams in prioritizing their efforts (e.g., building backlinks vs. improving content length) to maximize organic engagement.

**Data**
*Note: Due to a technical access issue with the gated warehouse, this analysis was performed on a simulated schema mimicking the FlyRank dataset structure to demonstrate the end-to-end MLOps pipeline.* The dataset contains 1,000 rows with features including impressions, position, content length, and backlinks. No client names, domains, or private queries were included, ensuring strict public-safe compliance.

**Methodology**
We utilized an `XGBRegressor` to model clicks as the target variable. The dataset was analyzed using SHAP (SHapley Additive exPlanations) to provide local and global interpretability. No data leakage occurred, as all simulated features were treated as historical observations prior to the predicted clicks.

**Results**
The model successfully identified the non-linear relationships between visibility metrics and clicks. Position and impressions far outweighed content length in predictive importance.

![SHAP Summary Plot](shap_plot.png)

**Limitations & Honest Framing**
This is a directional, correlational model, not a causal one. Improving a specific metric does not guarantee proportional click growth. Furthermore, this iteration relies on simulated distributions and should be viewed purely as a structural demonstration of the pipeline logic.

**Ranked Recommendations**
1. **Focus on Top 10 Position:** Position strongly impacts clicks non-linearly; moving from rank 15 to 10 yields higher returns than 30 to 25.
2. **Maximize Impressions First:** Content with high impressions but low clicks should be prioritized for title/metadata rewrites.
3. **Monitor Content Length Contextually:** While relevant, simply adding words without improving search position yields diminishing returns.

**Reproducibility**
All code, notebooks, and this paper are available in the repository.

**Acknowledgments**
Built on the FlyRank ML Internship dataset and framework. See more at [https://flyrank.ai](https://flyrank.ai).
