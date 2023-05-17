---
title: Reverie Books CT, LLC Database Project
header:
  overlay_color: "#32333b"
  overlay_image: /assets/images/post5_2023-05-17/freestocks-RgKmrxpIraY-unsplash.jpg
  image_description: "Picture of books taken by freestocks on Unsplash"
  show_overlay_excerpt: false
excerpt: Reverie Books CT, LLC is a small business that sells secondhand books via ecommerce and community tabling events. The client wanted a free, simple solution for managing their inventory, costs, and sales on Google Sheets.
date: May 17, 2023
toc: true
toc_sticky: true
tags:
  - Data Processing
  - Metadata
  - Relational Database
---
# Reverie Books CT, LLC Database Project
## OVERVIEW
Reverie Books CT, LLC is a small business that sells secondhand books via ecommerce and community tabling events. Customers have the option of purchasing a book in a ‘blind date’ format where the owner selects a book that meets their preferences. This surprise and delight marketing strategy transforms the purchase of a secondhand book into a memorable experience.
<br>
## PROBLEM
The owner of Reverie Books CT, LLC encountered an issue regarding their inventory management system. Upon acquisition of a book, pertinent information (ex. title, author, genre) was entered into a ‘Inventory Available’ spreadsheet. When the book was sold, this information was cut and pasted onto an ‘Inventory Sold” spreadsheet. This method made data processing lengthy, preventing the owner from focusing on other business tasks.
<br>
## SPECIFICATIONS
The owner of Reverie Books CT, LLC wanted a free, simple solution for managing their inventory, costs, and sales. Preferences included using the cloud-based Google Sheets software and the ability to calculate metrics.
<br>
## GOALS
* Develop a relational database diagram that illustrates the table structure and connections.
* Construct a relational database on Google Sheets for Reverie Books CT, LLC to manage its inventory, costs, and sales.
* Create a protocol that minimizes downstream data processing needs.
<br>
## MILESTONES
<u>Relational Database Diagram</u>
<br><br>
A diagram is required to illustrate table structure and connections of the database prototype. 
<u>Database Prototype</u>
<br><br>
The database prototype must be compatible with other spreadsheet programs as well as downloadable as individual tables for analysis and visualization in Tableau.
<br><br>
<u>Data Management Protocol</u>
The checklist will ensure the integrity of the data and simplify long term data management.
<br>
## DELIVERABLES
### Relational Database Diagram
A relational database diagram was created through the website <a href=’ https://dbdiagram.io/home’>dbdiagram.io</a>. In this schematic we can see that the database is composed of three connecting tables: an inventory table (InventoryAvail), its clone (InventorySold), and a dictionary table. The legend and metrics accessory sheets were included for downstream analysis. To find the code for this diagram, click <a href=’ https://github.com/hjkissinger/ReverieBooksCT/blob/main/RB-DBdiagram’>here</a>.
<br>
![ERD for Reverie Books CT, LLC]({{ site.url }}{{ site.baseurl }}/assets/images/post5_2023-05-17/RB-relationalDB.jpg)
<br>
All attributes included in the tables were specified by the client. The small business owner wanted the ability to track her inventory’s book type (genre, paperback, etc.) and cost. Cost was divided into three categories: material cost (book acquisition), raw material cost (wrapping paper), and shipping cost. This allows the client to account for cost of sales made at a tabled event or via ecommerce. 
<br><br>
The dictionary table stores static information on books such as title, author, year, etc. This table is connected to the InventoryAvail and InventorySold tables by the primary key, GenreID_Key. The GenreID_Key is an identifier assigned by the client. It is composed of a letter that designates genre and its database entry number. For example, the first mystery book acquisition would be M0000. With this system, if the client acquires two copies of the same book, the dictionary table would require only one data entry.
<br><br>
The *bolded* attributes in the relational database diagram are *primary keys*. To make the InventoryAvail and InventorySold tables have unique identifiers, the _InventoryAvail Sold_Status must equal FALSE_ and _InventorySold Sold_Status must equal TRUE_. That way, each table is a separate entity. The mechanics of these primary keys will be discussed in detail in the next section.
<br>
### Database Prototype
This section will discuss building the database prototype in Google Sheets.
<br><br>
The InventorySold clone table was created using the Google Sheets function:

```
={Sheet!A1:K#}
```
**Where K# matches the last column and last row number on InventoryAvail.** This function copies all inputs made on InventoryAvail onto InventorySold. Thus, all data entry can be completed on the InventoryAvail sheet upon book acquisition and sale.
<br><br>
The composite key for InventoryAvail and InventorySold is the assigned SKU and Sold_Status. Using the ‘Filter’ function at time intervals, the owner can change the Google Sheets view where InventoryAvail Sold_Status = FALSE and InventorySold Sold_Status = TRUE. This functionality enables the owner of Reverie Books CT to see their current stock and prevent data transfer errors.
<br><br>
To further simplify the data entry process, Google Sheets functions such as *check boxes* (Sold_Status) and *dropdowns* (Price_Type, Product_Type) were added to the InventoryAvail sheet. 
<br><br>
![Spreadsheet for Reverie Books CT, LLC]({{ site.url }}{{ site.baseurl }}/assets/images/post5_2023-05-17/RB-spreadsheet.jpg)
<br>
By entering data on a single sheet, the client can have confidence that her data is accurate, complete, and consistent.
<br>
###Data Management Protocol
Data management protocols provided to the client included data entry steps for book acquisition and sale, the expansion of the InventorySold clone, and data extraction for Tableau analysis and visualization.
