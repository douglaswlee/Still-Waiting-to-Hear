# Still-Waiting-to-Hear

This repo contains the work I did for my third indivdual project at Metis. For this project, I collected submissions to reddit's graduate school admissions subreddit, [r/GradAdmissions](https://www.reddit.com/r/gradadmissions/), from March through May 2018. This subreddit exists for prospective graduate school candidates to ask for advice and share experiences about the graduate school admissions process. 

My goals for this project were to:
1. Describe what topics best describe submissions to r/GradAdmissions (using Topic Modeling and t-distributed stochastic neighbor embedding (t-SNE))
2. Understand how these topics, along with characteristics of the submissions and the submitting user, contribute to the incidence of “useful feedback” (using Logistic Regression):

For this work, I characterize "useful feedback" according to whether the original poster (OP) returns to the comments section associated with the submission and thanks others for their responses.

This repo contains the following files:
* **RedditScrape.ipynb**, notebook which collects submissions and their associated comments from r/GradAdmissions
* **GetOPAttributesFinal.ipynb**, notebook which collects attributes of the OP for each submission from r/GradAdmisions pulled using **RedditScrape.ipynb**
* **TopicModeling.ipynb**, notebook which:
  * Prepares the submissions collected from **RedditScrape.ipynb** for topic modeling
  * Performs topic modeling using Term Frequency-Inverse Document Frequency (TF-IDF) and Non-negative Matrix Factorization (NMF)
  * Creates an interactive t-SNE plot to visualize the topics (see **gradadmissions.html**)
* **SupervisedLearningFromTopics.ipynb**, notebook which:
  * Prepares and merges the submission (document)-topic matrix from **TopicModeling.ipynb** and comments collected from **RedditScrape.ipynb** as data for a set of logistic regression models
  * Builds, evaluates, selects, and mildly tunes a logistic regression model
