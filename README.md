# CS 243, Fall 2023: Advanced Computer Networks

## Overview

This is a graduate-level course on computer networks. This course offers an in-depth exploration of a subset of advanced topics in networked systems. We will discuss the latest developments in the entire networking stack, the interactions between networks and high-level applications, and their connections with other system components such as compute and storage.

In this year's edition, we will use machine learning as a prime example to understand its unique requirements and challenges in the context of networking. As machine learning applications increasingly rely on larger models and faster accelerators, the demand for enhanced networking capabilities becomes imperative. Throughout this course, we will study cutting edge networking solutions and principles for  co-designing networks with compute and storage, to meet the evolving needs of machine learning applications. The course will include lectures, in-class presentations, paper discussions, and a research project.

- Instructor: Minlan Yu
- Lecture time: TuTh 11:15am to 12:30pm
- Location: SEC 1.402
- Office hour: Tu 10-11am, SEC 4.415
- Teaching fellows: Weifan Jiang (weifanjiang@g.harvard.edu); Mark Ting (weiteting@g.harvard.edu) 
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
- Project: 50% (5% initial project presentation, 5% mid-term report, 5% final project presentation, 35% final report and code)
- Reviews: 35%
- Class presentation: 10%
- Class participation: 5% (including class attendance, in-class discussion, and online discussion on Ed)

Please see detailed requirements after the syllabus

## Syllabus

This field is moving so fast. A majority of papers we read this year is new compared to last year. 

