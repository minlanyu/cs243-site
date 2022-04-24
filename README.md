# CS 243, Fall 2022: Advanced Computer Networks

## Overview

This is a graduate-level course on computer networks. Each year we may cover a selected subset of advanced topics in network systems. The goal of this course is not to have the full coverage of networking concepts and protocols, but for you to learn the latest development in networking and how networking plays a role in the end-to-end systems and affect higher-level applications through case studies.

This year we will focus on networked systems for machine learning. Recent trend of machine learning is to use increasingly large models using large data sets from various sources for a wide range of tasks (e.g., Google trains a large language model with 540-billion parameters on thousands of TPUs for a variety of complex language tasks). This trend means that we need to build systems that process this large amount of data and support large models distributedly across the network. In this course, we will study recent advances and challenges of networked systems in supporting large-scale machine learning applications. The course will include lectures, in-class presentations, paper discussions, and a research project.

- Instructor: Minlan Yu
- Lecture time: MW 1:30pm-2:45pm
- Location: 
- Office hour: W 12:30-1:30, SEC 4.415
- Prerequisite: This course has no prerequisites. But since this course will cover advanced topics in networking and systems, you will need to be able to read textbooks and papers to pick up the relevant background for each topic.
- Recommended prep: system programming at the level of CS 61 or CS 143 or CS 145.


## Textbook
There are no required textbooks for the course. You will read papers before each class to get the most out of the class. For backgrounds, you are encouraged to refer to the following books:
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find [an online version](https://proquest-safaribooksonline-com.ezp-prod1.hul.harvard.edu/9780123850591) in Harvard library.
- Please contact me if some concepts are hard to understand and I'll provide more supplemental materials.

## Coursework and Grading
- Project: 50%
- Reviews: 30%
- Class presentation: 20%
Please see detailed requirements after the syllabus

## Syllabus

- 8/31 Wed: Introduction  
  * Readings: [Berkely view](https://arxiv.org/pdf/1712.05855.pdf), [How to read](https://www.cs.princeton.edu/courses/archive/fall13/cos597E/papers/howtoread.pdf)
- 9/5 Mon: no class (labor day)
- 9/7 Wed: 
- 9/12 Mon:
- 9/14 Wed:
- 9/19 Mon:
- 9/21 Wed:
- 9/26 Mon:
- 9/28 Wed:
- 10/3 Mon:
- 10/5 Wed:
- 10/10 Mon:
- 10/12 Wed:
- 10/17 Mon:
- 10/19 Wed:
- 10/24 Mon:
- 10/26 Wed:
- 10/31 Mon:
- 11/2 Wed:
- 11/7 Mon:
- 11/9 Wed:
- 11/14 Mon:
- 11/16 Wed:
- 11/21 Mon:
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
- Paper-specific question: We will also post one question for the paper that you are supposed to answer

## Class Presentation
- Depending on the number of students, each student will give one to three talks in this class.
- The speaker should check with me at least 7 days ahead of time to discuss any confusions or questions on the paper. You can also get my feedback on your slides. In the class, we expect you to know most details of the paper and will refer to you if we have any confusions about the paper during our discussion.
- Some authors share slides online; Some conferences share conference talk videos online. You are encouraged to check out those slides/videos or reuse some for your presentation. However, please be aware that conference talks are often short and focuses more on the motivation rather than the technical details. They may also be biased in highlighting only the benefits of their approaches (everyone likes his own work). So if you reuse the slides, please add more technical details (make sure you really understand what's going on in detail), and share your own opinion of the work (not just the authors').
- The goal of the presentation and in-class discussion is to learn how to form your own opinions of a paper.

### Presentation format
- The presentation is supposed to cover the major content of the paper such as motivation (what problem the paper is solving; why is this problem not solved before), challenges (why is this problem difficult to solve), system design (how the authors address the challenges), Evaluation (Does it demonstrate that the problems/challenges are solved?), and your personal opinions of the paper.
- The talk is supposed to be longer than a normal conference talk because we want to extend on problem formulation (give more context on problem setting) and detailed system design.
- In addition, please read all the reviews submitted by your classmates and list their questions in the slides. And lead the discussions of these questions in class.

## Projects

The semester-long project is an open-ended systems research project. Project topics are of your choice but should be related to networking. Projects should be done in groups of two or three and include a systems building component. From my previous experiences, a significant portion of the final projects end up as published workshop papers. At the end of the semester, I'll suggest a few places for you to submit your course work to a real workshop! Or you may continue to work on it to make it a conference paper.

### Project Timeline
- Project Timeline
- 9/23 Form groups for course projects
- 10/02 Course project proposal presentation
- 11/02 Midterm project report
- 12/02 Final project presentation
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
