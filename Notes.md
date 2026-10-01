# DAX Measures — Copilot Notes

## 1. Total Sales

### Copilot Initial Suggestion

Copilot suggested using the SUM function on the sales amount column to calculate total sales.

### Final Measure

Total Sales =
SUM(fact_sales[sales_amount])

### Correction

The suggested calculation was checked against the fact table and the final measure was aligned with the actual sales amount column in fact_sales.

## 2. MoM Growth %

### Copilot Initial Suggestion

Copilot suggested calculating month-over-month growth by comparing current month sales with previous month sales using CALCULATE and DATEADD.

### Final Measure

MoM Growth % =
VAR CurrentSales = [Total Sales]
VAR PreviousSales =
CALCULATE(
[Total Sales],
DATEADD(Dim_Date[date], -1, MONTH)
)
RETURN
DIVIDE(
CurrentSales - PreviousSales,
PreviousSales
)

### Correction

The date column was checked and changed to the actual date field from the Dim_Date table so that the calculation works correctly with the project's date dimension.

## 3. Running Total Sales

### Copilot Initial Suggestion

Copilot suggested using CALCULATE with a filtered date table to calculate cumulative sales up to the current date.

### Final Measure

Running Total Sales =
CALCULATE(
[Total Sales],
FILTER(
ALL(Dim_Date[date]),
Dim_Date[date] <= MAX(Dim_Date[date])
)
)

### Correction

The calculation was checked to ensure that the date filter was applied using the Dim_Date table rather than directly relying on the fact table.

## 4. Product Sales Rank

### Copilot Initial Suggestion

Copilot suggested using RANKX to rank products according to their total sales.

### Final Measure

Product Sales Rank =
RANKX(
ALL(Dim_Product[item]),
[Total Sales],
,
DESC,
DENSE
)

### Correction

The ranking was configured to use the product dimension and the Total Sales measure so that products are ranked consistently according to their sales performance.

## Conclusion

GitHub Copilot was useful for providing initial DAX approaches and reducing the time required to develop the measures. Each suggestion was reviewed against the actual Power BI data model before being finalized. This helped ensure that the measures used the correct tables, columns, relationships, and business logic.
