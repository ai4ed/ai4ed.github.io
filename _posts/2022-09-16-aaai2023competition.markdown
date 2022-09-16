---
layout: post
title:  AAAI2023 Global Knowledge Tracing Challenge
date:   2022-09-16 10:00:00
image:  '/images/aaai2023competition.jpg'
tags:   [Competition, AAAI]
featured: true
category: competitions
---


## Global Knowledge Tracing Challenge

In this competition, we would like to call for researchers and practitioners worldwide to investigate the opportunities of **improving the student assessment performance via knowledge tracing approaches with rich side information**. 

Knowledge tracing (KT) is the task of **using students' historical learning interaction data to model their knowledge mastery over time so as to make predictions on their future interaction performance**, shown in the following Figure. Such predictive capabilities can potentially help students learn better and faster when paired with high-quality learning materials and instructions, which is crucial for building next-generation smart and personalized education. 


![A graphical illustration of knowledge tracing]({{site.baseurl}}/images/aaai2023competition_kt.jpg)


The KT related research has been studied since 1990s where Corbett and Anderson, to the best of our knowledge, were the first to estimate students' current knowledge with regard to each individual knowledge component (KC). A KC is a description of a mental structure or process that a learner uses, alone or in combination with other KCs, to accomplish steps in a task or a problem. Since then, many attempts have been made to solve the KT problem, such as probabilistic graphical models and factor analysis based models. Recently, due to the rapid advances of deep neural networks, deep learning based knowledge tracing (DLKT) models have become the de facto KT framework for modeling students' mastery of KCs. 


However, even through a large body of deep learning based KT models are proposed, the majority of existing baselines don't utilize the rich auxiliary side information in educational contexts. Various auxiliary side information could be extracted as external knowledge and integrated with the DLKT models. These auxiliary knowledge are expected to improve DLKT performance, which can be considered as follows:

* **Question side information**: (1) question text content; (2) latent question variations with respect to each KC; (3) question difficulty level; and (4) relations among questions.
* **Student side information**: (1) historical successful and failed attempts; (2) recent attempts; (3) students' learning ability; and (4) individualized prior knowledge of students.
* **KC side information**: (1) latent knowledge representation; and (2) relations among KCs.

Therefore, in this competition, we would like to call for researchers and practitioners to improve the KT models' performance by considering rich side information. The proposed education challenge will release a large student assessment dataset with rich textual and structural information. Specifically, the dataset is made up of 18,066 students, 7,652 questions, 1,175 KCs and 5,549,635 interactions. The average student historical sequence length is 307.19. Each question is associated with question text content, the explanations of question answers and its corresponding KCs. The relevant KCs are hierarchically structured. 

### Evaluation Metric

We will choose to use **AUC score** as the main evaluation metric for this competition. We will release the public training and test datasets for offline training and self-evaluation and will use a withheld private dataset to evaluate the final ranking of the competition participation teams. 



<!-- ## Important Dates

* ~~**November 12, 2021**~~ **November 19, 2021**: Workshop paper submission due AOE
* **November 30, 2021** : Notifications of acceptance
* **December 15, 2021**: Deadline of the camera-ready final paper submission
* **Feb 21, 2022**: Workshop Date  -->



## Organizers

<!-- ![Beautiful place]({{site.baseurl}}/images/aaai2022_workshop_organizers.jpg) -->

* **Zitao Liu** TAL Education Group, China
* **Weiqi Luo** Guangdong Institute of Smart Education, Jinan University, China
* **Shaghayegh (Sherry) Sahebi** University at Albany – SUNY, USA
* **Lu Yu** Beijing Normal University, China
* **Richard Tong** Squirrel AI Learning, USA
* **Jiahao Chen** TAL Education Group, China
* **Qiongqiong Liu** TAL Education Group, China