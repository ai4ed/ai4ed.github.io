---
layout: post
title:  AAAI2024 Global Competition on Math Problem Solving and Reasoning
date:   2023-10-01 10:00:00
image:  '/images/aaai2024competition.jpg'
tags:   [Competition, AAAI]
featured: false
category: competitions
---



## Background

Mathematics has always been regarded as the touchstone of artificial intelligence. The ability to reason mathematically represents, to a certain extent, the level of intelligence of today's general artificial intelligence cognitive models. When large language models overcome their "innate defects" (such as lack of complex reasoning capabilities, inaccurate numerical calculations, etc.) and successfully cope with the challenges of mathematical reasoning, **the world of artificial intelligence will enter a new era**.

In this context, how to enhance the mathematical reasoning ability of large language models and break through the innate deficiencies of language models has become a focus of attention in the global artificial intelligence field. Therefore, we have decided to hold the AAAI2024 Global Mathematical Problem Solving and Reasoning Competition, inviting AI enthusiasts, experts, and developers from around the world with forward-looking perspectives and innovative spirits to explore and solve challenges in the field of mathematics using large language models. This is not only a competition, but also a platform for collaboration, communication, and sharing innovative ideas.

This competition will bring us a brand new experience, allowing us to enjoy the fun of mathematics while appreciating the powerful capabilities of artificial intelligence. **Let us witness together how AI solves challenging problems in new ways and paves new paths for the future**.

## Data & Task Description

In this competition, in order to fully explore the mathematical reasoning abilities of various large models, we have divided the competition into two tracks: Chinese Mathematical Problem Solving and English Mathematical Problem Solving. The Chinese (TAL-SAQ7K-CN) and English (TAL-SAQ6K-EN) mathematical competition problem datasets used in the Chinese and English tracks are provided by leading Chinese educational technology company, TAL Education Group. The datasets used in this competition consist of high-quality Chinese and English mathematical competition questions, including the "Ying Chun Cup" Mathematics Competition and the "Hope Cup" Mathematics Invitational in China, as well as the AMC and other representative mathematical competitions both domestically and internationally.

These problem contents are authentic and reliable, and their formats have been carefully processed. Each problem includes the problem statement, difficulty level, and a chain of knowledge points from coarse-grained to fine-grained that are related to the problem. Moreover, the mathematical expressions in both datasets have been processed into a unified text format called Latex.

Furthermore, the TAL-SAQ7K-CN dataset covers mathematical knowledge from elementary school, middle school, and high school levels, while the TAL-SAQ6K-EN dataset only includes mathematical knowledge from the elementary school level.

### Evaluation Task

The TAL-SAQ7K-CN and TAL-SAQ6K-EN Mathematical Competition Problem datasets are used as the test sets for the competition. They consist of 7,436 and 5,927 questions, respectively. The answers to the questions will not be disclosed.

The prediction task for this competition is for the large model to generate the intermediate reasoning steps and the final answer for a given math problem. We will compare the model's predicted answers with the ground truth answers and use accuracy to determine the ranking in the competition.

**Accuracy** is the sole evaluation metric for ranking in this competition.

The evaluation results of this task are divided into public leaderboard results and private leaderboard results:

**Public leaderboard :** We have pre-randomized 30% of the data from TAL-SAQ7K-CN and TAL-SAQ6K-EN, which will be used to evaluate the participants' rankings on the public leaderboard. This portion of the data is provided for participants to debug their models and make adjustments based on the test results.

**Private leaderboard:** After the deadline, we will use the latest submission results from each team to evaluate the model results on the remaining 70% of the data from TAL-SAQ7K-CN and TAL-SAQ6K-EN. The highest score of the participants on the private leaderboard will be the final result of the competition.

