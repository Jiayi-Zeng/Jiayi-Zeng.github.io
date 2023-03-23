---
title: "6 Simulation Modeling and Monte Carlo Simulation"

date: 2023-03-10

tags: [DS]

categories: "Prescriptive Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303100331.png
---

# **1 Introduction**

Simulation is a very powerful and expressive analytics tool for very complex problems that cannot be simplified and solved by optimization techniques. Because of its close representation of reality, simulation has become the “go-to” tool for many business consultancy companies, so much so that sometimes even the optimally solvable problems are analyzed using simulation modeling. 

# **2 Key Terms**

- Simulation
- Heuristic
- Discrete-event simulation
- Continuous simulation
- Deterministic simulation
- Stochastic simulation
- Simio
- Monte Carlo simulation

# **3 What is Simulation?**

Generally speaking, *simulation* is an imitation of reality within a computer environment or the computerized representation of a given real-world situation. In order to simulate, a model of the real-world scenario must be developed. Such a model is designed to represent the key characteristics, behaviors, and functions of the particular physical or abstract world, system, or process. Although simulation is usually developed to mimic reality, sometimes it is developed for situations beyond reality, i.e., imaginary, surreal, or even “future” worlds. Perhaps the best example of the simulation of surreal worlds is found in video games. Most agree that video games represent the most advanced, leading-edge computer simulations in terms of functionality, randomness, and visual effects.

# **4 Types of Business Problems Can or Should be Solved with Simulation**

Simulation modeling has been applied to a variety of complex business systems. Especially suitable for systems that have a complex process of logic and stochastics (imprecise) time estimates. Successful applications of simulation can be found in many industries including manufacturing, healthcare, finance, mining, aerospace, telecommunications, tourism and entertainment, government, homeland security, defense, and military. Here are some high-level characteristics of systems and situations that warrant the development of a simulation modeling-based analytics application: 

- **Systems where it is too expensive, too risky, or impossible to do live experimentations**. In such situations, simulation provides an inexpensive, risk-free way to test and study the changes incurred in the system. 
- **Complex systems for which a significant change/improvement is being considered.** A guess is usually a poor substitute for an objective analysis of the system. Simulation can help in accurately predicting system behavior under projected condition changes and reduce the risk of making a poor decision.
- **Systems where predicting process variability is important.** A spreadsheet analysis cannot capture the dynamic aspects of a system, i.e., aspects which can have a major impact on system performance. Simulation can help you understand how various components interact with each other and how they affect overall system performance.
- **Systems where you have incomplete data.** Simulation cannot invent data where it does not exist, but simulation does well at determining sensitivity to unknowns. A high-level model can help you explore alternatives. A more detailed model can help you identify the most important missing data.
- **Systems where you need to communicate ideas.** The development of a simulation helps participants better understand the system. Modern 2D and 3D animations and other visual tools promote communication and understanding across a wide variety of stakeholders. 

# **5 Types of Simulation Models**

Simulation models are created using software tools designed to capture and represent the system components and their interrelationships and calculate/record their behavioral outcomes over time. Simulation is used for predicting both the effect of changes to existing systems and the projected performance of an imaginary, futuristic, or planned new system. Simulations are frequently used in the assessment of alternative designs, testing and validation of operations, and calculation of risk propensity of current and future systems. 

Simulations can be categorized based on several dimensions. The most common categorizations of simulations are based on:

1. Whether or not they include time into their representation of the underlying system (i.e., *static* versus *dynamic* simulation).
2. Whether they handle the probabilistic nature of the system variables (i.e., *deterministic* versus *stochastic* simulation).
3. Whether they perceive and represent the underlying phenomenon as a continuous system (i.e., *discrete* versus *continuous* simulation).

Let’s consider each of these categories in a bit more detail:

- **Static (time-independent) versus dynamic (time-dependent) simulation**. Time is a crucial element of most systems where the system status changes over time. Not every system needs to be analyzed over time. One of the prime examples of time-independent simulation modeling is called the *Monte Carlo* simulation, which we’ll discuss below.
- **Deterministic versus stochastic simulation.** In a stochastic simulation (the most common type of simulation models), randomness is explicitly captured to better represent the variation found in most real-world systems. Deterministic models have no variation.
- **Discrete versus continuous simulation.** Generally speaking, the terms “discrete” and “continuous” refer to the nature in which the states change within the system. A “state” in this context is a snapshot of the system as it is defined by all of its parameters and their respective values. Some systems are purely discrete or purely continuous, while others have both types of states present. 

## 5.1 SIMIO: a Popular Simulation Modeling Platform for Business Problems

Simio (see [simio.com)](https://www.simio.com/) is a very powerful, general purpose, commercial simulation tool. On this site, you can demo different types of simulations to see the breadth of what is possible. One of these types is the Monte Carlo simulation model.

# **6 Monte Carlo Simulation** 

A *Monte Carlo* simulation refers to any simulation, manual or computer-based, that utilizes random numbers to represent one or more of the variables in the simulation model. As the name suggests, this simulation is named after the city of Monte Carlo in Monaco. In addition to its natural beauty, Monte Carlo is famous for its casinos, chance gaming, and gambling. Although Monte Carlo simulation and stochastic simulation are two synonymous terms, because of its name appeal, this type of simulation is commonly called Monte Carlo— though stochastic simulation is a more descriptive and technical term for it. The Monte Carlo simulation process involves generating random (or chance) variables to represent and illustrate random collective behavior. Figure 1 below illustrates a simple depiction of developing a Monte Carlo simulation model. 

![Shows the steps for developing a Monte Carlo simulation model. Access the long description link for a detailed explanation.](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/VbeP_kpuIFhnteUTvb3nAPlVhW4G_3TDsJK0n7zpJkQ58ZmPSEpzn8TSpqTKGZtKog56ZANa5yGjh0UFWNUiJakDiVi-pje9LuPE7X8r4TYWcgpOdqfvgVIyaUUh8zs1i20fqpmTAeSx0aHGHJAieg)

*Figure 1: Steps for developing a Monte Carlo simulation model* [[Long Description](https://docs.google.com/document/u/0/d/1u5M9QEWtcYP3l92smXT1mLwFw1utkIIKYBZWG1gK240/edit)]

