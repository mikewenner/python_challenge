# python_challenge

## This is homework #2 focusing on the initial python skills learned in weeks 2 & 3 of the Rutgers FinTech Bootcamp program.  There are 2 activities in this assignment entitled PyBank and PyRamen.
***
## PyBank Challenge
### In this assignment, you will create a Python script that analyzes the financial records of your company.  Inside your starter code, you will find a financial dataset in the budget_data.csv file. This dataset is composed of two columns, Date and Profit/Losses. (Thankfully, your company has rather lax standards for accounting, so the records are simple.)

#### Your task is to create a Python script that analyzes the records to calculate each of the following:
- The total number of months included in the dataset
- The net total amount of Profit/Losses over the entire period
- The average of the changes in Profit/Losses over the entire period
- The greatest increase in profits (date and amount) over the entire period
- The greatest decrease in losses (date and amount) over the entire period

***
## PyRamen Challenge (This assignment has two parts):

## 1. Read the Data

## 2. Manipulate the Data

### Part 1: Read the Data
Complete the following steps:

- Read in menu_data.csv and set its contents to a separate list object. (This way, you can cross-reference your menu data with your sales data as you read in your sales data in the coming steps.)

- Initialize an empty menu list object to hold the contents of menu_data.csv.

- Use a with statement and open the menu_data.csv by using its file path.

- Use the reader function from the csv library to begin reading menu_data.csv.

- Use the next function to skip the header (first row of the CSV).

 - Loop over the rest of the rows and append every row to the menu list object (the outcome will be a list of lists).

- Set up the same process to read in sales_data.csv. However, instead append every row of the sales data to a new sales list object.

### Part 2: Manipulate the Data (Complete the following steps):

- Initialize an empty report dictionary to hold the future aggregated per-product results. The report dictionary will eventually contain the following metrics:
    - 01-count: the total quantity for each ramen type

    - 02-revenue: the total revenue for each ramen type

    - 03-cogs: the total cost of goods sold for each ramen type

     - 04-profit: the total profit for each ramen type

- Loop through every row in the sales list object.
For each row of the sales data, set the following columns of the sales data to their own variables:

    - Quantity
    - Menu_Item
- Perform a quick check if the sales_item is already included in the report. If not, initialize the key-value pairs for the particular sales_item in the report. Then, set the sales_item as a new key to the report dictionary and the values as a nested dictionary containing the following:

    - {
"01-count": 0,
"02-revenue": 0,
"03-cogs": 0,
"04-profit": 0,
}
- Create a nested loop by looping through every record in menu.
For each row of the menu data, set the following columns of the menu data to their own variables:

    - Item
    - Price
    - Cost
- If the sales_item in sales is equal to the item in menu, capture the quantity from the sales data and the price and cost from the menu data to calculate the profit for each item.

    - Cumulatively add the values to the corresponding metrics in the report like so:

        - report[sales_item]["01-count"] += quantity
report[sales_item]["02-revenue"] += price * quantity
report[sales_item]["03-cogs"] += cost * quantity
report[sales_item]["04-profit"] += profit * quantity
Else print the message "{sales_item} does not equal {item}! NO MATCH!".

- Write out the contents of the report dictionary to a text file. The report should output each ramen type as the keys and 01-count, 02-revenue, 03-cogs, and 04-profit metrics as the values for every ramen type