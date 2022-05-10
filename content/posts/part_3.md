---
title: "Part III: Engine Starts"
date: 2022-05-09
description: Part III
---

# Task Discription
Idealy we shall plot hotzones of early smoking, in terms of any individul student's own risk behaviors and the environment based on his school (the school's supportive score and the distance to retailers), since youth smoking is an issue calling on efforts from multiple parties. The cautionary results would suggest special measures for the hotzones' authorities, such as goverment's education branches, tobacco braches and each community's own administrators to regulate the smoking behaviors among teenagers. In a more broad way, the results would be useful for any city management plan in the goal of youth tobbaco control, and furthermore the city's sustainability.

However, given the limited dataset and resources we can get, we are not able to distinguish the risk behavior levels down to each school, since the smallest geographical unit of YRBSS data is a whole district. Thus this project focuses on anylyzing how all kinds of individual behaviors and social environmental factors influence the smoking acquisition in a machine learning way, without geo-mapping.

All the following procedures will show what and how the dataset for training was constructed according to previous analysis, so that we can combine risk behaviors, school scoring and school-to-retailer distances to predict whether a student's would start smoking very early.

# Preprocessing
## 2.1 roughly filter YRBSS dataset
- The chosen target is the age of start smoking q31 in 2019, so we only choose rows with valid target q31 value of 2019
- Check the answers from YRBSS, and exclude question attributes with response rate less than 70%


