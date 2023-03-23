---
title: "2 Decision Making: Theory, Process, & Practice"

date: 2023-03-06

tags: [DS]

categories: "Prescriptive Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303061115%20(2).png
---

# **1 Introduction**

Decision making can be spontaneous (自发的) or systematic. For personal and social matters, spontaneous and haphazard (胡乱的) decisions typically work fine, but for professional and business-related matters, one should follow a scientific and standardized process. Such a process helps in implementing best practices, promoting the use of data and information (as opposed to opinions and gut feelings 直觉), and hence, creating accurate and consistent outcomes. 

# **2 Concept(s) Overview** 

## 2.1 Overview of the Human Decision-Making Process

Simon (1977) said that such **a systematic process involves three major phases: *intelligence*, *design*, and *choice*. He later added a fourth phase (*implementation*). *Monitoring* can be considered a fifth phase (i.e., a form of feedback);** however, we view monitoring as part of the ‘intelligence’ phase as applied to the ‘implementation’ phase as we’ll see below. Simon's model is widely accepted as the most concise (简洁）, and yet most complete, characterization (表征) of rational decision making. A conceptual picture of this decision-making process is shown in Figure 1.

![The decision making/modeling process starts with real world issues or problems. These issues are considered in the first 'intelligence' phase where some kind of problem statement is produced. This statement leads to the 'design' phase or solution phase. Alternatives are considered and eventually a decision is made in the 'choice' stage leading to the 'implementation' phase. Once the decision is implemented the cycle moves back to the real world.](https://lh4.googleusercontent.com/4e-dWnGfX1r9mIs7UcuwLkWlXHdhuP0gPvEnVUpnpyGN0eidcmgn5_Z2_tvOQGAmMX1UbNSn-5eYBoU4b1DPbAUBzEGngOH-hUq1Y8oODFQEjpUn4ymzE-s-bEi4M67yM1oQ1rlz_eQhJr-YVT-vWQ)

*Figure 1: The decision-making/modeling process*

### 2.1.1 Intelligence

The *intelligence* phase in the decision-making process involves **scanning the environment**, either intermittently or continuously (间接性或持续性). It includes several activities aimed at identifying problem situations or opportunities. As mentioned above, it may also include monitoring the results of the implementation phase of a decision-making process.

### 2.1.2 Design

The *design* phase involves finding or developing and analyzing possible courses of action. These include **understanding the problem and testing solutions for feasibility.** A model of the decision-making problem is constructed, tested, and validated. Modeling involves conceptualizing (概念化) a problem and abstracting it into quantitative (定量) and/or qualitative (定性) form. For a mathematical model, the variables are identified, and their mutual (相互的) relationships are established.

### 2.1.3 Choice

Choice is the critical act of decision making. The *choice* phase is the one in which the actual decision and the commitment to follow a certain course of action are made. The boundary between the design and choice phases is often unclear because certain activities can be performed during both phases and because the decision maker can return frequently from choice activities to design activities (e.g., generate new alternatives while evaluating existing ones). The choice phase includes **searching for, evaluating, and recommending an appropriate solution to a model**. A solution to a model is a specific set of values for the decision variables in a selected alternative.

### 2.1.4 Implementation

*Implementation* is the actual deployment of the choice. The implementation of a proposed solution to a problem is the initiation of a new order of things or the introduction of change. Change must be managed, e.g., user expectations must be managed as part of change management. The definition of implementation is somewhat complicated because implementation is a long and involved process with vague boundaries. Simply put, the implementation phase involves putting a recommended solution to work. Many generic implementation issues, such as resistance to change, degree of support from top management, and the need for user training are important in dealing with managerial decisions.

## 2.2 CRISP-DM: A Standards Process for Analytics

The *CRISP-DM* (Cross-Industry Standard Process for Data Mining) methodology consists of a cyclical sequence of phases commonly used by data mining experts for traditional business intelligence (BI) data mining and data strategy development. Figure 2 summarizes this cycle— which is dynamic, features bidirectional movement between the six phases, and entails multiple iterations. In the diagram below, please note that:

- The iterative CRISP-DM process is shown in the outer circle.
- The most significant dependencies between phases are shown.
- Subsequent phases depend on results from the preceding phases.

*![A diagram showing the relationship between the 6 different phases of CRISP-DM. It illustrates the recursive nature of a data mining project.](https://lh3.googleusercontent.com/eW3nJAycOY0La88ygPNRaguPEKFv47vJiXq-xkx57F5xV1AP-nLuqrxbVWfCVcMlqXibc4a0bEusCe0GiVv0K6ZXmb7d-C4STlUuzQiLrKcH8Z86PGuQoLNp2sTioAzuqbGFyvemP-rbqLe3BAHYhQ)*

*Figure 2: The CRISP-DM process. (Source: Kenneth Jensen,* [*CC BY-SA 3.0*](https://creativecommons.org/licenses/by-sa/3.0)*, via Wikimedia Commons)* 

### 2.2.1The Six-Step Process to Guide Analytics Thinking and Problem Solving

In the [CRISP-DM 1.0 data mining guide](https://the-modeling-agency.com/crisp-dm.pdf), Chapman et al. (2000) lay out specific activities that can guide analytics thinking for each phase, as highlighted below:

#### **Phase 1: Business/Research Understanding**

- Define project requirements and objectives
- Translate objectives into a data mining problem definition
- Prepare a preliminary strategy to meet the objectives

#### **Phase 2: Data Understanding** 

- Collect data
- Perform exploratory data analysis (EDA)
- Assess data quality
- Select interesting subsets (*optional*)

#### **Phase 3: Data Preparation** 

- Prepare for modeling in subsequent phases
- Select cases and variables appropriate for analysis
- Cleanse and prepare data so it is ready for modeling tools
- Perform transformation of certain variables, if needed

#### **Phase 4: Modeling** 

- Select and apply one or more modeling techniques
- Calibrate model settings to optimize results
- Prepare additional data, if required, to support a particular technique

#### **Phase 5: Evaluation** 

- Evaluate one or more models for effectiveness
- Determine whether defined objectives are achieved
- Establish whether any important facet of the problem has not been sufficiently accounted for
- Make a decision regarding data mining results before deploying to the field

#### **Phase 6: Deployment**

- Make use of models created
- Generate the report (simple deployment example)
- Implement a parallel data mining effort in another department (complex deployment example)

*Note*: In some businesses, the customer often carries out the deployment based on the model delivered by the analytics team.

# **3 Mathematics for Prescriptive Analytics**
1. Linear Programming
2. Non-Linear Programming
3. Genetic Algorithm
4. Simulation

