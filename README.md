# Linear-programming

## Overview

This project is an implementation of unsupervised learning techniques and linear programming to optimize supplier selection and logistics within a supply chain network. The project involves clustering suppliers based on various performance metrics and solving a linear programming problem to minimize the total cost of manufacturing and transportation.

## Data

The project utilizes two datasets:
1. `SupplierAuditData.csv` - Contains monthly audit data for various suppliers, including defects, delivery times, unit costs, and flexibility.
2. `SupplierCharacteristics.csv` - Contains additional characteristics of suppliers, such as location, partnership status, and size.

## Clustering Analysis

### Steps:
1. **Load the Data**: Read the supplier audit and characteristics data.
2. **Calculate Statistics**: Group data by supplier and calculate mean and standard deviation for defects, costs, delivery time, and flexibility.
3. **K-Means Clustering**: Perform K-Means clustering on the calculated statistics to identify distinct groups of suppliers.
4. **Cluster Interpretation**: Analyze and interpret the characteristics of each cluster.

### Cluster Descriptions:
- **Cluster 0 (Low Cost, High Delivery Time)**: Suppliers with low defects and costs but longer delivery times.
- **Cluster 1 (High Cost, Low Defect Variability)**: High-cost suppliers with consistent quality and short delivery times.
- **Cluster 2 (High Defects, High Flexibility)**: Suppliers with high defects but high flexibility.
- **Cluster 3 (Moderate Cost, High Quality Variability)**: Moderate costs, high quality variability, and relatively flexible.

### Visualizations:
- Scatter plots depicting relationships between average defects, costs, delivery times, and flexibility for different clusters.

## Linear Programming

### Problem:
Minimize the total cost of manufacturing and transportation while fulfilling the demand of retailers.

### Steps:
1. **Model Setup**: Define the linear programming model and decision variables.
2. **Cost Definitions**: Define manufacturing and transportation costs.
3. **Objective Function**: Minimize the sum of manufacturing and transportation costs.
4. **Constraints**: Include demand fulfillment and flow balance constraints.
5. **Solve the Model**: Use the `pulp` library to solve the linear programming problem.

### Results:
- Optimal total cost: $9,985,000.
- Supplier S1 exclusively meets the demand, with no utilization of Supplier S2.
- Warehouses distribute products to retailers efficiently.

## Conclusion

This project demonstrates the application of unsupervised learning to classify suppliers and the use of linear programming to optimize supply chain logistics. The clustering analysis helps in understanding supplier performance, while the linear programming model provides a cost-effective strategy for fulfilling retailer demands.

## Requirements

- Python 3.x
- Pandas
- Scikit-learn
- Matplotlib
- Pulp

## Usage

1. **Data Loading**:

    ```python
    import pandas as pd

    audit_data = pd.read_csv('SupplierAuditData.csv')
    characteristics_data = pd.read_csv('SupplierCharacteristics.csv')
    ```

2. **Clustering**:

    ```python
    from sklearn.cluster import KMeans
    import matplotlib.pyplot as plt

    # Group by supplier and calculate statistics
    # Perform K-Means clustering
    # Plot results
    ```

3. **Linear Programming**:

    ```python
    from pulp import LpProblem, LpMinimize, LpVariable, lpSum

    # Define and solve the linear programming model
    ```

## Files

- `hw4_panshul3.pdf`: Detailed report of the assignment.
- `SupplierAuditData.csv`: Supplier audit data.
- `SupplierCharacteristics.csv`: Supplier characteristics data.
