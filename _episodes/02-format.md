---
title: "Formatting Spreadsheets"
teaching: 0
exercises: 0
questions:
- "How can I make my tables easily understandable by humans?"
- 
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

The data in spreadsheets often needs to be human readable in addition to being something that the computer can understand. It is important to remember that sometimes the things we can see in a spreadsheet have no meaning to the computer, so if you transfer data from one format to another you may lose key information. Below is an example:

![Starting Table](../fig/2020-01-17-EngiExcel-condColor.png)

This is our example table, but with conditional formatting applied - yellow is the lowest to bright green for the  highest. This formatting makes it easy for us to see what is happening in the table, but the analysis of which numbers are higher or lower is limited to Excel. This information would have to be calculated in the context of another statistics program. The same would apply if we manually **bolded** the numbers we wanted to use or made the text a different color.

## Formatting for Clarity

There are lots of things we can do in Excel to make our tables easier to understand. The simplest way is to outline our discrete sections of data and bolding the headings. For example:

![Starting Table](../fig/2020-01-17-EngiExcel-boldOutline.png)

As we go forward with our example we will talk about some more strategies:

> ## Add the cells for the rest of the problem
> 
> The first section of data for the problem shows the amount it costs to send each widget from each of the warehouses to each of the labs. The problem we are trying to solve with the data is to find the most cost-effective way to ship 300 widgets to each of the labs from warehouses that have the following supply: Warehouse 1 - 150, Warehouse 2 - 300, Warehouse 3 - 450. 
> 
> The element that we are going to ask Excel to calculate for us is the shipments from the warehouses and to the labs. In order to use solver later, we will set up a table to hold that data. We will also set up rows and columns to hold the other requirements that need to be fulfilled that are mentioned above.
>
{: .challenge}

{% include links.md %}

