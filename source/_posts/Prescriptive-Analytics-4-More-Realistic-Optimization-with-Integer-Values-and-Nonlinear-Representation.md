---

title: 4 More Realistic Optimization with Integer Values and Nonlinear Representation 

date: 2023-03-08

tags: [DS]

categories: "Prescriptive Analytics: Digital Decisioning"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303081012.png
---

# **Introduction**

Linear programming (LP) is a powerful tool to optimally solve a wide variety of business problems. Despite its power and widespread use, LP also comes with a few restrictive assumptions. Some of these assumptions can be removed or relaxed by using a slightly modified formulation of optimization problems, and the two assumptions that stand out in this front are:

- **Divisibility:** In LP, it is assumed that the solution (i.e., the values assigned to the decision variables) can be real/fractional numbers. We all know that many decision variables cannot have fractional values, such as the number of certain types of products to produce or the number of boxes of goods to ship to a warehouse, etc. The relaxation of this assumption, where the integer value of decision variables is a requirement, led to a derivative programming algorithm called *integer programming*. 
- **Linearity:** It is also assumed that linear proportionality exists in the formulation of the objective function and constraints. That is, the formulation of the objective function and the constraints does not allow for multiplication, square, or higher power representation of the decision variables. Removal of this assumption led to models that allow nonlinear relationships and are called *nonlinear programming*.

# **Integer Programming**

In linear programming models, one of the key assumptions is the unrestricted nature of the decision variable values. That is, the decision variables can assume real/fractional value; although, in most cases, the decision variables cannot have quantities as fractional values, such as the optimal quantity of each product to produce. Technically speaking, an *integer programming* problem is a mathematical optimization program in which some or all of the decision variables are restricted to be integers. *Mixed-integer programming* is like integer programming in that some, though not all, of the decision variables are required to assume integer values. 

The key difference between linear programming and integer programming is rather trivial. In linear programming, the decision variables are allowed to assume real values, whereas, in integer programming, they are required to have integer values. The solution mechanism for linear programming and integer programming is quite different, where the integer programming solution method requires significantly longer processing time and more computational resources. 

# **Simple Overview of Nonlinear Optimization**

*Nonlinear programming* (or *nonlinear optimization*) is the process of solving an optimization problem where some of the constraints and/or the objective function are expressed in a nonlinear algebraic formulation. 

An optimization problem aims to find the extreme/best points (maximum or minimum) of an objective function over a set of unknown (yet to be determined) decision variables while satisfying the conditions of a system of equalities and inequalities (collectively termed as “constraints”). In this optimization formulation, if the algebraic representation of decision variables is all or partially nonlinear, then we call it nonlinear programming. 

Often, in order to use the straightforward LP formulation, business analysts oversimplify the problem representation using linear equations where a nonlinear equation would be a more natural fit. In most cases, the results would be complementary, and such a simplification can be justified with the provided computational efficiency.

# **Sensitivity Analysis for More Detailed Explanation of the Optimal Solution** 

In addition to the optimal solution, Excel Solver can also provide a sensitivity analysis report for any LP solution. To generate a sensitivity analysis report, you need to select *Sensitivity* on the dialog box that pops up at the end of the Solver solution procedure (see Figure 1). 

**![A screenshot of the Solver Results dialog box in Excel. The dialog box shows that you need to select the Sensitivity box within the Reports section to generate a sensitivity analysis report.](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/j884-qR17OM7_ZbeAmacC5nOelxSND1JsPIk5kWw3a0i2TX_pPOUiTIVq5YSTpqgNgONA2xwmvsFdfYwOCisjdT-Ix2qqH8cJT4V8tO0ugFiqbZlZG7mCmeow0g1B4qIaBl-xTKkPppWAA_lDCKaWA)**

*Figure 1: Screenshot of a Solver Results dialog box in Excel*

A sensitivity analysis report helps in better understanding the optimal solution and its level of sensitivity to certain problem parameters. Specifically, the sensitivity analysis report provides two sets of measures: (1) **sensitivity of the objective function coefficients, and (2) sensitivity of the constraints’ right-hand-side values.** This information can potentially be used by decision makers to further improve the objective function value by manipulating/relaxing the values used in the problem definition.

# **Transportation Modeling**

The goal of the transportation problem is to minimize the total cost of transportation, where there is shipping of products from several *sources* (i.e., supply centers such as production plants) to *sinks* (i.e., demand centers such as warehouses). This shipping is accomplished while complying with supply-and-demand constraints, where the supply constraints limit the amounts of products shipped out of a source (e.g., a production plant or distribution center), and the demand constraints enforce the amounts of products to be sent to each sink (e.g., a warehouse or retail outlet). Figure 2 illustrates this in a simple pictorial representation. 

![An illustration of transportation modeling showing the three columns - the production plants on the left column links to warehouses in the right column and the middle column shows the supply and demand constraints. ](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/2v6eCTjkEMalRD_ZYK3GBMw87qut1AO1al_JA34axqRP8o8ZZSbbvmQHqcOzXEA1ZuUsW5Fu-dms6hJS4cKcynG8g4kZh4CIiQhvc1gjpdobnMOVUipwi5ayJNfeOsmBpqVEk1QZY8MATyN8PlJbYA)

*Figure 2: Transportation modeling illustration*

In this overly simplified example, we have three sources (i.e., three plants) and four sinks (i.e., four warehouses). Any of these plants can send products to any warehouse, each shipment with a different unit transportation cost. Each plant has production limits and each warehouse has demand requirements. The goal in this example is to find a solution that produces the minimum total transportation cost. This problem can also be represented as a simple matrix as shown in Figure 3 below. 

![The same transportation problem but represented in a matrix. There are four warehouses, each listed in a vertical column. There are three plants, each listed in a horizontal row. The cost of each shipment is listed in the intersections of the warehouse columns and plant rows. In addition, there is a supply column on the far right showing the supply number of each plant, and there is a demand row on the bottom depicting the demand of each warehouse. The supply column and demand row intersect on the bottom right of the matrix.](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/zBV156XraoShpMlgpQJSFPRuaBK53u6kwwcvB4XCKqxmNg7R2xhuGfDMOwqn2VdIw0gNyDeBBr-y8UAUoQK7Q_nt7kPffdmNwcDRcAP_Bk-CunEWRm5wCwf32N-GytDabzeBQiPv6Dfx268K8sS7Ww)

*Figure 3: The same transportation model represented as a matrix*

This problem can be solved **heuristically (using common logic) or optimally** (using linear programming). Let’s look at each solution in more detail below.

## Heuristic/Logical Solution 

To solve this problem, we can use a common-sense logical rule to assign shipment quantities into 12 decision cells which would minimize the total transportation cost while still complying with the supply-and-demand constraints. A commonly used heuristic is called “**maximizing shipment quantities for minimum unit cost options**.” In execution of this heuristic, one would find the minimum unit transportation cost cell and assign the largest possible value (quantity on that cell) while complying with the supply-and-demand constraints. This procedure is repeated until all 12 cells are filled with zeros and some non-zero integer numbers. This would produce a good solution but not necessarily the best (i.e., the optimal) solution. 

## Optimal/Excel Solution

The same problem can also be solved using Excel Solver, optimally. We can accomplish this in a similar way to that which we followed while solving the product-mix problem, i.e., by formulating the problem in an Excel sheet, specifying the optimization problem parameters in the Solver dialog box, and generating the optimal solution.