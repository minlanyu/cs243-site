# CS 243, Fall 2022: Advanced Computer Networks

## Overview

This is a graduate-level course on computer networks. Each year we select a subset of advanced topics in networked systems to showcase 
latest developments in networking and how networking plays a role in the end-to-end systems to support higher-level applications.

This year we will take machine learning as an example to study their needs for networking and the key challenges they bring to the network stack. The growth of machine learning applications is driven by system hardware and software advances. A new trend in machine learning is to build increasingly large models using large data sets from various sources for a wide range of tasks. For example, Google trains a large language model with 540-billion parameters on thousands of TPUs for a variety of complex language tasks. This trend brings new challenges to networked systems: We now need to build large-scale distributed systems across the network to process such large amount of data, training large models, and serving inference requests. In this course, we will study system challenges in machine learning and how to co-design networks and the other parts of the systems to meet the needs of machine learning applications. The course will include lectures, in-class presentations, paper discussions, and a research project.

- Instructor: Minlan Yu
- Lecture time: MW 1:30pm-2:45pm
- Location: 
- Office hour: W 12:30-1:30, SEC 4.415
- Prerequisite: This course has no prerequisites. Since this course will focus on reading papers on latest topics in networking, you will need to be able to pick up the relevant background for each topic from textbooks or online materials.
- Recommended prep: system programming at the level of CS 61 or CS 143 or CS 145.


