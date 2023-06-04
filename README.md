# CS 243, Fall 2023: Advanced Computer Networks

## Overview

This is a graduate-level course on computer networks. This course offers an in-depth exploration of a subset of advanced topics in networked systems. We will discuss the latest developments in the entire networking stack, the interactions between networks and high-level applications, and their connections with other system components such as compute and storage.

In this year's edition, we will use machine learning as a prime example to understand its unique requirements and challenges in the context of networking. As machine learning applications increasingly rely on larger models and faster accelerators, the demand for enhanced networking capabilities becomes imperative. Throughout this course, we will study cutting edge networking solutions and principles for  co-designing networks with compute and storage, to meet the evolving needs of machine learning applications. The course will include lectures, in-class presentations, paper discussions, and a research project.

- Instructor: Minlan Yu
- Lecture time: MW 11:15am to 12:30pm
- Location: SEC 1.402
- Office hour: W 10-11am, SEC 4.415
- Teaching fellows: Zhiying Xu (zhiyingxu@g.harvard.edu); Kevin Xu (kxu@college.harvard.edu)
- Prerequisite: This course has no prerequisites. Since this course will focus on reading papers on latest topics in networking, you will need to be able to pick up the relevant background for each topic from textbooks or online materials.
- Recommended prep: system programming at the level of CS 61 or CS 143 or CS 145.


