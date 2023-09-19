---
layout: post
title:  AAAI2024 Global Competition of Solving Math Problems using LLMs
date:   2023-10-01 10:00:00
image:  '/images/aaai2024competition.jpg'
tags:   [Competition, AAAI]
featured: false
category: competitions
---



## Background

In this competition, we would like to call for researchers and practitioners worldwide to investigate the opportunities of **xxx**. 



## Data & Task Description




### Evaluation Task






### Data Files



<!-- **<span style="color:red">All the data files can be download at [https://forms.gle/3TT5VN9ZFnG3JXBPA](https://forms.gle/3TT5VN9ZFnG3JXBPA).</span>** -->


### Baseline Results

<!-- We have used pyKT to run **DKT** and **AKT** on the aforementioned training data and evaluate on our public test sets. All these approaches are purely trained with question/KC ids and student responses without any auxiliary information, such as question content. For the **Majority** model, we use the correct rate of each question in the training dataset to predict the test set. Details can reference our [codes](https://github.com/pykt-team/pykt-toolkit/tree/main/examples/competitions/aaai2024_competition). The results are used as baseline results for this competition:

| Model      | Non-Accumulative | Accumulative     |
| :---       |    :----:        |    :----:        |
| DKT        | 0.6801           | 0.7086           |
| AKT        | 0.7812           | 0.7692           |
| Majority   | 0.7381           | -                |



Practically, there are two different approaches, i.e., **accumulative prediction** and **non-accumulative prediction**. The accumulative prediction approach uses the last predicted values for the current prediction while the non-accumulative prediction predicts all future values all at once. Details are discussed in the pyKT paper [^11]. -->

### Instruction and Codes
<!-- We provide easy to use codes and detailed instructions in [here](https://github.com/pykt-team/pykt-toolkit/tree/main/examples/competitions/aaai2024_competition). -->



### Submission Site

<!-- We use codalab to receive submissions and please submit your results at [https://codalab.lisn.upsaclay.fr/competitions/8087](https://codalab.lisn.upsaclay.fr/competitions/8087). -->


## Competition Schedule

<!-- - November 17, 2022 - Start Date.
- December 31, 2022 - Final submission deadline.
- January 2, 2024 - Final competition results announced.

All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted.The competition organizers reserve the right to update  -->the contest timeline if they deem it necessary.

## Award

- We will provide cash prizes for the top-3 teams (1st place: $1000; 2nd place: $600 ; 3rd place $300)
- An official certificate will be awarded to the top-3 teams.
- The top-3 teams will be invited to give oral presentations during AAAI 2024.
- The first author of the top-3 teams will be invited to contribute to a competition review paper.

Note: The top-3 teams should make their training and testing code publicly available for verification after the testing submission deadline.


## Sponsor

![Sponsor TAL Education Group]({{site.baseurl}}/images/aaai2024competition_sponsor.jpg) 


## Terms and Conditions

The rules of the competition are as follows:
- Submitted code must use a machine learning model to generate predictions. Submission of hard-coded prediction results is prohibited.
- Users may work in teams of up to 6 people.
- For participants to be eligible for prizes, their code must be publicly available.


## Organizers

* **Liang Xu** TAL Education Group, China
* **Jiong Zhao** TAL Education Group, China
* **Ying Zheng** Guangdong Institute of Smart Education, Jinan University, China
* **Jiahao Chen** TAL Education Group, China

**Contact**: <pykt.team@gmail.com>


## Reference

<!-- [^1]: Piech, Chris, et al. "Deep knowledge tracing." Advances in neural information processing systems 28 (2015).
[^2]: Yeung, Chun-Kit, and Dit-Yan Yeung. "Addressing two problems in deep knowledge tracing via prediction-consistent regularization." Proceedings of the Fifth Annual ACM Conference on Learning at Scale. 2018.
[^3]: Nagatani, Koki, et al. "Augmenting knowledge tracing by considering forgetting behavior." The World Wide Web Conference. 2019.
[^4]: Lee, Jinseok, and Dit-Yan Yeung. "Knowledge query network for knowledge tracing: How knowledge interacts with skills." Proceedings of the 9th international conference on learning analytics & knowledge. 2019.
[^5]: Zhang, Jiani, et al. "Dynamic key-value memory networks for knowledge tracing." Proceedings of the 26th international conference on World Wide Web. 2017.
[^6]: Guo, Xiaopeng, et al. "Enhancing Knowledge Tracing via Adversarial Training." Proceedings of the 29th ACM International Conference on Multimedia. 2021.
[^7]: Nakagawa, Hiromi, Yusuke Iwasawa, and Yutaka Matsuo. "Graph-based knowledge tracing: modeling student proficiency using graph neural network." 2019 IEEE/WIC/ACM International Conference On Web Intelligence (WI). IEEE, 2019.
[^8]: Ghosh, Aritra, Neil Heffernan, and Andrew S. Lan. "Context-aware attentive knowledge tracing." Proceedings of the 26th ACM SIGKDD international conference on knowledge discovery & data mining. 2020.
[^9]: Pandey, Shalini, and George Karypis. "A self-attentive model for knowledge tracing." 12th International Conference on Educational Data Mining, EDM 2019. International Educational Data Mining Society, 2019.
[^10]: Choi, Youngduck, et al. "Towards an appropriate query, key, and value computation for knowledge tracing." Proceedings of the Seventh ACM Conference on Learning@Scale. 2020.
[^11]: Liu, Zitao, et al. "pyKT: A Python Library to Benchmark Deep Learning based Knowledge Tracing Models." Thirty-sixth Conference on Neural Information Processing Systems Datasets and Benchmarks Track. -->
