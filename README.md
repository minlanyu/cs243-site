# CS 243, Fall 2024: Advanced Computer Networks

## Overview

This is a graduate-level course on computer networks, offering an in-depth exploration of selected advanced topics in networked systems. We will discuss the latest developments across the entire networking stack, the interactions between networks and high-level applications, and their connections with other system components such as compute and storage.

In this year's edition, we will use machine learning as a prime example to understand its unique requirements and challenges in the context of networking. As machine learning applications increasingly rely on larger models and faster accelerators, the demand for enhanced networking capabilities becomes imperative. Throughout this course, we will study cutting edge networking solutions and principles for  co-designing networks with compute and storage, to meet the evolving needs of machine learning applications. The course will include lectures, in-class presentations, paper discussions, and a research project.

- Instructor: Minlan Yu
- Lecture time: TuTh 11:15am to 12:30pm
- Location: SEC 1.402
- Office hour: Tu 10-11am, SEC 4.415
- Teaching fellows: Qianru Lao qianrulao@fas.harvard.edu; Shiji Xin sxin@fas.harvard.edu
- Prerequisite: This course has no prerequisites. Since this course will focus on reading papers on latest topics in networking, you will need to be able to pick up the relevant background for each topic from textbooks or online materials.
- Recommended prep: system programming at the level of CS 61 or CS 143 or CS 145.

## Infrastructure Notes

**If you are thinking of attending the class, please check [the infrastructure page](infra.md) to set up your infrastructure as soon as possible**

