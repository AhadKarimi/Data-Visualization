# Multiplying SUM by Each Column Value with a Measure in Power BI
![Multiplying SUM by Each Column Value with a Measure in Power BI](https://datadp.com/wp-content/uploads/2024/08/How_to_Multiply_a_Sum_Measure_by_Each_Value_of_a_Column_in_DAX_Thumbnail.jpg)

In Power BI, it’s common to need to multiply the total SUM of a column by each value in another column to perform more complex calculations. Here’s a quick guide on how to achieve this using DAX.

# Table:

|Month  |Index  |BurnRate  |
|-------|-------|----------|
|Nov	|1	|16,157.44|
|Dec	|2	|9,489.11|
|Jan	|3	|12,960.78|
|Feb	|4	|12,126.44|
|Mar	|5	|13,329.78|
|Apr	|6	|16,626.33|
|May	|7	|23,324.89|
|Jun	|8	|20,419.22|
|Jul	|9	|22,842.33|
|Aug	|10	|0.00|
|Sep	|11	|0.00|
|Oct	|12	|0.00|


## Step 1: Create the TotalBurnRate Measure:
```dax
TotalBurnRate = SUM(MyTable[BurnRate])
```

## Step 2: Create Multiplied Index By Total BurnRate Measure:
```dax
MultipliedIndexByTotalBurnRate = 
SELECTEDVALUE(MyTable[Index]) * CALCULATE(SUM(MyTable[BurnRate]), ALL(MyTable))
```

## Result and download:
![Multiply SUM by Column in Power BI](https://datadp.com/wp-content/uploads/2024/08/How_to_Multiply_a_Sum_Measure_by_Each_Value_of_a_Column_in_DAX_Result-1024x359.jpg)


[Download PBIX file](https://datadp.com/wp-content/uploads/2024/08/How_to_Multiply_a_Sum_Measure_by_Each_Value_of_a_Column_in_DAX_v2.pbix)