### Data Files
<!-- **<span style="color:red">All the data files can be download at [https://forms.gle/3TT5VN9ZFnG3JXBPA](https://forms.gle/3TT5VN9ZFnG3JXBPA).</span>** -->
- **tal_saq7k_cn_stage_1.jsonl:** This is a part of TAL-SAQ7K-CN used in the first stage of the evaluation, with fields and examples as follows:
  -  "dataset_version": The identifier of the dataset version, identification of the source dataset version from which TAL-SCQ5K-EN/TAL-SCQ5K-CN has been created.
  - "queId": The identifier of the global ID for the question.
  - "difficulty": The difficulty level of the question, ranging from 0 to 4.
  - "qtype": The type of the question, with the value "short_answer" indicating that the question is a short answer question.
  - "problem": the question string to a math competition question.
  - "knowledge_point_routes": knowledge point route from coarse-grained to fine-grained.  
<pre class="highlight"><code>{
    "dataset_version": "2023-07-07",
    "queId": "05de5fa272834c0d91b4a9e60d3b9068",
    "difficulty": "4",
    "qtype": "short_answer",
    "problem": "一枚均匀的硬币掷$$10$$次，从不接连出现正面的概率为$$\\frac{i}{j}$$（即约分数），求$$i+j$$．",
    "knowledge_point_routes": ["竞赛-&gt;知识点-&gt;排列组合与概率-&gt;概率初步"]
}</code></pre> 
<!-- **<span style="color:red">All the data files can be download at [https://forms.gle/3TT5VN9ZFnG3JXBPA](https://forms.gle/3TT5VN9ZFnG3JXBPA).</span>** -->
- **tal_saq7k_cn_stage_2.jsonl:** This is a part of TAL-SAQ7K-CN used in the second stage of the evaluation, with the same fields and examples as above.
- **tal_saq6k_en_stage_1.jsonl:** This is a part of TAL-SAQ6K-EN used in the first stage of the evaluation, with the same fields as above and examples as follows:
<pre class="highlight"><code>{
    "dataset_version": "2023-07-07",
    "queId": "17a4a261e09e46b188ed0705441570df",
    "difficulty": "3",
    "qtype": "short_answer",
    "problem": "In a number sequence, the first integer is $$3$$, the second is $$10$$, and starting from the third integer, each integer is the sum of the two integers directly in front of it. What is the remainder when the $$1997^{\\text{th}}$$ integer is divided by $$3$$? ",
    "knowledge_point_routes": ["Overseas Competition-&gt;Knowledge Point-&gt;Number Theory Modules-&gt;Remainder Problems-&gt;Questions involving Divisions with Remainders"]
}</code></pre> 
- **tal_saq6k_en_stage_2.jsonl:** This is a part of TAL-SAQ6K-EN used in the second stage of the evaluation, with the same fields and examples as above.

### Baseline Results

We provide three test baseline methods for this competition, which are **GPT-3.5**, **GPT-4**, and **MathGPT**. Their performance on the public leaderboard is as follows:

<!-- We have used pyKT to run **DKT** and **AKT** on the aforementioned training data and evaluate on our public test sets. All these approaches are purely trained with question/KC ids and student responses without any auxiliary information, such as question content. For the **Majority** model, we use the correct rate of each question in the training dataset to predict the test set. Details can reference our [codes](https://github.com/pykt-team/pykt-toolkit/tree/main/examples/competitions/aaai2024_competition). The results are used as baseline results for this competition:

| Model      | Non-Accumulative | Accumulative     |
| :---       |    :----:        |    :----:        |
| DKT        | 0.6801           | 0.7086           |
| AKT        | 0.7812           | 0.7692           |
| Majority   | 0.7381           | -                |



Practically, there are two different approaches, i.e., **accumulative prediction** and **non-accumulative prediction**. The accumulative prediction approach uses the last predicted values for the current prediction while the non-accumulative prediction predicts all future values all at once. Details are discussed in the pyKT paper [^11]. -->

<!--### Instruction and Codes
<!-- We provide easy to use codes and detailed instructions in [here](https://github.com/pykt-team/pykt-toolkit/tree/main/examples/competitions/aaai2024_competition). -->



### Submission Site

<!-- We use codalab to receive submissions and please submit your results at [https://codalab.lisn.upsaclay.fr/competitions/8087](https://codalab.lisn.upsaclay.fr/competitions/8087). -->
We use Codabench to receive submission results, please submit your results at: 


## Competition Schedule

<!-- - November 17, 2022 - Start Date.
- December 31, 2022 - Final submission deadline.
- January 2, 2024 - Final competition results announced.-->

- October 10, 2023 - Start Date.
- December 31, 2023 - Final submission deadline.
- January 10, 2024 - Final competition results announced.
All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted.The competition organizers reserve the right to update the contest timeline if they deem it necessary.

<!--All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted.The competition organizers reserve the right to update the contest timeline if they deem it necessary.-->

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

- **Liang Xu** TAL Education Group, China
- **Jiong Zhao** TAL Education Group, China
- **Zitao Liu** Guangdong Institute of Smart Education, Jinan University, China
- **Isabelle Guyon**, Google, USA
- **Simon Woodhead**, EEDI, UK
- **Panagiota Konstantinou**, EEDI, UK

**Contact**: ai4ed-24@aaai.org


<!--## Reference-->

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
