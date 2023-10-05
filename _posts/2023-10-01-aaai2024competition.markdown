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

Mathematics has always been regarded as the touchstone of artificial intelligence. The ability to reason mathematically represents, to a certain extent, the level of intelligence of today's general artificial intelligence cognitive models. When large language models (LLMs) overcome their "innate defects" (such as lack of complex reasoning capabilities, inaccurate numerical calculations, etc.) and successfully cope with the challenges of mathematical reasoning, the world of artificial intelligence will enter a new era.

In this context, how to enhance the mathematical reasoning ability of LLMs and break through the innate deficiencies of language models has become a focus of attention in the global artificial intelligence field. Therefore, we have decided to hold the AAAI2024 Global Competition on Mathematical Problem Solving and Reasoning, inviting AI enthusiasts, experts, and developers from around the world with forward-looking perspectives and innovative spirits to explore and solve challenges in the field of mathematics using LLMs. Specifically, in this competition, we would like to ask participants to **automatically solve K-12 math problems by using LLMs**.

This competition will bring us a brand new experience, allowing us to enjoy the fun of mathematics while appreciating the powerful capabilities of artificial intelligence. Let us witness together how AI solves challenging problems in new ways and paves new paths for the future.

## Data & Task Description

In this competition, to fully explore the mathematical reasoning abilities of various large models, we have divided the competition into two tracks: 


- Track 1: Chinese Math Problem Solving 

- Track 2: English Math Problem Solving


The math problem datasets used in both tracks are collect from K-12 math related competitions, including the "Ying Chun Cup", "Hope Cup" Mathematics Competition in China and the American Mathematics Competitions (AMC 8/10/12) worldwide. Both the datasets for track 1 (TAL-SAQ7K-CN dataset) and track 2 (TAL-SAQ6K-EN) are provided by TAL Education Group (NYSE:TAL), which is a leading smart learning solutions provider in China with global footprints.

These problem contents are authentic and reliable, and their formats have been carefully processed. Each problem includes the problem statement, difficulty level, and a chain of knowledge concepts/points from coarse-grained to fine-grained that are related to the problem. Moreover, the mathematical expressions in both datasets have been processed into the standard Latex format.

Specifically, the TAL-SAQ7K-CN dataset covers mathematical knowledge from elementary school, middle school, and high school levels, while the TAL-SAQ6K-EN dataset only includes mathematical knowledge from the elementary school level.

### Evaluation Task

The TAL-SAQ7K-CN and TAL-SAQ6K-EN datasets are used as the test sets for this competition. They consist of 7,436 and 5,927 questions respectively. Answers to the questions will not be disclosed.

The prediction task is using LLMs to generate the intermediate reasoning steps and the final answer for math problems. When submitting the results, the participants are asked to **submit all the predicted results of all the math problems in either track 1 or track 2**. We will compare the model's predicted answers with the ground truth answers and use accuracy to determine the ranking in the competition. **Accuracy is the sole evaluation metric for ranking in this competition**.


### Leaderboards

In this competition, we create both public and private leaderboards for better participation experience:

- **public leaderboard**: The team ranking in public leaderboard are measured in terms of accuracy  on a pre-fixed 30% of data samples in TAL-SAQ7K-CN or TAL-SAQ6K-EN. The purpose of this public leaderboard is to help participants debug and fine-tune their LLMs results.


- **private leaderboard**: The competition awards are **only based on the team ranking in private leaderboard**. We will use the remaining 70% data samples in TAL-SAQ7K-CN or TAL-SAQ6K-EN for evaluation. The highest score of the participants on the private leaderboard will be the final result of the competition.

### Data Files

