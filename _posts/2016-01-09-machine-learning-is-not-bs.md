---
layout: post
title:  "Machine Learning is not BS in Monitoring"
---

Recently I came across provocatively titled ["Machine Learning in Monitoring is BS"](https://medium.com/the-opsee-blog/machine-learning-in-monitoring-is-bs-134e362faee2) and decided to reply but the response came out longer than typical comment so I posted it separately.

1. Ambiguity of the data - true point. It's impossible to build a single universal model that eats any data and alert when it's wrong. But it's possible to build different models for different cases with the help of humans. And yes, it's possible for machine learning to find if a bump on EEG is good or bad, see [Epilepsy Seizure Prediction Challenge](https://www.kaggle.com/c/seizure-prediction)

2. Multiplicity of variables. It's true that mass of metrics doesn't make a lot of sense without context but adding context back and applying dimensionality reduction methods ([SVD]({{ site.url }}/blog/multivariate-svd-pca/)) allows to reduce the mass into handful. If ECG of one cow is quite different from ECGs of all other cows then it's quite likely to be sick.

3. User experience. Not all machine learning methods are opaque. [Deep learning](https://en.wikipedia.org/wiki/Deep_learning) and [gradient boosting](https://en.wikipedia.org/wiki/Gradient_boosting) models are black boxes but there are many interpretable models like [regularized linear](https://en.wikipedia.org/wiki/Linear_regression) and [logistic regression](https://en.wikipedia.org/wiki/Logistic_regression). They can give answers like "sales tomorrow will be higher than the previous Monday because it's a first working day after long holidays and sales are usually higher in that case".

4. Visualization. Traditional monitoring that is built around dashboards and staring at graphs doesn't scale. At the same time there are different ways to present loads of data in compact visual form that makes sense to human (like [MDS, T-SNE]({{ site.url }}/blog/multivariate-mds-tsne)). Machine learning  could be used to produce better visualization to help humans understand what's going on.

There is a lot of hype around machine learning and as it usually happens some of overhyped technologies fail to deliver. The same problem was faced by information security community as explained in "Secure because Math" ([pdf](https://www.blackhat.com/docs/us-14/materials/us-14-Pinto-Secure-Because-Math-A-Deep-Dive-On-Machine-Learning-Based-Monitoring-WP.pdf), [video](https://www.youtube.com/watch?v=TYVCVzEJhhQ)) talk by [@alexcpsec](https://twitter.com/alexcpsec) 

Machine learning is not a magic that would digest uncleaned and unlabeled metrics and point out when and how the system was broken. It's rather a set of tools which when used appropriately will reduce manual labor for devops looking after production systems.