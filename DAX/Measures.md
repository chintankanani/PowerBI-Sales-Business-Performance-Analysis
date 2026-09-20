# DAX Measures

This file documents the key DAX measures used in the Power BI dashboard.

## Sales & Profitability

### Total Revenue

```DAX
Total Revenue =
SUMX(
    'Sales 2015-2017',
    'Sales 2015-2017'[ProductPrice] *
    'Sales 2015-2017'[OrderQuantity]
)
```

Calculates total revenue based on product price and quantity sold.

---

### Total Profit

```DAX
Total Profit =
SUMX(
    'Sales 2015-2017',
    (
        'Sales 2015-2017'[ProductPrice] -
        'Sales 2015-2017'[ProductCost]
    ) *
    'Sales 2015-2017'[OrderQuantity]
)
```

Calculates total profit after considering product cost and quantity sold.

---

### Profit Margin %

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Revenue],
    0
)
```

Calculates profit as a percentage of total revenue.

---

## Orders & Customers

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(
    'Sales 2015-2017'[OrderNumber]
)
```

Calculates the number of unique orders.

---

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(
    'Sales 2015-2017'[CustomerKey]
)
```

Calculates the number of unique customers represented in the sales data.

---

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

Calculates the average revenue generated per order.

---

## Quantity & Returns

### Total Quantity

```DAX
Total Quantity =
SUM(
    'Sales 2015-2017'[OrderQuantity]
)
```

Calculates the total quantity of products sold.

---

### Total Returned Quantity

```DAX
Total Returned Quantity =
SUM(
    Returns[ReturnQuantity]
)
```

Calculates the total quantity of products returned.

---

### Return Rate %

```DAX
Return Rate % =
DIVIDE(
    [Total Returned Quantity],
    [Total Quantity],
    0
)
```

Calculates returned quantity as a percentage of total quantity sold.

---

## Data Validation

### Has Customer

```DAX
Has Customer =
IF(
    ISBLANK(
        SELECTEDVALUE(Customers[CustomerKey])
    ),
    0,
    1
)
```

Used to identify valid customer records and prevent unmatched customer records from affecting selected customer visuals.

---

## Key Dashboard KPIs

The main dashboard uses these measures to report:

- Total Revenue
- Total Profit
- Profit Margin
- Total Orders
- Total Customers
- Total Quantity
- Average Order Value
- Total Returned Quantity
- Return Rate

These measures support the dashboard's analysis of sales performance, profitability, customer behaviour, product performance and returns.
