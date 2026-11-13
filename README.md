# Machine Learning for Engineering Applications

Cleaned and documented Jupyter notebooks from the CEE 902 in-class exercises. Each notebook implements one supervised learning method, with the mathematics stated alongside the code and the results interpreted at the end.

**Author:** Samuel Asiedu

## Notebooks

| Notebook | Method | Problem | Implementation |
|---|---|---|---|
| [01_multivariate_linear_regression.ipynb](01_multivariate_linear_regression.ipynb) | Multivariate linear regression | House price from size, floors, and age | NumPy, batch gradient descent |
| [02_logistic_regression_flood.ipynb](02_logistic_regression_flood.ipynb) | Logistic regression | Flood occurrence from daily precipitation | NumPy, batch gradient descent |
| [03_softmax_weather_classification.ipynb](03_softmax_weather_classification.ipynb) | Softmax (multinomial logistic) regression | Sunny, Rain, or Snow from temperature and humidity | NumPy, batch gradient descent |
| [04_knn_flood_prediction.ipynb](04_knn_flood_prediction.ipynb) | K-nearest neighbors | Flood occurrence from distance to water and relative elevation | scikit-learn, train/validation/test workflow |

## Data

All datasets are synthetic or illustrative and are intended for learning only.

| Dataset | Used by | Location |
|---|---|---|
| 15 illustrative houses | Notebook 01 | Defined inside the notebook |
| 100 simulated precipitation days | Notebook 02 | Generated inside the notebook (seed 42) |
| 100 synthetic weather observations | Notebook 03 | `data/CEE902_weather_synthetic_100.csv` |
| 800 synthetic flood sites | Notebook 04 | `data/flood_sites.csv` (**not included, see below**) |

**Note on notebook 04.** The file `flood_sites.csv` is not part of this repository yet. Place it in the `data/` folder before running the notebook. The outputs currently stored in notebook 04 come from the original run of the exercise on that file.

## Getting started

```bash
pip install -r requirements.txt
```

```bash
jupyter lab
```

Start Jupyter from the repository root so that the relative `data/` paths resolve.

## Conventions used in the notebooks

- Raw data are never overwritten. Scaled copies are created from stored training statistics, and the same statistics are reused for new observations.
- Each model is wrapped in small functions (`gradient_descent`, `get_cost`, `predict_...`) so that every step can be tested on its own.
- Reported accuracies in notebooks 01 to 03 are training-set results and are labeled as such. Only notebook 04 uses a held-out test set.
