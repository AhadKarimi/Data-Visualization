
# Visualizing Interest Rates, Housing Prices, and Municipality Population in Power BI
![enter image description here](https://datadp.com/wp-content/uploads/2024/08/Visual-Insights-Interest-Rates-Housing-Prices-Population-Growth-1024x647.png)
Visual Insights Interest Rates, Housing Prices & Population Growth

Creating a comprehensive dashboard that tracks multiple economic indicators can provide valuable insights. In this post, we’ll explore how to build a line chart in Power BI that measures  **Interest Rates**,  **Housing Prices**, and  **Municipality Population**.

**First**, let’s set up your data. Ensure you have a dataset that includes the following columns:

-   **Year**
-   **Interest Rate (%)**
-   **Housing Price ($)**
-   **Municipality Population**

**Second**, we face the challenge of only having two Y-axes available in a standard line chart. To solve this, we can use a  **Composite Metric**  to combine Housing Prices with Population Growth. Here’s a DAX formula to create this metric:

    Composite Metric ($) = 
    SUMX(
      'Table',
      'Table'[Housing Price ($)] * (1 + 'Table'[Population Growth (%)] / 100)
    )
    
**Third**, create the line chart:

1.  **X-axis**: Set this to  **Year**.
2.  **Primary Y-axis**: Use  **Interest Rate (%)**.
3.  **Secondary Y-axis**: Use the  **Composite Metric ($)**.

You can download the PBIX file and the sample data in an XLSX file from the links below to explore and practice on your own:

[Download Power BI file](https://datadp.com/wp-content/uploads/2024/08/Visual_Insights_Interest-Rates_Housing_Prices_Population_Growth.pbix)

[Download Table](https://datadp.com/wp-content/uploads/2024/08/Table.xlsx)