### Introduction
- 9/5 Tu: Introduction (Minlan)
  * Reading 1: [Applied Machine Learning at Facebook: A Datacenter Infrastructure Perspective](https://research.facebook.com/file/904032783795098/hpca-2018-facebook.pdf)
  * Reading 2: [How to Read a Paper](https://www.cs.princeton.edu/courses/archive/fall13/cos597E/papers/howtoread.pdf)
  * Optional reading: [MLSys: The New Frontier of Machine Learning Systems](https://arxiv.org/pdf/1904.03257.pdf)
  * Optional reading: [A Berkeley View of Systems Challenges for AI](https://arxiv.org/pdf/1712.05855.pdf)
- 9/7 Th: Model trend and Hardware trend (Minlan)

### Parallelism Schemes
- 9/12 Tu: Warm up project and infrastructure setup (TFs will lead this class)
- 9/14 Th: Data Parallellism and Sharding (Guest lecture by Prof. Tushar Krishna and William Won)
  * Reading: [PyTorch FSDP: Experiences on Scaling Fully Sharded Data
Parallel](https://arxiv.org/pdf/2304.11277.pdf)
  * Optional reading: [Meta blog post](https://engineering.fb.com/2021/07/15/open-source/fsdp/)
- 9/19 Tu: Model Parallelism and Pipelining (Minlan)
  * Reading: [PipeDream: Generalized Pipeline Parallelism for DNN Training](https://cs.stanford.edu/~matei/papers/2019/sosp_pipedream.pdf)
  * Optional reading: [GPipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism](https://proceedings.neurips.cc/paper/2019/file/093f65e080a295f8076b1c5722a46aa2-Paper.pdf)
- 9/21 Th: Tensor Parallelism (Gareth Wu, Jessica Chen, Sahil Kuchlous)
  * Reading: [Efficient Large-Scale Language Model Training on GPU Clusters Using Megatron-LM](https://arxiv.org/pdf/2104.04473.pdf)
  * Optional Reading: [Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism](https://arxiv.org/pdf/1909.08053.pdf)* 
- 9/26 Tu: Automated parallelism (Sam DePaolo, Stephen Yang)
  * Reading: [Alpa: Automating Inter- and Intra-Operator Parallelism for Distributed Deep Learning](https://arxiv.org/pdf/2201.12023.pdf)

### Communication Schemes
- 9/28 Th: Parameter Server vs All Reduce (Safwan Hossain, Tonghan Wang)
  * Reading: [A Unified Architecture for Accelerating Distributed DNN Training in Heterogeneous GPU/CPU Clusters](https://www.usenix.org/system/files/osdi20-jiang.pdf)
  * Optional reading: [NCCL communication primitives](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/overview.html), [Tree-based NCCL](https://developer.nvidia.com/blog/massively-scale-deep-learning-training-nccl-2-4/)
- 10/3 Tu: Flow and network scheduling (Aayush Karan, Jared Ni, Victor Goncalves)
  * Reading: [Cassini: Network-Aware Job Scheduling in Machine Learning Clusters](https://arxiv.org/pdf/2308.00852.pdf)
  * Optional Reading: [Efficient Flow Scheduling in Distributed Deep Learning Training with Echelon Formation](https://conferences.sigcomm.org/hotnets/2022/papers/hotnets22_pan.pdf)
- 10/5 Th: Ethics: System impact on fairness in ML
  * Reading: [Advances and Open Problems in Federated Learning](https://arxiv.org/pdf/1912.04977.pdf) Only need to read Section 6 (page 75-80)
  * Optional reading: [Measuring Algorithmic Fairness](https://virginialawreview.org/wp-content/uploads/2020/06/Hellman_Book.pdf)
- 10/10 Tu: Compression (Hannah Zhou, Justin O'Dwyer, Nina Lei)
  * Reading: [HiSpeed DNN Training with Espresso: Unleashing the Full Potential of Gradient Compression with Near-Optimal Usage Strategies](https://www.cs.rice.edu/~eugeneng/papers/EuroSys23.pdf)
- 10/12 Th: Course project pitch presentation

<!--
Memory-communication tradeoffs
  * Reading: [ZeRO: Memory Optimizations Toward Training Trillion Parameter Models](https://arxiv.org/pdf/1910.02054.pdf)
-->
  
### End-to-end ML workflow
- 10/17 Tu: Data ingestion (Albert Qi, Alice Wu, Feiyang Huang)
  * Reading: [Understanding data storage and ingestion for large-scale deep recommendation model training](https://dl.acm.org/doi/pdf/10.1145/3470496.3533044?casa_token=hgqFSo4RkdIAAAAA:ADj2kpsgPUEjftbV54blNpO_98zhNTM675gjwsQ8uw7rDJcFeSRx99bIuEB-_H4Q1E4JPxfHPsJK)
- 10/19 Th: Checkpointing (Michal Kurek, Natnael Teshome, Nithya Gottipati)
  * Reading: [Check-N-Run: a Checkpointing System for Training Deep Learning Recommendation Models](https://www.usenix.org/system/files/nsdi22-paper-eisenman.pdf)
  * Optional reading: [CheckFreq: Frequent, Fine-Grained DNN Checkpointing
](https://www.microsoft.com/en-us/research/publication/checkfreq-frequent-fine-grained-dnn-checkpointing/)
- 10/24 Tu: Preprocessing (Cameron Wong, Dalila Oliva, Shirley Zhang)
  * Reading: [Where Is My Training Bottleneck? Hidden Trade-Offs in Deep Learning Preprocessing Pipelines](https://dl.acm.org/doi/pdf/10.1145/3514221.3517848?casa_token=0sDxMYVe-d8AAAAA:v1Zeh6kccJU9E4xa6fbd_Vy6wGuJfkqhGav9Dv02oPIF1xiLu8CL7tdXO0xiZ_63Eh3mbjwWHbd0)
  * Optional Reading: [FastFlow: Accelerating Deep Learning Model Training with Smart Offloading of Input Data Pipeline](https://www.vldb.org/pvldb/vol16/p1086-um.pdf)
- 10/26 Th: Energy saving (Daniela Shuman, Derek Hu, Yang Hu)
  * Reading: [Zeus: Understanding and Optimizing GPU Energy Consumption of DNN Training](https://www.usenix.org/system/files/nsdi23-you.pdf)
- 10/31 Tu: Job scheduling (Hannah Pierce-Hoffman, Kane Norman, Parita Shah)
  * Reading: [Looking Beyond GPUs for DNN Scheduling on Multi-Tenant Clusters](https://www.microsoft.com/en-us/research/uploads/prod/2022/03/osdi22-fiddle-synergy.pdf)


### Hardware
- 11/2 Th: TPU
  * Reading: [TPU v4: An Optically Reconfigurable Supercomputer for Machine Learning with Hardware Support for Embeddings](https://arxiv.org/pdf/2304.01433.pdf)
- 11/7 Tu: Optical networks
  * Reading: [Jupiter Evolving: Transforming Google’s Datacenter Network via Optical Circuit Switches and
Software-Defined Networking](https://dl.acm.org/doi/pdf/10.1145/3544216.3544265)
  * Optional Reading: [TOPOOPT: Co-optimizing Network Topology and Parallelization Strategy for Distributed Training Jobs](https://people.csail.mit.edu/ghobadi/papers/topoOpt_nsdi_2023.pdf)
- 11/9 Th: Programmable switches
  * Reading: [ATP: In-network Aggregation for Multi-tenant Learning](https://www.usenix.org/system/files/nsdi21-lao.pdf)
  * Optional reading: [Scalable Hierarchical Aggregation and Reduction Protocol (SHARP)TM Streaming-Aggregation Hardware Design and Evaluation](https://network.nvidia.com/sites/default/files/related-docs/solutions/hpc/paperieee_copyright.pdf)
- 11/14 Tu: FPGA
  * Reading: [FAERY: An FPGA-accelerated Embedding-based Retrieval System](https://www.usenix.org/conference/osdi22/presentation/zeng)
  * Optional Reading: [Nvidia HugeCTR](https://developer.nvidia.com/blog/introducing-merlin-hugectr-training-framework-dedicated-to-recommender-systems/)

## Other types of ML
- 11/16 Th: Federated learning
  * Reading: [Oort: Efficient Federated Learning via Guided Participant Selection](https://www.mosharaf.com/wp-content/uploads/oort-osdi21.pdf)
- 11/21 Tu: Sky computing 
  * Reading: [SkyPilot: An Intercloud Broker for Sky Computing](https://www.usenix.org/conference/nsdi23/presentation/yang-zongheng)
  * Optional reading: [From Cloud Computing to Sky Computing](https://sigops.org/s/conferences/hotos/2021/papers/hotos21-s02-stoica.pdf)
- 11/23 no class: Thanksgiving 
- 11/28 Tu: Serving systems 
  * Reading: [Orca: A Distributed Serving System for Transformer-Based Generative Models](https://www.usenix.org/conference/osdi22/presentation/yu)
  * Optional reading: [Shepherd: Serving DNNs in the Wild](https://www.usenix.org/system/files/nsdi23-zhang-hong.pdf)

## Wrapping up
- 11/30 Th: Project Presentation
- 12/5 Tu: Project Presentation
- 12/11 Final Project Deadline (updated based on school examination group and dates)

## Reviews
- Students are expected to write reviews for the papers in each class. We will give scores based on the top 90\% of the reviews. This means it is ok if you miss 10\% of the reviews throughout the class.
- Your reviews are due at noon one day before (Monday noon for Tuesday classes; Wednesday noon for Thursday classes). So the presenter of the paper can have time collect all your questions and we can discuss in class. For the lectures we have guest speakers, the TF will collect the questions and please raise your question in class.
- The goal of the reviews is to get you comfortable of reading research papers in networking and systems
- Detailed review questions are in HotCRP. 

## Class Presentation
- Depending on the number of students, each student will give one to three talks in this class.
- The speaker should send your slides to me 3 days before the presentation. In the class, we expect you to know all the details of the paper and be able to answer our questions about the paper during the in-class discussion. If you have any questions about the paper, you can reach out to me to discuss it before the class.
- Some authors share slides online; Some conferences share conference talk videos online. You are encouraged to check out those slides/videos or reuse some for your presentation. However, please be aware that conference talks are often short and focuses more on the motivation rather than the technical details. They may also be biased in highlighting only the benefits of their approaches (everyone likes his own work). So if you reuse the slides, please add more technical details (make sure you really understand what's going on in detail), and share your own opinion of the work (not just the authors').
- The goal of the presentation and in-class discussion is to learn how to form your own opinions of a paper.

### Presentation format
- The presentation is supposed to cover the major content of the paper such as motivation (what problem the paper is solving; why is this problem not solved before), challenges (why is this problem difficult to solve), system design (how the authors address the challenges), Evaluation (Does it demonstrate that the problems/challenges are solved?), and your personal opinions of the paper.
- The talk should be around 45-50 minutes excluding the review questions and discussions. This is longer than a normal conference talk because we want to extend on problem formulation (with more context on problem setting) and detailed system design.
- In addition, please read all the reviews submitted by your classmates and list their questions in the slides. And lead the discussions of these questions in class.
- Please also be prepared answer detailed questions we may have on the paper during the discussion.
- The grading of the presentation will be based on both the content (your understanding of the papers) and presentation (your delivery of the knowledge).

## Projects
The semester-long project is an open-ended systems research project. Project topics are of your choice but should be related to networking. Projects should be done in groups of two or three and include a systems building component. Selected projects can be submitted to a peer-reviewed workshop papers or posters.

### Project Timeline
- 9/22 Fri at noon: Form groups for course projects
- 10/1 Sun at noon: Course project proposal
- 10/2-6: Schedule individual meetings with Minlan to get feedback on your project proposal
- 10/12 Th: Course project pitch presentation
- 11/5 Sun at noon: Midterm project report due at noon
- 11/6-10: Schedule individual meetings with Minlan to get feedback on your midterm report
- 11/28 Tu, 11/30 Th: Final project presentation
- 12/11 Final project due at noon
- 12/12 Review of other students' project due at noon

### Project Proposal and project pitch presentation
The project proposal is not graded but it serves as the good basis for your individual meeting with Minlan and for your pitch presentation. 
Each group should give a 5-minute talk on your project ideas. The talk should include 
- What problem are you solving? 
- Why it's an important problem? 
- What are the potential challenges you may face in solving the problem? 
- What are the first steps (your plan for the next month)?

### Midterm Project Report
- Describe the problem you plan to solve, why it is novel/unique, what the major challenges
- Describe the detailed design for your project and what you have implemented/evaluated so far
- Describe the remaining challenges, how you would address them, and your plan for the remaining time.
- The midterm report should be about 2-4 pages and serve as a starting point for your final project report (see detailed requirements for the final report below)

### Final project presentations
This should be similar to a workshop talk. You might consider covering the following content (not necessarily in the same order):
- What problem are you trying to solve?
- Why is it an important problem?
- What's your basic solution to the problem?
- What are the challenges in the problem?
- How did you solve these challenges? Or how do you plan to solve the challenges?
- Some preliminary results
- Future works

### Final Project Report
The report should be similar in spirit to a workshop paper, which is six pages of double-column, single-spaced, 10-point font, excluding references. Here's an example latex framework for formatting and building your paper. As shown in the framework, you may consider the following sections for your report: (adapted from Eddie's version)
- Title: Something grabby that correctly describes a part of the contribution.
- Abstract: A paragraph or two that concisely describes the motivation for the work (the problem the work addresses), the contribution of the work, and a highlight of your results.
- Introduction: The introduction often cover the following questions: what problem are you trying to solve? Why is your problem is important? What are the key challenges in solving your problem? What are your high-level ideas in addressing these challenges? What are your key design/system architecture? What are your key findings and evaluation results?
- Design: We typically start with the high-level architecture of your system, and then describe the details of your design, described in enough relevant detail that a skilled system builder could replicate your work. It is also important to compare your design choices with alternative approaches to give us reasons on why you design your system in this way.
- Evaluation: For systems work, this will often include the following subsections: (1) Experimental setup. Describe how you ran your experiments. What kinds of machine? How much memory? How many trials? How did you prepare the machine before each trial? (2) The experiments themselves, grouped by purpose. Include figures. (3) A summary of the experimental results. Some good evaluations are organized around performance hypotheses: statements that the experiments aim to support or disprove. It is important to discuss the implications of your results and why you see such results.
- Related work: A description of related research, especially research closely related to your own work. The purposes of this section are citation and comparison. Foundational work requires citation only; “Amazon Web Services introduced modern serverless computing with AWS Lambda in 2014 [19].” More recent work requires comparison. Describe for each group of citations (1) the core idea, (2) what is complementary with your work, (3) what is more advanced than your work, and (4) what is advanced upon by your work. (2)–(4) are optional—some papers will be entirely complementary with or orthogonal to your work. (Hopefully no work will be entirely more advanced than yours!)
- Conclusion: Summary of your work

### Code submission
Together with the final report, you should submit the github link of your project code. No need for superb software engineering, but ideally the code should be accompanied by enough documentation that a motivated user could attempt to replicate your results. You will need to demonstrate your product to the TFs at the final office hour. 

### Grading
The first three milestones (pitch presentation, midterm report, final project presentations) each take 5%. We will grade based on how much you are keeping up with the progress of the stages. You will also get feedback at these milestones on how to improve your projects. The final project will be graded based on: Motivation, Design, and delivered system and its evaluation. 

### Policy on ChatGPT and generative AI
ChatGPT and generative AI tools are in general not useful for this course assignments (reviews and project reports). The default is that such use is disallowed unless with the permission of the course staffs. Any such use must be appropriately acknowledged and cited. It is each student’s responsibility to assess the validity and applicability of any GAI output that is submitted; you bear the final responsibility. Violations of this policy will be considered academic misconduct. We draw your attention to the fact that different classes at Harvard could implement different AI policies, and it is the student’s responsibility to conform to expectations for each course. THere is also [Harvard guidelines for GAI tools](https://provost.harvard.edu/guidelines-using-chatgpt-and-other-generative-ai-tools-harvard). 

## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)

## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
