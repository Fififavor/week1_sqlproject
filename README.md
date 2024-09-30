You are provided with a table called Sales, which contains the following columns:
1). SaleID: A unique ID for each sale.
2). ProductID: The ID of the product sold.
3). CustomerID: The ID of the customer who made the purchase.
4). SaleDate: The date the sale occurred.
5). Amount: The amount of the sale.

Questions- Write SQL scripts that:
1). Finds the total sales for each product.

SELECT ProductID, SUM(Amount) AS TotalSales
FROM Sales
GROUP BY ProductID;

2). Calculates the total sales for each month.

SELECT YEAR(SaleDate) AS SaleYear, MONTH(SaleDate) AS SaleMonth, SUM(Amount) AS TotalSales
FROM Sales
GROUP BY YEAR(SaleDate), MONTH(SaleDate);

3). Identifies customers who made more than 5 purchases.

SELECT CustomerID, COUNT(SaleID) AS PurchaseCount
FROM Sales
GROUP BY CustomerID
HAVING COUNT(SaleID) > 5;