## Textbook
There are no required textbooks for the course. You will read papers before each class to get the most out of the class. For backgrounds, you are encouraged to refer to the following books:
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find an online version [here](https://book.systemsapproach.org/).
- Please contact me if some concepts are hard to understand and I'll provide more supplemental materials.

## Coursework and Grading
- Project: 50% (5% initial project presentation, 5% mid-term report, 5% final project presentation, 35% final report and code)
- Reviews: 35%
- Class presentation: 10%
- Class participation: 5% (including class attendance, in-class discussion, and online discussion on Ed)

Please see detailed requirements after the syllabus

## Syllabus

### Introduction
- 9/5 Tu: Introduction (Minlan)
  * Reading 1: [Applied Machine Learning at Facebook: A Datacenter Infrastructure Perspective](https://research.facebook.com/file/904032783795098/hpca-2018-facebook.pdf)
  * Reading 2: [How to Read a Paper](https://www.cs.princeton.edu/courses/archive/fall13/cos597E/papers/howtoread.pdf)
  * Optional reading: [MLSys: The New Frontier of Machine Learning Systems](https://arxiv.org/pdf/1904.03257.pdf)
  * Optional reading: [A Berkeley View of Systems Challenges for AI](https://arxiv.org/pdf/1712.05855.pdf)
- 9/7 Th: Application: Neural network strucutures; various parallelism schemes (Minlan)
- 9/12 Tu: Hardware: Popular hardware; Network Techniques; Trends (Minlan)
- 9/14 Th: Project ideas

### Parallelism Schemes
- Data Parallellism and Sharding
  * Reading: [PyTorch FSDP: Experiences on Scaling Fully Sharded Data
Parallel](https://arxiv.org/pdf/2304.11277.pdf)
  * Optional reading: [Meta blog post](https://engineering.fb.com/2021/07/15/open-source/fsdp/)
- 9/19 Tu: Model Parallelism and Pipelining
  * Reading: [PipeDream: Generalized Pipeline Parallelism for DNN Training](https://cs.stanford.edu/~matei/papers/2019/sosp_pipedream.pdf)
  * Optional reading: [GPipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism](https://proceedings.neurips.cc/paper/2019/file/093f65e080a295f8076b1c5722a46aa2-Paper.pdf)
- 9/21 Th: Tensor Parallelism
  * Reading: [Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism](https://arxiv.org/pdf/1909.08053.pdf)* 
- 9/26 Tu: Automated parallelism
  * Reading: [Alpa: Automating Inter- and Intra-Operator Parallelism for Distributed Deep Learning](https://arxiv.org/pdf/2201.12023.pdf)
  * Optional reading: [Efficient Large-Scale Language Model Training on GPU Clusters Using Megatron-LM](https://cs.stanford.edu/~matei/papers/2021/sc_megatron_lm.pdf)
- 9/28 Th: 

### Communication Schemes
- 10/3 Tu: Parameter Server 
  * Reading: [A Unified Architecture for Accelerating Distributed DNN Training in Heterogeneous GPU/CPU Clusters](https://www.usenix.org/system/files/osdi20-jiang.pdf)
  * Optional reading: [Scaling Distributed Machine Learning with the Parameter Server](https://www.cs.cmu.edu/~muli/file/parameter_server_osdi14.pdf)
- 10/5 Th: All Reduce
  * Optional reading: [NCCL communication primitives](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/overview.html), [Tree-based NCCL](https://developer.nvidia.com/blog/massively-scale-deep-learning-training-nccl-2-4/)
- Memory-communication tradeoffs
  * Reading: [ZeRO: Memory Optimizations Toward Training Trillion Parameter Models](https://arxiv.org/pdf/1910.02054.pdf)

### End-to-end ML workflow
- 10/10 Tu: Data ingestion
  * Reading: [Understanding data storage and ingestion for large-scale deep recommendation model training](https://dl.acm.org/doi/pdf/10.1145/3470496.3533044?casa_token=hgqFSo4RkdIAAAAA:ADj2kpsgPUEjftbV54blNpO_98zhNTM675gjwsQ8uw7rDJcFeSRx99bIuEB-_H4Q1E4JPxfHPsJK)
- 10/12 Th: Course project pitch presentation
- 10/17 Tu: Preprocessing
  * Reading: [Where Is My Training Bottleneck? Hidden Trade-Offs in Deep Learning Preprocessing Pipelines](https://dl.acm.org/doi/pdf/10.1145/3514221.3517848?casa_token=0sDxMYVe-d8AAAAA:v1Zeh6kccJU9E4xa6fbd_Vy6wGuJfkqhGav9Dv02oPIF1xiLu8CL7tdXO0xiZ_63Eh3mbjwWHbd0)
- Embedding: Nvidia HugeCTR
  * Reading: [Blog1](https://developer.nvidia.com/blog/introducing-merlin-hugectr-training-framework-dedicated-to-recommender-systems/), [Blog2]()
- 10/19 Th: Checkpointing 
  * Reading: [Check-N-Run: a Checkpointing System for Training Deep Learning Recommendation Models](https://www.usenix.org/system/files/nsdi22-paper-eisenman.pdf)
  * Optional reading: [CheckFreq: Frequent, Fine-Grained DNN Checkpointing
](https://www.microsoft.com/en-us/research/publication/checkfreq-frequent-fine-grained-dnn-checkpointing/)
- 10/24 Tu: Fault Tolerance
- Energy saving
  * Reading: [Zeus: Understanding and Optimizing GPU Energy Consumption of DNN Training](https://www.usenix.org/system/files/nsdi23-you.pdf)


### Multi-tenancy
- Job scheduling


- 10/26 Th:
- 10/31 Tu:
- 11/2 Th:
- 11/7 Tu:
- 11/9 Th:
- 11/14 Tu:
- 11/16 Th:
- 11/21 Tu:
- 11/23 no class: Thanksgiving 
- 11/28 Tu: Ethics
- 11/30 Th: Project Presentation
- 12/5 Tu: Project Presentation
- 12/15 Final Project Deadline (Tentative)

### Hardware 
- TPU
  * Reading: [TPU v4: An Optically Reconfigurable Supercomputer for Machine Learning with Hardware Support for Embeddings](https://arxiv.org/pdf/2304.01433.pdf)
- Optical networks
  * Reading: [Jupiter Evolving: Transforming Google’s Datacenter Network via Optical Circuit Switches and
Software-Defined Networking](https://dl.acm.org/doi/pdf/10.1145/3544216.3544265)
  * Optional Reading: [TOPOOPT: Co-optimizing Network Topology and Parallelization Strategy for Distributed Training Jobs](https://people.csail.mit.edu/ghobadi/papers/topoOpt_nsdi_2023.pdf)
- 11/2 Wed: Programmable switches
  * Reading: [ATP: In-network Aggregation for Multi-tenant Learning](https://www.usenix.org/system/files/nsdi21-lao.pdf)
  * Optional reading: [Nvidia SHARP]()
- NvLink


### Other types of ML
- Federated learning
- 10/24 Mon: Ray (Joel Runevic, Jason Akoun)
  * Reading: [Hoplite: Efficient and Fault-Tolerant Collective Communication for Task-Based Distributed Systems](https://conferences.sigcomm.org/sigcomm/2021/files/papers/3452296.3472897.pdf)
  * Optional reading: [Ray: A Distributed Framework for Emerging AI Applications](https://www.usenix.org/system/files/osdi18-moritz.pdf)
- 10/26 Wed: Serving systems (Eric Tang, Andrew Sima)
  * Reading: [Clipper: A Low-Latency Online Prediction Serving System](https://www.usenix.org/system/files/conference/nsdi17/nsdi17-crankshaw.pdf)
  * Optional reading: [Serving DNNs like Clockwork: Performance Predictability from the Bottom Up](https://www.usenix.org/system/files/osdi20-gujarati.pdf)
- 10/31 Mon: Video queries (Wei-Te Ting, Spandan	Madan)
  * Reading: [Nexus: A GPU Cluster Engine for Accelerating DNN-Based Video Analysis](https://homes.cs.washington.edu/~arvind/papers/nexus.pdf)
  * Optional reading: [Focus: Querying Large Video Datasets with Low Latency and Low Cost](https://web.eecs.umich.edu/~mosharaf/Readings/Focus.pdf)

### Scheduler 
- 9/19 Mon: Communication scheduler (Jailyn Clark)
  * Reading: [A Generic Communication Scheduler for Distributed DNN Training Acceleration](http://yibozhu.com/doc/bytescheduler-sosp19.pdf) 
- 9/21 Wed: Network-aware job scheduler (Kidist Alemu, Dimitrije Pavlov) 
  * Reading: [THEMIS: Fair and Efficient GPU Cluster Scheduling](https://utns.cs.utexas.edu/papers/nsdi20-themis.pdf)
  * Optional: [Tiresias: A GPU Cluster Manager for Distributed Deep Learning](https://www.usenix.org/system/files/nsdi19-gu.pdf)
- 9/26 Mon: Course project discussion 
- 9/28 Wed: Co-flow (Jeff Jiang, Hao	Wang)
  * Reading: [Sincronia: Near-Optimal Network Design for Coflows](https://www.cs.cornell.edu/~ragarwal/pubs/sincronia.pdf)

### Optimizing communication 
- 10/3 Mon: Multicast (Vic Feng, Joshua Michels)
  * Reading: [Elmo: Source Routed Multicast for Public Clouds](https://gitlab.com/mshahbaz/mshahbaz.gitlab.io/-/raw/master/publications/sigcomm19-elmo.pdf)
  * Reading 2: Read Sec 5.1 in [Orca: Server-assisted Multicast for Datacenter Networks](https://www.usenix.org/system/files/nsdi22-paper-diab_orca.pdf)
- 10/5 Wed: Sparsity (Harrison Termotto, Emil	Ghitman Gilkes)
  * Reading: [Efficient Sparse Collective Communication and its application to Accelerate Distributed Deep Learning](https://conferences.sigcomm.org/sigcomm/2021/files/papers/3452296.3472904.pdf)
- 10/10 Mon: No class (University holiday)
- 10/12 Wed: Compression (Xinran Tang, Minghao Li) (Led by TF) 
  * Reading: [Gradient Compression Supercharged High-Performance Data Parallel DNN Training](https://www.ruichuan.org/papers/hipress-sosp21.pdf)
- 10/17 Mon: Course project pitches
- 10/19 Wed: Congestion control (Chris Zhu, Eric Zhang)
  * Reading: [HPCC: High Precision Congestion Control](https://minlanyu.seas.harvard.edu/writeup/sigcomm19.pdf)

### Heterageneous devices
- 11/9 Wed: CPUs (Daniel Son, William Cooper)
  * Reading: [Dorylus: Affordable, Scalable, and Accurate GNN Training over Billion-Edge Graphs](https://web.cs.ucla.edu/~harryxu/papers/dorylus-osdi21.pdf)
 
- Ethics: System impact on fairness in ML


### Other topics
- 11/21 Mon: Sky computing (Yuji Chai, Luke Bailey, Richard Lun)
  * Reading: [The Sky Above The Clouds](https://arxiv.org/pdf/2205.07147.pdf)

### Wrapping up
- 11/23 Wed: no class (Thanksgiving break)
- 11/28 Mon: Project presentation
- 11/30 Wed: Project presentation

## Reviews
- Students are expected to write reviews for the papers in each class. We will give scores based on the top 90\% of the reviews. This means it is ok if you miss 10\% of the reviews throughout the class.
- Your reviews are due at noon one day before (Monday noon for Tuesday classes; Wednesday noon for Thursday classes). So the presenter of the paper can have time collect all your questions and we can discuss in class. For the lectures we have guest speakers, the TF will collect the questions and please raise your question in class.
- The goal of the reviews is to get you comfortable of reading research papers in networking

### Review format
- Paper summary
- What are the paper’s strengths? Just a couple of sentences, please.
- What are the paper’s areas for improvement? Just a couple of sentences, please.
- Any thoughts or questions that you hope to discuss in class?
- Other comments about the paper
- Paper-specific question: We will post one question for each paper that you are supposed to answer in your review

## Class Presentation
- Depending on the number of students, each student will give one to three talks in this class.
- The speaker should send your slides to me 3 days before the presentation. In the class, we expect you to know all the details of the paper and be able to answer our questions about the paper during the in-class discussion. If you have any questions about the paper, you can reach out to me to discuss it before the class.
- Some authors share slides online; Some conferences share conference talk videos online. You are encouraged to check out those slides/videos or reuse some for your presentation. However, please be aware that conference talks are often short and focuses more on the motivation rather than the technical details. They may also be biased in highlighting only the benefits of their approaches (everyone likes his own work). So if you reuse the slides, please add more technical details (make sure you really understand what's going on in detail), and share your own opinion of the work (not just the authors').
- The goal of the presentation and in-class discussion is to learn how to form your own opinions of a paper.

### Presentation format
- The presentation is supposed to cover the major content of the paper such as motivation (what problem the paper is solving; why is this problem not solved before), challenges (why is this problem difficult to solve), system design (how the authors address the challenges), Evaluation (Does it demonstrate that the problems/challenges are solved?), and your personal opinions of the paper.
- The talk is supposed to be longer than a normal conference talk because we want to extend on problem formulation (give more context on problem setting) and detailed system design.
- In addition, please read all the reviews submitted by your classmates and list their questions in the slides. And lead the discussions of these questions in class.

## Projects
The semester-long project is an open-ended systems research project. Project topics are of your choice but should be related to networking. Projects should be done in groups of two or three and include a systems building component. Selected projects can be submitted to a peer-reviewed workshop papers or posters.

### Project Timeline
- 9/17 Sun at noon: Form groups for course projects
- 10/1 Sun at noon: Course project proposal
- 10/2-6: Schedule individual meetings with Minlan to get feedback on your project proposal
- 10/12 Th: Course project pitch presentation
- 11/5 Sun at noon: Midterm project report due at noon
- 11/6-10: Schedule individual meetings with Minlan to get feedback on your midterm report
- 11/28 Tu, 11/30 Th: Final project presentation
- 12/11 Final project due at noon
- 12/12 Review of other students' project due at noon

### Project Proposal presentation
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
Together with the final report, you should submit the github link of your project code. No need for superb software engineering, but ideally the code should be accompanied by enough documentation that a motivated user could attempt to replicate your results.

### Evaluation Testbed
- We will apply for AWS EC2 credits for the class. Please contact me if you need credits.
- You might also consider public testbed such as [CloudLab](https://www.cloudlab.us/)

## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)

## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