## Textbook
There are no required textbooks for the course. You will read papers before each class to get the most out of the class. For backgrounds, you are encouraged to refer to the following books:
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach, by Jim Kurose and Keith Ross. The latest is 8th edition but earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach, by Larry Peterson and Bruce Davie. You can find an online version [here](https://book.systemsapproach.org/).
- Please contact me if some concepts are hard to understand and I'll provide more supplemental materials.

## Coursework and Grading
- Project: 50% (1% project proposal, 4% initial project presentation, 5% mid-term report, 5% final project presentation, 35% final report and code)
- Reviews: 35%
- Class presentation: 10%
- Class participation: 5% (including class attendance, in-class discussion, and online discussion on Ed)

Please see detailed requirements after the syllabus

## Syllabus

We have introduced a group of new papers this year again. The papers we read have an emphasis on distributed systems and networking in the ML area. 

### Introduction
- 9/3 Tu: Introduction (Minlan)
  * Reading 1: [Applied Machine Learning at Facebook: A Datacenter Infrastructure Perspective](https://research.facebook.com/file/904032783795098/hpca-2018-facebook.pdf)
  * Reading 2: [How to Read a Paper](https://www.cs.princeton.edu/courses/archive/fall13/cos597E/papers/howtoread.pdf)
- 9/5 Th: Background on model and hardware (Minlan)
<!--
https://jalammar.github.io/illustrated-transformer/
https://jalammar.github.io/illustrated-gpt2/
-->

### Distributed Training (various parallelism schemes)
- 9/10 Tu: Data Parallellism and Sharding (Minlan)
  * Reading: [PyTorch FSDP: Experiences on Scaling Fully Sharded Data Parallel](https://arxiv.org/pdf/2304.11277.pdf)
  * Optional reading: [Meta blog post](https://engineering.fb.com/2021/07/15/open-source/fsdp/)
- 9/12 Th: Model Parallelism and Pipelining 
  * Reading: [PipeDream: Generalized Pipeline Parallelism for DNN Training](https://cs.stanford.edu/~matei/papers/2019/sosp_pipedream.pdf)
  * Optional reading: [GPipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism](https://proceedings.neurips.cc/paper/2019/file/093f65e080a295f8076b1c5722a46aa2-Paper.pdf)
- 9/17 Tu: Parameter Server vs All Reduce 
  * Reading: [A Unified Architecture for Accelerating Distributed DNN Training in Heterogeneous GPU/CPU Clusters](https://www.usenix.org/system/files/osdi20-jiang.pdf)
- 9/19 Th: NCCL optimizations
  * Reading: [Rethinking Machine Learning Collective Communication as a Multi-Commodity Flow Problem](https://www.sivak.dev/assets/pdf/sigcomm24_teccl.pdf)
  * Optional Reading: [GC3: An Optimizing Compiler for GPU Collective Communication](https://arxiv.org/pdf/2201.11840)


### Large language models
- 9/24 Tu: LLM training 
  * Reading: [Efficient Large-Scale Language Model Training on GPU Clusters Using Megatron-LM](https://arxiv.org/pdf/2104.04473.pdf)
  * Optional Reading: [ZeRO-Infinity: Breaking the GPU Memory Wall for Extreme Scale Deep Learning](https://ieeexplore.ieee.org/abstract/document/9355301)
- 9/26 Th: LLM serving
  * Reading: [Efficient Memory Management for Large Language Model Serving with PagedAttention](https://arxiv.org/pdf/2309.06180)
- 10/1 Tu: TF's tutorial on training systems
- 10/3 Th: Course project pitch presentation
- 10/8 Tu: Throughput-latency tradeoffs
  * Reading: [Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve](https://www.usenix.org/system/files/osdi24-agrawal.pdf)
- 10/10 Th: Distributed serving
  * Reading: [DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving](https://www.usenix.org/system/files/osdi24-zhong-yinmin.pdf)

### Network optimizations
- 10/15 Tu: NCCL as a service
  * Reading: [MCCS: A Service-based Approach to Collective Communication for Multi-Tenant Cloud](https://www.yongjiwu.me/assets/pdf/sigcomm24-mccs.pdf)
- 10/17 Th: Flow scheduling
  * Reading: [Crux: GPU-Efficient Communication Scheduling for Deep Learning Training](https://dl.acm.org/doi/pdf/10.1145/3651890.3672239)
- 10/22 Tu: RDMA 
  * Reading: [RDMA over Ethernet for Distributed AI Training at Meta Scale](https://dl.acm.org/doi/pdf/10.1145/3651890.3672233)

<!-- - Compression
  * Reading: [HiSpeed DNN Training with Espresso: Unleashing the Full Potential of Gradient Compression with Near-Optimal Usage Strategies](https://www.cs.rice.edu/~eugeneng/papers/EuroSys23.pdf) -->

<!-- * Optional reading: [NCCL communication primitives](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/overview.html), [Tree-based NCCL](https://developer.nvidia.com/blog/massively-scale-deep-learning-training-nccl-2-4/) -->

<!--
Memory-communication tradeoffs
  * Reading: [ZeRO: Memory Optimizations Toward Training Trillion Parameter Models](https://arxiv.org/pdf/1910.02054.pdf)
Flow and network scheduling (Aayush Karan, Jared Ni, Victor Goncalves)
  * Reading: [Cassini: Network-Aware Job Scheduling in Machine Learning Clusters](https://arxiv.org/pdf/2308.00852.pdf)
  * Optional Reading: [Efficient Flow Scheduling in Distributed Deep Learning Training with Echelon Formation](https://conferences.sigcomm.org/hotnets/2022/papers/hotnets22_pan.pdf)
-->

### Reliability
- 10/24 Th: Checkpointing 
  * Reading: [Gemini: Fast failure recovery in distributed training with in-memory checkpoints](https://assets.amazon.science/29/31/6523473f48e4af52252bac56ef51/gemini-fast-failure-recovery-in-distributed-training-with-in-memory-checkpoints.pdf)
  * Optional reading: [Check-N-Run: a Checkpointing System for Training Deep Learning Recommendation Models](https://www.usenix.org/system/files/nsdi22-paper-eisenman.pdf)
- 10/29 Tu: Ethics
- 10/31 Th: Fault tolerance 
  * Reading: [Oobleck: Resilient Distributed Training of Large Models Using Pipeline Templates](https://xinjin.github.io/files/SOSP23_Oobleck.pdf)
  * Optional reading: [SlipStream: Adapting Pipelines for Distributed Training of Large DNNs Amid Failures](https://arxiv.org/abs/2405.14009)
- 11/5 Tu: Diagnosis
  * Reading: [Cloud Atlas: Efficient Fault Localization for Cloud Systems using Language Models and Causal Insight](https://arxiv.org/pdf/2407.08694)
  * Optional Reading: bytedance paper

### End-to-end ML workflow
Data ingestion 
  * Reading: [Understanding data storage and ingestion for large-scale deep recommendation model training](https://dl.acm.org/doi/pdf/10.1145/3470496.3533044?casa_token=hgqFSo4RkdIAAAAA:ADj2kpsgPUEjftbV54blNpO_98zhNTM675gjwsQ8uw7rDJcFeSRx99bIuEB-_H4Q1E4JPxfHPsJK)
  * Optional Reading: [RecD: Deduplication for End-to-End Deep Learning Recommendation Model Training Infrastructure](https://arxiv.org/abs/2211.05239)

 
- 11/5 Tu: Automated parallelism 
  * Reading: [Alpa: Automating Inter- and Intra-Operator Parallelism for Distributed Deep Learning](https://arxiv.org/pdf/2201.12023.pdf)
- 11/7 Th: LLM training in Production
  * Reading: [MegaScale: Scaling Large Language Model Training to More Than 10,000 GPUs](https://www.usenix.org/system/files/nsdi24-jiang-ziheng.pdf)
  * Optional reading: [The Llama 3 Herd of Models](https://arxiv.org/pdf/2407.21783#page=64.50)
- 11/12 Tu: Carbon cost for ML (invited talk from Carole-Jean Wu, Meta)



### Hardware
- 11/14 Th: TPU 
  * Reading: [Resiliency at Scale: Managing Google’s
TPUv4 Machine Learning Supercomputer](https://www.usenix.org/system/files/nsdi24-zu.pdf)
  * optional Reading: [TPU v4: An Optically Reconfigurable Supercomputer for Machine Learning with Hardware Support for Embeddings](https://arxiv.org/pdf/2304.01433.pdf)
- 11/19 Tu: 
- 11/21 Th: In-network aggregation 
  * Reading: [ATP: In-network Aggregation for Multi-tenant Learning](https://www.usenix.org/system/files/nsdi21-lao.pdf)
  * Optional reading: [Scalable Hierarchical Aggregation and Reduction Protocol (SHARP)TM Streaming-Aggregation Hardware Design and Evaluation](https://network.nvidia.com/sites/default/files/related-docs/solutions/hpc/paperieee_copyright.pdf)


<!-- ## ML in the wild
- Federated learning 
  * Reading: [Oort: Efficient Federated Learning via Guided Participant Selection](https://www.mosharaf.com/wp-content/uploads/oort-osdi21.pdf)
- Sky computing 
  * Reading: [SkyPilot: An Intercloud Broker for Sky Computing](https://www.usenix.org/conference/nsdi23/presentation/yang-zongheng)
  * Optional reading: [From Cloud Computing to Sky Computing](https://sigops.org/s/conferences/hotos/2021/papers/hotos21-s02-stoica.pdf) -->
- 11/26 Tu: Final project presentation (batch I)

## Wrapping up
- 11/28 Th: no class: Thanksgiving 
- 12/3 Tu: Final project presentation (batch II)
- 12/11 Final Project Deadline (updated based on school examination group and dates)

## Reviews
- The goal of the reviews is to help you become comfortable reading research papers in networking and systems.
- Students are expected to write reviews for the papers discussed in each class. Scores will be based on the top 90% of the reviews, meaning it is acceptable to miss THREE reviews throughout the course.
- Reviews are due by noon one day before class (Monday noon for Tuesday classes; Wednesday noon for Thursday classes). This allows the presenter to collect all your questions for class discussion. For lectures with guest speakers, the TF will collect the questions. Please raise your questions during class.
- Reviews submitted within a week after the deadline only get half of the scores. All reviews submitted later than that do not get any scores.
- Detailed review questions are available in HotCRP. Each paper may have a specific question in addition to the general review questions.

## Class Presentation
- The goal of the presentation and in-class discussion is to learn how to form your own opinions about a paper.
- Depending on the number of students, each student will give one to three talks during the course.
- The speaker should send their slides to me three days before the presentation. In class, we expect you to know all the details of the paper and be able to answer questions during the discussion. If you have any questions about the paper, feel free to reach out to me before the class.
- Some authors share slides online, and some conferences share conference talk videos. You are encouraged to check out these resources or reuse them for your presentation with clear citations. However, be aware that conference talks are often short and focus more on the motivation rather than the technical details. They may also highlight only the benefits of their approaches (Everyone likes his own work). So, if you reuse the slides, please add more technical details, ensure you understand the content thoroughly, and share your own opinions of the work (not just the authors').

### Presentation format
- The presentation should cover the major content of the paper, including motivation (what problem the paper is solving; why this problem wasn't solved before), challenges (why this problem is difficult to solve), system design (how the authors address the challenges), evaluation (does it demonstrate that the problems/challenges are solved?), and your personal opinions of the paper.
- The talk should be around 45-50 minutes, excluding the review questions and discussions. This is longer than a normal conference talk to allow for more context on problem settings and detailed system design.
- Additionally, read all the reviews submitted by your classmates, list their questions in your slides, and lead the discussion of these questions in class.
- Be prepared to answer detailed questions about the paper during the discussion.
- The presentation will be graded based on both content (your understanding of the paper) and presentation (your delivery of the knowledge).

## Projects
The semester-long project is an open-ended systems research project. Project topics are of your choice but should be related to networking. Projects should be done in groups of two or three and include a systems building component. Selected projects can be submitted as peer-reviewed workshop papers or posters.

### Project Timeline
- 9/8 Sun at noon: Form groups for course projects
- 9/22 Sun at noon: Course project proposal
- 9/23-27: Schedule individual meetings with Minlan to get feedback on your project proposal
- 10/3 Th: Course project pitch presentation
- 11/3 Sun at noon: Midterm project report due at noon
- 11/4-8: Schedule individual meetings with Minlan to get feedback on your midterm report
- 11/24 Tu, 12/3 Tu: Final project presentation
- 12/11 Final project due at noon
- 12/12 Review of other students' project due at noon

### Project Proposal
The project proposal serves as a checkpoint, providing a basis for your individual meetings with Minlan and for your pitch presentations.
**You will receive the full 1% grade if you submit your proposal on time.** Unfortunately, late submissions will not be accepted, and there is no opportunity to make up the grade. After submission, you can keep updating your proposal and bring your latest one to your meeting with Minlan.

### Project pitch presentation
Each group should deliver a 5-minute talk on their project ideas. Be mindful about the scope of your project to ensure it can be completed by your team within two and a half months.
The presentation should include the following points (one slide per question):
- What problem are you solving? 
- Why is it an important problem? 
- What potential challenges might you face in solving the problem?
- What is your plan for the midterm report and division of work within the team?

**Your grade depend on how concrete your problem and execution plan are** 

### Midterm Project Report
The midterm report should be about 2-4 pages and serve as a starting point for your final project report (see detailed requirements for the final report below) **To achieve a high score for your midterm report, it is important to deliver an initial evaluation of your system.** You don't need to complete the entire system; instead, focus on identifying the most critical component/question in your project and provide an initial quantitative evaluation. The midterm report should include the following:
- Describe the problem you plan to solve, why it is novel/unique, and the major challenges (similar to your project pitch presentation, but feel free to adapt it based on your new understanding of the problem).
- Describe the detailed design of your project and what you have implemented/evaluated so far.
- Provide one evaluation figure about your initial system (This will be the focus of your meeting with Minlan)
- Discuss the remaining challenges, how you plan to address them, and your plan for the remaining time.

### Final project presentations
This presentation should resemble a workshop talk. You might consider covering the following content (not necessarily in the same order):
- What problem are you solving?
- Why is it an important problem?
- What is your basic solution to the problem?
- What are the challenges in the problem?
- How did you solve these challenges? Or how do you plan to solve them?
- Your preliminary evaluation results
- What do you plan to improve for the final report?


### Final Project Report
The report should be similar in spirit to a workshop paper, spanning six pages of double-column, single-spaced, 10-point font, excluding references. Here is an example LaTeX framework for formatting and building your paper. As shown in the framework, you may consider the following sections for your report (adapted from Eddie's version):

- Title: Something grabby that correctly describes a part of the contribution.
- Abstract: A paragraph or two that concisely describes the motivation for the work (the problem addressed), the contribution of the work, and a highlight of your results.
- Introduction: The introduction often covers the following questions: what problem are you trying to solve? Why is your problem important? What are the key challenges in solving your problem? What are your high-level ideas for addressing these challenges? What are your key design/system architecture? What are your key findings and evaluation results?
- Design: Start with the high-level architecture of your system, and then describe the details of your design in enough relevant detail that a skilled system builder could replicate your work. Compare your design choices with alternative approaches to explain why you designed your system this way.
- Evaluation: For systems work, this often includes the following subsections: (1) Experimental setup: Describe how you ran your experiments. What kinds of machine? How much memory? How many trials? How did you prepare the machine before each trial? (2) The experiments themselves, grouped by purpose. Include figures. (3) A summary of the experimental results. Some good evaluations are organized around performance hypotheses: statements that the experiments aim to support or disprove. It is important to discuss the implications of your observed results and why you see such results.
- Related work: Describe related research, especially research closely related to your work. This section serves to provide citations and comparisons. For each group of citations, describe (1) the core idea, (2) what is complementary with your work, (3) what is more advanced than your work, and (4) what is advanced upon by your work. (2)–(4) are optional—some papers will be entirely complementary with or orthogonal to your work.
- Conclusion: Summarize your work and its contributions.

### Code submission
Together with the final report, you should submit the github link of your project code. No need for superb software engineering, but ideally the code should be accompanied by enough documentation that a motivated user could attempt to replicate your results. You will need to demonstrate your product to the TFs at the final office hours. 

### Grading
The first four milestones (initial proposal, pitch presentation, midterm report, final project presentations) are mainly graded based on how well you keep up with the project progress at each stage. You will also get feedback at these milestones on how to improve your projects. The final project will be graded based on: Motivation, Design, delivered system, and its evaluation. 

### Policy on ChatGPT and generative AI
ChatGPT and generative AI tools are in general not useful for this course assignments (reviews and project reports). The default is that such use is disallowed unless with the permission of the course staffs. Any such use must be appropriately acknowledged and cited. It is each student’s responsibility to assess the validity and applicability of any GAI output that is submitted; you bear the final responsibility. Violations of this policy will be considered academic misconduct. We draw your attention to the fact that different classes at Harvard could implement different AI policies, and it is the student’s responsibility to conform to expectations for each course. THere is also [Harvard guidelines for GAI tools](https://provost.harvard.edu/guidelines-using-chatgpt-and-other-generative-ai-tools-harvard). 

## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)

## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
