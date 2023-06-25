<div id="top" align="center">

<img src=https://github.com/IIIS-Li-Group/OpenFE/blob/master/docs/logo/openfe.svg width=300 />

OpenFE: An efficient automated feature generation tool
-----------------------------
<h3> |<a href="https://arxiv.org/abs/2211.12507"> Paper </a> | 
<a href="https://openfe-document.readthedocs.io/en/latest/"> Documentation </a> | 
<a href="https://github.com/IIIS-Li-Group/OpenFE/tree/master/examples"> Examples </a> |  </h3>

</div>

OpenFE is a new framework for automated feature generation for tabular data. 
OpenFE is easy-to-use, effective, and efficient with following advantages:
- OpenFE can discover effective candidate features for improving the learning performance of both GBDT and neural networks.
- OpenFE is efficient and supports parallel computing.
- OpenFE covers 23 useful and effective operators for generating candidate features.
- OpenFE supports binary-classification, multi-classification, and regression tasks.
- OpenFE can automatically handle missing values and categorical features.

For further details, please refer to [the paper](https://arxiv.org/abs/2211.12507). 

Extensive comparison experiments on public datasets show that OpenFE outperforms existing feature generation methods on both effectiveness and efficiency.
Moreover, we validate OpenFE on the [IEEE-CIS Fraud Detection](https://www.kaggle.com/competitions/ieee-fraud-detection)
Kaggle competition, and show that a simple XGBoost model with features generated by OpenFE 
beats 99.3% of 6351 data science teams. The features generated by OpenFE results in larger performance
improvement than the features provided by the first-place team in the competition.

# 🔥 News
- [**2023-06-25**]: The code and datasets to reproduce the results in our paper are now available at [OpenFE_reproduce](https://github.com/ZhangTP1996/OpenFE_reproduce). Please note that the code for OpenFE in OpenFE_reproduce is not the most recent version, as it is intended solely for reproduction purposes. Typically, employing the latest version here will yield superior performance.
- [**2023-04-26**]: OpenFE has been accepted by ICML2023!


# 🏴󠁶󠁵󠁭󠁡󠁰󠁿 Get Started and Documentation

## Installation

It is recommended to use **pip** for installation.

```
pip install openfe
```

Please do not use **conda install openfe** for installation.
It will install another python package different from ours.

## ⚡️ A Quick Example

It only takes four lines of codes to generate features by OpenFE. First, we generate features by OpenFE.
Next, we augment the train and test data by the generated features.

```
from openfe import OpenFE, transform

ofe = OpenFE()
features = ofe.fit(data=train_x, label=train_y, n_jobs=n_jobs)  # generate new features
train_x, test_x = transform(train_x, test_x, features, n_jobs=n_jobs) # transform the train and test data according to generated features.
```

We provide an example using the standard california_housing dataset in 
[this link](<https://github.com/IIIS-Li-Group/OpenFE/blob/master/examples/california_housing.py>). 
A more complicated example demonstrating OpenFE can outperform machine learning experts in the IEEE-CIS Fraud Detection 
Kaggle competition is provided in [this link](<https://github.com/IIIS-Li-Group/OpenFE/blob/master/examples/IEEE-CIS-Fraud-Detection/>).
Users can also refer to our [documentation](<https://openfe-document.readthedocs.io/en/latest/>) for more advanced usage of OpenFE and FAQ about feature generation.