Both the TAL-SAQ7K-CN and TAL-SAQ6K-EN datasets can be download at [https://github.com/math-eval/aaai2024comp](https://github.com/math-eval/aaai2024comp).

Each question and its auxiliary information is stored in the JSON format with the following fields:

- "dataset_version": The identifier of the source dataset version.
- "queId": The identifier of the global ID for the question.
- "difficulty": The difficulty level of the question, ranging from 0 to 4.
- "qtype": The type of the question, with the value "short_answer" indicating that the question is a short answer question.
- "problem": The question content of a math competition question.
- "knowledge_point_routes": The knowledge point route from coarse-grained to fine-grained.  

Here, we provide a real sample from TAL-SAQ6K-EN and TAL-SAQ7K-CN respectively.


#### A math problem sample from TAL-SAQ6K-EN

```
{
    "dataset_version": "2023-07-07",
    "queId": "17a4a261e09e46b188ed0705441570df",
    "difficulty": "3",
    "qtype": "short_answer",
    "problem": "In a number sequence, the first integer is $$3$$, the second is $$10$$, and starting from the third integer, each integer is the sum of the two integers directly in front of it. What is the remainder when the $$1997^{\\text{th}}$$ integer is divided by $$3$$? ",
    "knowledge_point_routes": ["Overseas Competition-&gt;Knowledge Point-&gt;Number Theory Modules-&gt;Remainder Problems-&gt;Questions involving Divisions with Remainders"]
}
```

#### A math problem sample from TAL-SAQ7K-CN

```
{
    "dataset_version": "2023-07-07",
    "queId": "05de5fa272834c0d91b4a9e60d3b9068",
    "difficulty": "4",
    "qtype": "short_answer",
    "problem": "一枚均匀的硬币掷$$10$$次，从不接连出现正面的概率为$$\\frac{i}{j}$$（即约分数），求$$i+j$$．",
    "knowledge_point_routes": ["竞赛-&gt;知识点-&gt;排列组合与概率-&gt;概率初步"]
}
```




### Baseline Results

We provide three test baseline methods for this competition, which are **GPT-3.5**, **GPT-4**, and **MathGPT**. Their performance on the public leaderboard is as follows:

|   | TAL-SAQ7K-CN-Public | TAL-SAQ6K-EN-Public |
| -------- | -------- | -------- |
| GPT3.5| 13.5| 50.84 |

### Submission Instructions

In this competition, we require the participants to submit their prediction results of all math problems in either track 1 or track 2. As we mentioned, there are 7436 and 5927 math problems in track 1 and track 2 respectively.

When preparing the prediction results, please strictly following the rules below:

- Generate your prediction results in a JSON format: The JSON file should only contain queIds (unique identifier of each question) as the key, and the cleaned final answer (extracted from the models' original generations) in **str** format as the value. 
- Name your prediction results files to **TAL_SAQ7K_CN_prediction.json** for track 1 and **TAL_SAQ6K_EN_prediction.json** for track 2.
- Please **zip** your json result file as follows:
  * create a folder and put your json file in.
  * open your terminal and cd to the folder
  * run the **zip** command as ___zip file_to_be_submitted.zip *___
- Submit the **file_to_be_submitted.zip** file to Codabench.



Here is an example of expected submission format: [https://github.com/math-eval/aaai2024comp/blob/main/submission_example.json](https://github.com/math-eval/aaai2024comp/blob/main/submission_example.json).


We use Codabench to receive submission results, please submit your results at: 

- Track 1: [https://www.codabench.org/competitions/1455/](https://www.codabench.org/competitions/1455/)

- Track 2: [https://www.codabench.org/competitions/1456/](https://www.codabench.org/competitions/1456/)



## Competition Schedule


- October 10, 2023 - Start date.
- December 31, 2023 - Final submission deadline.
- January 10, 2024 - Final competition results announced.

All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted.The competition organizers reserve the right to update the contest timeline if they deem it necessary.



## Award

- We will provide cash prizes for the top-3 teams of both tracks (1st place: $1000; 2nd place: $600; 3rd place $300)
- An official certificate will be awarded to the top-3 teams for both track 1 and track 2.
- The top-3 teams of two tracks will be invited to give oral presentations during AAAI 2024.
- The first author of the top-3 teams from both tracks will be invited to contribute to a competition review paper.

Note: The top-3 teams should make their training and testing code publicly available for verification after the testing submission deadline.


## Sponsor

![Sponsor TAL Education Group]({{site.baseurl}}/images/aaai2024competition_sponsor.jpg) 


## Terms and Conditions

The rules of the competition are as follows:

- Participants can choose to participate one of two tracks or both.
- Submitted code must use a machine learning model to generate predictions. Submission of hard-coded prediction results is prohibited.
- Users may work in teams of up to 6 people.
- For participants to be eligible for prizes, their code must be publicly available.


## Competition Organizers

<div class="grid-custom grid-cols-4">

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Liang-Xu.png" />
    <div class="title">
      Liang Xu
    </div>
    <P class="text-center">Staff Machine Learning Engineer</P>
    <P class="text-center">TAL Education Group, China</P>
  </div>

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Jiong-Zhao.png" />
    <div class="title">
      Jiong Zhao
    </div>
    <P class="text-center">Staff Machine Learning Engineer</P>
    <P class="text-center">TAL Education Group, China</P>
  </div>

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Jiahao-Chen.png" />
    <div class="title">
      <a href="https://www.tabchen.com/" target="_blank">Jiahao Chen</a>
    </div>
    <P class="text-center">Staff Machine Learning Engineer</P>
    <P class="text-center">TAL Education Group, China</P>
  </div>


  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Zitao-Liu.png" />
    <div class="title">
      <a href="https://www.zitaoliu.com/" target="_blank">Zitao Liu</a>
    </div>
    <P class="text-center">Dean of Guangdong Institute of Smart Education,</P>
    <P class="text-center">Jinan University, Guangzhou, China</P>
  </div>

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Isabelle-Guyon.png" />
    <div class="title">
      <a href="https://guyon.chalearn.org/" target="_blank">Isabelle Guyon</a>
    </div>
    <P class="text-center">Director of Research</P>
    <P class="text-center">Google Brain</P>
  </div>

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Muktha-Ananda.png" />
    <div class="title">
      <a href="https://www.linkedin.com/in/mukthananda/" target="_blank">Muktha Ananda</a>
    </div>
    <P class="text-center">Director of Engineering</P>
    <P class="text-center">Google Learning Platform</P>
  </div>

  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Simon-Woodhead.png" />
    <div class="title">
      <a href="https://www.linkedin.com/in/simon-woodhead/?originalSubdomain=uk" target="_blank">Simon Woodhead</a>
    </div>
    <P class="text-center">Chief Data Scientist and Co-Founder</P>
    <P class="text-center">EEDI, UK</P>
  </div>
  <div class="avatar-item">
    <img src="{{site.baseurl}}/images/aaai2024/Panagiota-Konstantinou.png" />
    <div class="title">
      <a href="https://www.linkedin.com/in/panagiota-konstantinou/" target="_blank">Panagiota Konstantinou</a>
    </div>
    <P class="text-center">Machine Learning Research Engineer</P>
    <P class="text-center">EEDI, UK</P>
  </div>
</div>

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
