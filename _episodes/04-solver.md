---
title: "A Brief Intro to Solver"
teaching: 0
exercises: 0
questions:
- "What prep work do we need to do to use Solver?"
- "How do the different components of Solver work?"
objectives:
- "Be able to think through a problem so we can use Solver."
- "Talk about how to document your steps in Solver."
keypoints:
- "Solver can be useful, but you need to think through the problem."
- "In order for other people to understand what you did you need to document your steps." 
---

## Adding Solver to the Data Ribbon

Solver is built in to Excel, but it may not automatically show up. It should be in the Data ribbon in the **Analyze** section. If it is not there, you can go to the **File** menu and choose **Options**. Go to **Add-ins** and choose **Excel Add-ins** from the **Manage:** menu and click **Go...**. Make sure that the **Solver Add-in** is checked.

![Main Options - Add-ins Menu](../fig/2020-01-17-EngiExcel-addIns.png) ![Add-ins check boxes](../fig/2020-01-17-EngiExcel-addInsSolver.png) 

## Solver for our Distribution Example

The initial Solver window is shown in the image below. The default values are highlighted with green borders.

![Solver Default](../fig/2020-01-17-EngiExcel-solverDefaults.png)

Solver correctly guessed that the **Objective** of our analysis is the **TotalCost**. This is the value that is the goal of our analysis. We can ask it to look for the **Max** (which is the default), the **Min** (which is actually what we want - the lowest possible total cost of sending the widgets where they need to go), or **Value Of:** (where you can set a specific value as the objective).

**Choose the Min button instead of Max**. 

The second choice we need to make in Solver is to indicate the **Variable Cells**. These are the cells that Solver will adjust to find the solution to our problem, in this case the number of widgets to each lab from each warehouse. 

**Type Sent in the By Changing Variable Cells: box.**

The next box allows us to set additional constraints on our analysis. In our case, the **Total Sent** from each warehouse can't exceed the **Total Stock** and the **Total Received** by each lab should equal the **Total Request**. Click on the **Add** button and the following window will show up:

![Change Constraint](../fig/2020-01-17-EngiExcel-changeConstraint.png)     

The **Cell Reference** is the cell or group of cells with the function in it, with the values changing based on the **Variable Cells**. The **Constraint** is the cells or cells that have the values that remain constant. You can choose your operator from the pull-down menu, from **<=, >=, =, bin, diff, or int**. We won't talk about bin (binary), diff (difference), or int (integer) in this lesson. If you click the **Add** button you will get the chance to add another constraint, whereas if you click **OK** it will save that constraint and close the window. The **Cancel** button closes the window without saving.

The last thing you need to do is **Select a Solving Method:**. The default is **GRG Nonlinear**. If you are not absolutely sure that your problem is linear, this is the best choice of method. The **Simplex LP** method is for linear problems and the **Evolutionary** method is for non-smooth problems. Your final Solver window should look like this:

![Final Solver settings](../fig/2020-01-17-EngiExcel-solverFinal.png) 

When you click **Solve** you will get the following information about the Solver solution:

![Solver Results](../fig/2020-01-17-EngiExcel-solverResults.png)  

 

  

{% include links.md %}