## 2.2 encoding the features
We stratify the target value to 3 categories: non-smokers (with q31 = 1.0, those who don't smoke), youger started smokers(q31 = 2.0, 3.0 or 4.0, those who first smoke before 13 years old), and older started (q31 = 5.0, 6.0 or 7.0, those who first smoke after 13 years old).

Sitecode is a nominal feature, to feed this feature into the model we have to transform it into numbers. Integers 0 to 4 respectively corresponds to ['NYG' 'NYH' 'NYI' 'NYJ' 'NYK'].

## 2.3 impute nan values
There are still lots of missing values in df, because the students are not always keen about filling in the survey, so we need to impute these values to make them as real as possible.

The YRBSS data points sampled from the same PSU and stratum in the same borough are likely to be from the same class of the same school [ref](), so we can impute the demographic features with other valid values based on these. gender is imputed from the mode of the same (PSU,stratum) group, because we already know that male and female are roughly the same amount, so if a subgroup is one-gender dominated, there would be another subgroup is another-gender dominated, and eventually they counter off. It's not so good to guese race from mode, though, otherwise we make minority groups more minority, generating biased model on races. All statistical indicators are meaningless on race, because the numbers are manually assigned, and in fact we can't put a distance, mean value, or bigger/smaller on a race value. As a result, we randomly generate a race number. age is different from race, that we can actually compare ages, and therefore we simply use round up mean values to fill in.

The question answers are hard to impute, so we assign a new value 0.0, as a new category, to the missing ones. This will sure influence the model, because they in fact would definitely have different answers but now they are treated as the same. We will see the results then.

# Impute External Attributes from School Analysis
We want to make use of the following features from Part2 School Analysis:
- supportive environment score
- retailer to school ratio
- mean shortest distance to retailers

in which each school has a specific score and distance calculated, and a borough has a retailer to school ratio. Thus, the score and distance are uniformly sampled from each school, since the probability of one student coming from one school is equal. Students in one borough would have the same retailer to school ratio of that borough.

After this step, the dataset for training contains 8595 records.

# Build a decision tree model
## 4.1 basic model setting
raining/test set split: 70% training set, 30% test set

Model chosen: Random Forest
  The attributes are mostly categorical answers from a survey, so tree-based models would be suitable. The complexity would not be so high to overfit, and it is easy to tell whether one attribute plays an important role in classification. The advantage of Random Forest is that it offsets the data imbalance by bootstrap, which generates a new dataset sampled from the original one for each classification tree in the forest. We have seen that this dataset is not strictly balanced -- there are fewer records of Staten Island, and that's when random forest is more suitable.

## 4.2 further attributes filter, to avoid data leakage
The samples come from only high school students, so age is not randomly included -- as in Part1's demographic analysis, students are usually 14-17 years old. Since the target is also about age, and a student who is 15 should not choose that he starts smoking at 16 or 17, the age attribute is inherently correlated with the target, and as a result we should drop age.

We already know that age and grade is highly correlated in Part1 YRBSS demographic analysis, so we don't include grade column to avoid data leakage. Similarly, q30, whether smoked, and q31, initiation of smoking, have a causal relationship: if a non smoker is being honest, he should show consistency with his answers for q30 and q31, and therefore we exclude q30 as well.

Other features were then checked again on their number of missing values. The features still with small amount of missing values are kept with the missing values droped, and features with quite a few missing values are excluded completely.

![IMAGE](/part_3/part_3_cm.svg/)

## Comment
The model on all students doesn't work well enough as expected. It shows an extreme bias on "no smoking", skewing the prediction very much. More than 60% of smokers who started smoking before 13 and about 75% of smokers who started after 13 were classified as non-smoking. Possible reasons of this lie in the sizes of these two groups. Compared to over 7000 records of non-smokers, the latter two only constitute about 1000 records. This lead to the model to be underfitting, and unable to learn the smokers' characteristics, compared to the non-smokers. The issue would be relieved if given a larger dataset.

The model trained on only smokers are much less biased compared to the previous model. Both class reaches an accuracy of 70%. Considering the limited size, we can only claim the model is performing well within the existed dataset. The generalization performance is still in doubt.

Some conclusions, or perhaps assumptions can still be drawn from the comparisons, regardless of the unsatisfying results. Non-smoking high school students would always be the majority, whether they would start smoking is not always predictable, but once they pick up smoking, there might be some pattern in all kinds of behaviors, where adults and administrations can get in the way, and imporse some positive effects.

![IMAGE](/part_3/part_3_importances.svg/)

## Comment
Seeing from the top 20 most important features of the smoker model, q40, when started drinking alcohol, tops at first. This suggests that starting to smoke and starting to drink are not seperate events -- once the guard to one is down, the other might soon collapse. Similarly, q46, also in the top 5, describes the initiation age of marijuana usage. These three features combined informed us that regulations should not be isolated, and a sustainable city shall maintain a good balance in all.

Q59 describes the age of first sexual intercourse, which in combination with the tobacco, drug and alcohol complete a teenage group profile who are highly curious, impulsive and reckless, and eager to feel like adults by making not cool decisions.

Distance and score are listed the 2nd and the 3rd, meaning that our assumption that the social environments influence smoking initiation is also proved to some extent. How this two feature differ the smoking initiation age is demonstrated in the following chart.

Density, on the other hand, is not as influential as the other two envrionmental factors. The impurity lessened by it alone is only half that of the other two. It seems it does not matter that much the average number of retailers against schools, but the specific neighborhood condition of each individual school contained in distance.

Demographic features, such as race and sitecode are not very important in this model, even though we found different distributions of all years of 5 boroughs in YRBSS's analysis.

![IMAGE](/part_3/part_3_feature_diff.svg/)

## Comment
The difference within smokers who start smoking at different ages show different patterns in all the features we explored. The age of smoking initiation seems to positively related with all these 5 factors: age of starting drinking alcohol, distance to retailers, school's supportive score, age of starting using marijuana, age of first sextual intercourse. Younger age of catching up alcohol, drug and sex often predicts younger age of smoking, too. Same with the school factors, if a school is located further from tobacco retailers, and receives a higher supportive score, the students attending this school are likely to start smoking later in life.

The lesson we can learn from this result complies with our common sense, but powerful: Keep your kid away from any of this: alcohol and drug, will help them stay away from tobacco, too. Sexual education, school's societal environmental building-up and a clean, peaceful neighborhood would support their healthy behaviors, and any administrator and stakeholder in the related departments should bare this in mind, to make their city more upright and sustainable for the younger people.
