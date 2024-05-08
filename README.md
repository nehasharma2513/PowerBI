In this project we are performing Sales Analysis for AtliQ Hardware. The sales have declined recently, and the head sales director wants to identify where the business is failing. We're developing Sales Reports using PowerBI to uncover the sales performance of the market, highlighting the areas that need improvement.

The AIMS Grid for this project is as follows:

<img width="488" alt="AIMS grid" src="https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/56838d65-90c6-4602-a819-b44381e1d038">

This is the schema for the data : 

![Sales_schema Chart](https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/c497c689-6ca4-400f-b07b-ebbbbcfb86c6)

Following steps are performed for data cleaning:

1. Removed International Data from 'markets' table. AtliQ Hardware operates mainly in India hence we are assuming international transactions happened only once in a lifetime
2. Removed zero and -1 sales_quantity rows from 'transactions' table. Assuming these are erroneous entries.
3. Added new column to 'transactions' table : norm_sales_amount. This column has the conversion done for USD values in sales_amount column.

The data is loaded into MySQL database using the SQL dump. Following this data analysis is perfomed using MySQL workbench. For the list of queries executed refer SQL_Query document in the repo.

Data is then loaded into PowerBI desktop and the model is defined as follows :

![ERD](https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/bdd215cd-dc04-4961-9325-c6d4527b3619)

Additional measures are calculated using DAX and stored in the BaseMeasures table. 

Market Insights Report is created highlighting zone-wise sales performance which can be drill down into market-wise charts.

![Market_SS](https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/a91cb305-de1d-4081-a496-545333d10678)

![Market_SS2](https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/07275d81-92c2-4990-87dd-4a920d091bbf)

Customer Insights Report highlights sales performance for each customer.

<img width="722" alt="Customer_SS" src="https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/a826da7e-f446-417b-8be8-49b21973fc03">

**Limitations:** 
Product Insights could not be performed as some of the product_codes were missing from the 'products' table. On further investigating it was discovered these product_codes had entries in the 'transactions' table.

<img width="485" alt="product_missing1" src="https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/b0206982-dc3b-47ab-9b98-c4aa664c76e3">
<img width="363" alt="product_missing2" src="https://github.com/nehasharma2513/PowerBI-SalesAnalysis/assets/142134132/1c22c8cc-80d5-43f1-b819-6b6a795a57f1">

<br/>
Connect with me : [Neha Sharma](https://www.linkedin.com/in/nehasharma25)
<br/>
Credits: [CodeBasics](https://codebasics.io/resources/sales-insights-data-analysis-project)


