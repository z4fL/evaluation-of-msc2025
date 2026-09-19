# Evaluation of Tournamen MSC 2025 Mobile Legends: Bang Bang

Machine learning research project associated with the scientific article **“Match Outcome Prediction in Draft Pick and In-game Phases of MSC 2025 Mobile Legends using Random Forest and XGBoost.”**.

This repository contains the Jupyter Notebook used during the research process, covering data preprocessing, feature engineering, model training, and evaluation.

## Related Publication

This project is associated with the following scientific article:

> [**Match Outcome Prediction in Draft Pick and In-game Phases of MSC 2025 Mobile Legends using Random Forest and XGBoost**](https://doi.org/10.30871/jaic.v9i6.11658)

The study evaluates match outcome prediction separately between the draft pick and in-game phases using data from the MSC 2025 tournament.

## Research Workflow

The notebook contains the machine learning workflow used in the research:

```text
Data Preparation
      ↓
Data Preprocessing
      ↓
Feature Engineering
      ↓
Model Training
      ↓
Model Evaluation
```

Two prediction phases are evaluated.

### Draft Pick

Draft pick features represent team composition and hero-related characteristics, including hero strength, synergy, damage type, and patch-related factors.

### In-game

In-game features represent match conditions at multiple time-based snapshots, including gold, kills, turrets, turtles, lords, and other objective statistics.

### Evaluation
The models evaluated are:

* Random Forest
* XGBoost

Evaluation includes:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion matrix
* Feature importance
* Per-snapshot evaluation for the in-game phase

## Dataset

The research dataset was collected and prepared specifically for the MSC 2025 analysis.

The data collection process involved multiple sources and methods, including:

* **Liquipedia API** for tournament and draft pick information
* **A third-party MLBB API** for hero-related attributes and ratings
* **MSC 2025 match recordings** for in-game snapshots and manual data extraction
* **Official MLBB patch notes** for patch-related information

The original datasets are **not included in this repository**.

This is intentional. The research data contains information collected from third-party sources and match recordings, and this repository does not redistribute those source datasets.

Examples of the dataset structure, features, and exploratory data are available directly in the notebook.

## Notebook

The repository contains:

```text
Evaluation_MSC_2025.ipynb
```

The notebook contains the research workflow and recorded outputs, covering:

* Dataset overview
* Dataset exploration
* Data preprocessing
* Feature engineering
* Random Forest implementation
* XGBoost implementation
* Model evaluation
* Feature importance
* Per-snapshot in-game evaluation
* Result visualizations

The notebook is provided as a **research artifact** documenting the machine learning workflow and recorded experimental results.

The original datasets required to reproduce the complete experiment are not included in this repository.

## Results

The research evaluates model performance separately between the draft pick and in-game phases.

For the draft pick phase, the models achieved a maximum accuracy of **57%**, with ROC-AUC values of approximately **0.56 for Random Forest** and **0.58 for XGBoost**.

For the in-game phase, the highest recorded accuracy was **88% for Random Forest** and **84% for XGBoost** on the last snapshot. Both models achieved a **ROC-AUC of 0.94** on the same snapshot.

Within the scope of this research, the in-game snapshot features produced higher predictive performance than the draft pick features.

These results are specific to the MSC 2025 dataset and the patch conditions covered by the study. They should not be interpreted as general performance across other tournaments, datasets, or game versions.

## Data Sources & Attribution

The research uses data originating from multiple external sources.

### Liquipedia

Tournament and draft pick information was collected through the Liquipedia API. Draft pick data was manually verified against match recordings during preprocessing because some raw API entries were incomplete or inconsistent with the recorded matches.

### Third-party MLBB API

Hero-related attributes and ratings were obtained through a third-party MLBB API and used as supporting data for draft pick feature engineering.

### MSC 2025 Match Recordings

Official MSC 2025 match recordings were used to verify draft pick information and extract in-game statistics. Screenshots were captured at predefined timestamps, and statistics such as gold, kills, turrets, turtles, lords, and other objectives were manually recorded.

### MLBB Patch Notes

Patch-related information for the training and test data was collected from the official MLBB Discord server, covering patch 1.9.68 and patch 1.9.91. The information was used to identify hero balance changes and patch-specific characteristics.

The original source datasets, API responses, and collected data are **not redistributed** in this repository.

External sources remain subject to their respective terms, licenses, and attribution requirements.

## Limitations

The research dataset is limited to the **MSC 2025 tournament** and the specific patch range covered by the study.

Because hero META, team playstyles, and in-game statistical distributions can change across tournaments and patches, the resulting models are not assumed to generalize directly to other competitive events or future game versions.

The in-game analysis is based on predefined time-based snapshots rather than real-time prediction.

The study uses qualification stage matches as training data and the MSC 2025 main event as test data. The difference in tournament stage and patch conditions may introduce differences in the characteristics of the training and test datasets.

## Disclaimer

**Mobile Legends: Bang Bang, MSC, and related game and tournament properties belong to their respective owners. This project is not affiliated with, endorsed by, or sponsored by Moonton or the MSC tournament organizers.**

No ownership of third-party data, match recordings, game assets, or other external content is claimed by this repository.

## License

The **source code** in this repository (notebook, scripts) is licensed under the [MIT License](LICENSE), unless otherwise stated. You are free to use, modify, and redistribute the code with attribution.

The **research paper** associated with this repository is licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/), as required by the publishing journal (JAIC). See the [publication](https://doi.org/10.30871/jaic.v9i6.11658) for details.

Third-party data and sources are not included in this repository, see the [Dataset](#dataset) section above.
