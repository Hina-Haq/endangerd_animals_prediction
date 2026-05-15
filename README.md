<div align="center">

# Wildlife Threat Prediction

### A Machine Learning Model for Threatened Species

**Hina Haq**

</div>

---

## Index

- [Project Overview](#project-overview)
- [Introduction](#introduction)
- [Data Sources](#data-sources)
- [Data Preparation](#data-preparation)
- [Models Tested](#models-tested)
- [Results](#results)
- [Predictions](#predictions)
- [Next Steps](#next-steps)
- [Tools Used](#tools-used)
- [Repository Structure](#repository-structure)
- [How to Run](#how-to-run)
- [Links](#links)
- [Limitations](#limitations)

---

## Project Overview

Wildlife Threat Prediction is a machine learning project that predicts whether a species is threatened using taxonomy and conservation data.

The model is built as a screening tool to help conservation teams prioritize species that may need closer attention. It is designed to support expert review, not replace it. 

---

## Introduction

Scientists estimate that 150 to 200 species of animals, plants, insects, and birds go extinct every single day. 

This project addresses that challenge by using machine learning to flag species that may be at higher risk. The idea is simple: instead of manually reviewing every species, the model helps surface the ones that deserve a closer look. 

---

## Data Sources

This project uses two public conservation sources:

- [IUCN Red List](https://www.iucnredlist.org/)
- [WWF Species Profiles](https://www.worldwildlife.org/species/)

The WWF dataset contained 82 rows and provided threatened-status labels, while the IUCN dataset contained 159,542 rows and provided taxonomy and species context. 

---

## Data Preparation

The workflow followed a simple data pipeline:
1. Load the WWF and IUCN datasets.
2. Match records using scientific names.
3. Build one final modelling table.
4. Encode categorical variables into numeric values.
5. Split the data into train and test sets.
6. Engineer additional features such as taxonomic risk signals. 

I used taxonomy-related variables as habitat proxies to help the model detect useful patterns. 

---

## Models Tested

Several classification models were compared:
- Decision Tree.
- Bagging.
- Random Forest.
- AdaBoost.
- Gradient Boosting. 

Bagging was selected because it had the highest test accuracy and the most stable validation results. 

---

## Results

The final model achieved 74.5% test accuracy. 

Its key classification results were:
- Non-threatened recall: 0.95.
- Threatened recall: 0.20.
- Threatened precision: 0.60. 

This means the model is useful as an initial screening tool, but it still misses too many threatened species to be used as the only decision-maker. 

---

## Predictions

The final model ranked species by predicted threat probability and returned the top five highest-risk species.

The top five were:
- *Acipenser ruthenus*.
- *Cookeconcha contorta*.
- *Acipenser oxyrinchus*.
- *Acipenser transmontanus*.
- *Meta stridulans*. 

Four of these were correct predictions, and one was a false positive. 

---

## Next Steps

To improve the model, the next steps would be:
- Add more ecological and geographic data. 
- Try stronger imbalance-handling methods. 
- Improve feature engineering. 
- Tune the classification threshold to improve recall for threatened species. 

---

## Tools Used

- Python.
- Pandas.
- NumPy.
- Matplotlib.
- Scikit-learn.
- Jupyter Notebook. 

---

## Repository Structure

```text
endangerd_animals_prediction/
│
├── README.md
├── WildlifeThreatPrediction.pptx
├── WildlifeThreatPrediction.pdf
├── Notes-for-presentaion.docx
└── finalML_final.ipynb
```

---

## How to Run

1. Open `finalML_final.ipynb`.
2. Run the notebook from top to bottom.
3. Update the dataset paths for your local machine.
4. Review the model outputs, predictions, and evaluation metrics. 

---

## Links

- [IUCN Red List](https://www.iucnredlist.org/)
- [WWF Species Profiles](https://www.worldwildlife.org/species/)
- [Final Presentation PDF](https://github.com/Hina-Haq/endangerd_animals_prediction/blob/main/WildlifeThreatPrediction.pdf)

---

## Limitations

- The WWF dataset is very small compared with the IUCN dataset. 
- The model has weak recall for threatened species. 
- Accuracy alone is not enough for a conservation screening model. 
- More ecological and geographic data would likely improve performance. 

---

*This project is for educational purposes only*
*Student Project from IronHack*
