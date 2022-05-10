---
title: "Part III: Engine Starts"
date: 2022-05-09
description: "Given the analysis we did in previous parts, this one will show how the dataset for training was constructed according to previous analysis, so that we can combine risk behaviors, school scoring and school-to-retailer distances to predict whether a student would start smoking early using Random Forest model."
---

# Combine Everything to Achieve More
Given the analysis we did in previous pages, ideally, we shall plot hot zones of early smoking, in terms of any individual student's own risk behaviors and the environment based on his school (the school's supportive score and the distance to retailers), since youth smoking is an issue calling on efforts from multiple parties. The cautionary results would suggest special measures for the hot zones' authorities, such as government’s education branches, tobacco branches and each community's own administrators to regulate the smoking behaviors among teenagers. In a broader way, the results would be useful for any city management plan in the goal of youth tobacco control, and furthermore the city's sustainability.
However, given the limited dataset and resources we can get, we are not able to distinguish the risk behavior levels down to each school, since the smallest geographical unit of YRBSS data is a whole district. Thus, this project focuses on analyzing how all kinds of individual behaviors and social environmental factors influence the smoking acquisition in a machine learning way, without geo-mapping.

All the following procedures will show what and how the dataset for training was constructed according to previous analysis, so that we can combine risk behaviors, school scoring and school-to-retailer distances to predict whether a student would start smoking very early.

# A Random Forest Model
The attributes are mostly categorical answers from a survey, so tree-based models would be suitable. The complexity would not be so high to overfit, and it is easy to tell whether one attribute plays an important role in classification. The advantage of Random Forest is that it offsets the data imbalance by bootstrap, which generates a new dataset sampled from the original one for each classification tree in the forest. We have seen that this dataset is not strictly balanced -- there are fewer records of Staten Island, and that's when random forest is more suitable.
The training set and test set is split from the chosen dataset with ration 7:3. Over 8000 data are used eventually.

# Performances on All Students, and Only Smoking Students
The model on all students reaches 100% correctness in the training set, but unfortunately doesn't work well enough as expected on the test set. See the left confusion matrix plot below. It shows an extreme bias on "no smoking", skewing the prediction very much. More than 60% of smokers who started smoking before 13 and about 75% of smokers who started after 13 were classified as non-smoking. Possible reasons of this lie in the sizes of these two groups. Compared to over 7000 records of non-smokers, the latter two only constitute about 1000 records. This led to the model to be underfitting, and unable to learn the smokers' characteristics, compared to the non-smokers. The issue would be relieved if given a larger dataset.
The model trained on only smokers are much less biased compared to the previous model. Both classes reach an accuracy of 70%. Considering the limited size, we can only claim the model is performing well within the existed dataset. The generalization performance is still in doubt.
![IMAGE](/part_3/part_3_cm.svg/)

# Smokers Are Predictable, According to This Model
To review this model, we first scan the features’ importance’s in predicting early smoking:
![IMAGE](/part_3/part_3_importances.svg/)

Seeing from the top 20 most important features of the smoker model, `q40`, when started drinking alcohol, tops at first. This suggests that starting to smoke and starting to drink are not seperate events -- once the guard to one is down, the other might soon collapse. Similarly, `q46`, also in the top 5, describes the initiation age of marijuana usage. These three features combined informed us that regulations should not be isolated, and a sustainable city shall maintain a good balance in all.
`q59` describes the age of first sexual intercourse, which in combination with the tobacco, drug and alcohol complete a teenage group profile who are highly curious, impulsive and reckless, and eager to feel like adults by making not cool decisions.
`distance` and `score` are listed the 2nd and the 3rd, meaning that our assumption that the social environments influence smoking initiation is also proved to some extent. How this two feature differ the smoking initiation age is demonstrated in the following chart.
`density`, on the other hand, is not as influential as the other two envrionmental factors. The impurity lessened by it alone is only half that of the other two. It seems it does not matter that much the average number of retailers against schools, but the specific neighborhood condition of each individual school contained in `distance`.
Demographic features, such as `race` and `sitecode` are not very important in this model, even though we found different distributions of all years of 5 boroughs in YRBSS's analysis.
In the end, trying to dig in how early smokers behave differently with those started smoking later, let’s check the exact distribution of the top 5 important features:
![IMAGE](/part_3/part_3_feature_diff.svg/)

The difference within smokers who start smoking at different ages show different patterns in all the features we explored. The age of smoking initiation seems to positively related with all these 5 factors: age of starting drinking alcohol, distance to retailers, school's supportive score, age of starting using marijuana, age of first sextual intercourse. Younger age of catching up alcohol, drug and sex often predicts younger age of smoking, too. Same with the school factors, if a school is located further from tobacco retailers, and receives a higher supportive score, the students attending this school are likely to start smoking later in life.
The lesson we can learn from this result complies with our common sense, but powerful: Keep your kid away from any of this: alcohol and drug, will help them stay away from tobacco, too. Sexual education, school's societal environmental building-up and a clean, peaceful neighborhood would support their healthy behaviors, and any administrator and stakeholder in the related departments should bare this in mind, to make their city more upright and sustainable for the younger people.
