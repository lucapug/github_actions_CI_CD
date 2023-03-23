# github_actions_CI_CD

The goal is to adopt best practices in MLops in order to productionize a ML project. To do so, we experiment Continuous Integration/Continuous Deployment (CI/CD) techniques offered by the Github actions tool. Here is a list of the main aspects treated in the present project:

* organizing the project structure in a easily interpretable manner (based on the cookie-cutter concept)
* data versioning (to be added to the code versioning functionalities offered by Github)
* continous integration: automatic actions on push events with associated reports on model performance
* dockerize the inference application, to ease the deployment
* continous deployment: automatic deployment of newly tagged versions of the app
* data drift monitoring by means of specific data-drift detector to be automatically triggered on batches of inference outputs

the technologies adopted are Iterative DVC and CML combined with Github Actions, S3 storage, Seldon Alibi for data drift detection, fly.io for app hosting

Everything is applied to the following problem:

A bank is investigating a very high rate of customer leaving the bank. In order to investigate and predict which of the customers are more likely to leave the bank soon (Exited column in the dataset), a dataset of 10.000 customers records is analyzed

Dataset source: [Deep Learning A-Z - ANN dataset | Kaggle](https://www.kaggle.com/datasets/filippoo/deep-learning-az-ann)

It's a binary classification problem over tabular data. The solution proposed as a starting point for the CI/CD experiments, is a Random Forest Classifier model, with F1 score as performance metric.