## Textbook
There are no required textbooks for the course. You will read papers before each class to get the most out of the class. For backgrounds, you are encouraged to refer to the following books:
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find [an online version](https://proquest-safaribooksonline-com.ezp-prod1.hul.harvard.edu/9780123850591) in Harvard library.
- Please contact me if some concepts are hard to understand and I'll provide more supplemental materials.

## Coursework and Grading
- Assignment: 10%
- Project: 50%
- Reviews: 30%
- Class presentation: 10%
Please see detailed requirements after the syllabus

## Syllabus

### Introduction
- 8/31 Wed: Introduction  
  * Reading 1: [A Berkeley View of Systems Challenges for AI](https://arxiv.org/pdf/1712.05855.pdf)
  * Reading 2: [How to Read a Paper](https://www.cs.princeton.edu/courses/archive/fall13/cos597E/papers/howtoread.pdf)
- 9/5 Mon: no class (labor day)

### Communication frameworks and Parallelism
- 9/7 Wed: Parameter Server
  * Reading: Scaling Distributed Machine Learning with the Parameter Server (https://www.cs.cmu.edu/~muli/file/parameter_server_osdi14.pdf)
- 9/12 Mon: BytePS
  * Reading: [A Unified Architecture for Accelerating Distributed DNN Training in Heterogeneous GPU/CPU Clusters](https://www.usenix.org/system/files/osdi20-jiang.pdf)
- 9/14 Wed: Data parallelism
  * Reading: [PyTorch Distributed: Experiences on Accelerating Data Parallel Training](https://arxiv.org/pdf/2006.15704.pdf)
  * Optional reading: [NCCL communication primitives](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/overview.html), [Tree-based NCCL](https://developer.nvidia.com/blog/massively-scale-deep-learning-training-nccl-2-4/)
- 9/19 Mon: Optimizing AllReduce
  * 
- 9/21 Wed: Pipeline parallelism
  * Reading: [PipeDream: Generalized Pipeline Parallelism for DNN Training](https://cs.stanford.edu/~matei/papers/2019/sosp_pipedream.pdf)
  * Optional reading: [GPipe: Efficient Training of Giant Neural Networks using Pipeline Parallelism](https://proceedings.neurips.cc/paper/2019/file/093f65e080a295f8076b1c5722a46aa2-Paper.pdf)
- 9/26 Mon: Compression
  * Reading: [Gradient Compression Supercharged High-Performance Data Parallel DNN Training](https://www.ruichuan.org/papers/hipress-sosp21.pdf)
- 9/28 Wed: Course project discussion

### Programming frameworks
- 10/3 Mon: Spark
  * Reading: [Discretized Streams: Fault-Tolerant Streaming Computation at Scale](https://pages.cs.wisc.edu/~shivaram/cs744-readings/dstreams.pdf)
- 10/5 Wed: Ray
  * Reading: [Ray: A Distributed Framework for Emerging AI Applications](https://www.usenix.org/system/files/osdi18-moritz.pdf)
  * Optional reading: [Data-Parallel Actors: A Programming Model for Scalable Query Serving Systems](https://cs.stanford.edu/~matei/papers/2022/nsdi_uniserve.pdf)
- : Graph processing
  * Reading: [GraphX: Graph Processing in a Distributed Dataflow Framework](https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-gonzalez.pdf)
  * Optional reading: [Scalability! But at what COST?](https://www.usenix.org/system/files/conference/hotos15/hotos15-paper-mcsherry.pdf)

### Inferences
- 10/10 Mon: Serving systems
  * Reading: [Clipper: A Low-Latency Online Prediction Serving System](https://www.usenix.org/system/files/conference/nsdi17/nsdi17-crankshaw.pdf)
  * Optional reading: [Serving DNNs like Clockwork: Performance Predictability from the Bottom Up](https://www.usenix.org/system/files/osdi20-gujarati.pdf)
- 10/12 Wed: Course project pitchtes
- 10/17 Mon: Video queries
  * Reading: [Nexus: A GPU Cluster Engine for Accelerating DNN-Based Video Analysis](https://homes.cs.washington.edu/~arvind/papers/nexus.pdf)
  * Optional reading: [Focus: Querying Large Video Datasets with Low Latency and Low Cost](https://web.eecs.umich.edu/~mosharaf/Readings/Focus.pdf)
  
### Accelerating ML
- 10/19 Wed: Programmable switches
  * Reading: [ATP: In-network Aggregation for Multi-tenant Learning](https://www.usenix.org/system/files/nsdi21-lao.pdf)
  * Optional: [Scaling Distributed Machine Learning with In-Network Aggregation](https://www.usenix.org/system/files/nsdi21-sapio.pdf)
- 10/24 Mon: FPGA
  * Reading: [Serving DNNs in Real Time at Datacenter Scale with Project Brainwave](https://web.eecs.umich.edu/~mosharaf/Readings/Brainwave.pdf) 
- 10/26 Wed: Optical networks
  * Reading: [SiP-ML: High-Bandwidth Optical Network Interconnects for Machine Learning Training](https://people.csail.mit.edu/ghobadi/papers/sipml_sigcomm_2021.pdf)
 
### Scheduling
- Workload
  * Reading: [Analysis of Large-Scale Multi-Tenant GPU Clusters for DNN Training Workloads](https://www.usenix.org/system/files/atc19-jeon.pdf)
- 10/31 Mon: Introspective scheduler
  * Reading: [Gandiva: Introspective Cluster Scheduling for Deep Learning](https://www.usenix.org/system/files/osdi18-xiao.pdf)
- 11/2 Wed: Network-aware scheduler
  * Reading: [THEMIS: Fair and Efficient GPU Cluster Scheduling](https://utns.cs.utexas.edu/papers/nsdi20-themis.pdf)
  * Optional: [Tiresias: A GPU Cluster Manager for Distributed Deep Learning](https://www.usenix.org/system/files/nsdi19-gu.pdf)
- 11/7 Mon: Scale-adaptive scheduler
  * Reading: [Pollux: Co-adaptive Cluster Scheduling for Goodput-Optimized Deep Learning](https://www.usenix.org/system/files/osdi21-qiao.pdf)
- 11/9 Wed:

### Learning in wide-area networks
- 11/14 Mon: 
  * Reading: [Gaia: Geo-Distributed Machine Learning Approaching LAN Speeds](https://www.usenix.org/system/files/conference/nsdi17/nsdi17-hsieh.pdf)
- 11/16 Wed:
- 11/21 Mon: Ethics: fairness in ML
  * Reading: 

### Wrapping up
- 11/23 Wed: no class (Thanksgiving break)
- 11/28 Mon: Project presentation
- 11/30 Wed: Project presentation
- 12/17 Project due date

## Reviews
- Students are expected to write reviews for the papers in each class. We will give scores based on the top 90\% of the reviews. This means it is ok if you miss 10\% of the reviews throughout the class.
- Your reviews are due at noon one day before (Sunday noon for Monday classes; Tuesday noon for Wed classes). So the presenter of the paper can have more time collect all your questions and we can discuss in class. For the lectures we have guest speakers, the TF will collect the questions and please raise your question in class.
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
The semester-long project is an open-ended systems research project. Project topics are of your choice but should be related to networking. Projects should be done in groups of two or three and include a systems building component. From my previous experiences, a significant portion of the final projects end up as published workshop papers. At the end of the semester, I'll suggest a few places for you to submit your course work to a real workshop! Or you may continue to work on it to make it a conference paper.

### Project Timeline
- 9/23 Fri: Warm-up assignments due
- 9/30 Fri: Form groups for course projects
- 10/7 Fri: Course project proposal due
- 10/12 Wed: Course project pitch presentation
- 11/04 Fri: Midterm project report
- 11/28 Mon, 11/30 Wed: Final project presentation
- 12/17 Final project due
- 12/19 Review of other students' project due

### Project Proposal presentation
Each group should give a 10-minute talk on your project ideas. The talk should include - What problem are you solving? - Why it's an important problem? - What are the potential challenges you may face in solving the problem? - What are the first steps (your plan for the next month)?

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
We will apply for AWS EC2 credits for the class. Please contact me if you need credits.
You might also consider public testbed such as [CloudLab](https://www.cloudlab.us/)

## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)

## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
