# BI
BI Practical


1.Implementation of classification algorithm in R programming.Consider the annual rainfall details start from 2012.
Code:
rainfall <- c(799,1174.8,865.1,1334.6,635.4,918.5,685.5,998.6,784.2,985,882.8,1071)
rainfall.timeseries <- ts(rainfall,start=c(2012,1),frequency=12)
print(rainfall.timeseries)
png(file="rainfall.png")
plot(rainfall.timeseries)
dev.off()
	


2.Implementation of decision tree using R tool.
code:
library(party)
input.dat <- readingskills[1:105, ]
png(file = "decision_tree.png")
output.tree <- ctree(
  nativespeaker ~ age + shoesize + score,
  data = input.dat
)
plot(output.tree)
dev.off()

3.Data analysis using Time Series analysis
Code:
rainfall <- c(799,1174.8,865.1,1334.6,635.4,918.5,685.5,998.6,784.2,985,882.8,1071)
rainfall.timeseries <- ts(rainfall,start=c(2012,1),frequency=12)
print(rainfall.timeseries)
png(file="rainfall.png")
plot(rainfall.timeseries)
dev.off()

4.Performing data clustering using clustering algorithm using R (K-mean Clustering).
Code:
newiris <- iris
newiris$Species <- NULL
KC <- kmeans(newiris, 3)
KC
table(iris$Species, KC$cluster)
png(file = "cluster.png")
plot(newiris[c("Sepal.Length", "Sepal.Width")],
     col = KC$cluster)
points(KC$centers[, c("Sepal.Length", "Sepal.Width")],
       col = 1:3, pch = 8, cex = 2)
dev.off()

6.Linear regression using R.
code:
x <- c(151, 174, 138, 186, 128, 136, 176, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y ~ x)
print(summary(relation))

new_data <- data.frame(x = 170) 
result <- predict(relation, new_data)
print(result)

png(file = "linear_regression.png")
plot(x, y, 
     col = "blue", 
     main = "Height & Weight Regression", 
     cex = 1.3, 
     pch = 16, 
     xlab = "Weight in kg", 
     ylab = "Height in cm")
dev.off()

9.Write Python program to read data from CSV file.
Code:
library(caTools)
quality <- read.csv("C:/Users/Students/Downloads/quality.csv")
str(quality)
table(quality$PoorCare)
set.seed(88)
split <- sample.split(quality$PoorCare, SplitRatio = 0.75)
qualityTrain <- subset(quality, split == TRUE)
qualityTest <- subset(quality, split == FALSE)
nrow(qualityTrain)
QualityLog <- glm(PoorCare ~ OfficeVisit + Narcotics, data = qualityTrain, family = "binomial")
summary(QualityLog)

10.write Python Program to Read data from a CSV file. Perform simple Data analysis and generate basic insight
Code:
import pandas as pd
file_path = "Book1.csv"
df = pd.read_csv(file_path)
print("\n First 5 rows of the dataset :")
print(df.head())
print("\n Dataset summary :")
df.info()
print("\n Basic statistics :")
print(df.describe())
print("\n Missing values in Each Column :")
print(df.isnull().sum())
print("\n Column Names :")
print(df.columns)
if 'Salary' in df.columns:
    print(f"\n Average Salary: {df['Salary'].mean()}")
if 'Age' in df.columns:
    print(f"\n Youngest Person's Age: {df['Age'].min()}")
    print(f"\n Oldest Person's Age: {df['Age'].max()}")
if 'Gender' in df.columns:
    print("\n Gender Distribution :")
    print(df['Gender'].value_counts())
print("\n Data Analysis Completed Successfully!")

11.Perform data visualization using Python on any sales data.
Code:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dates = pd.date_range(start='2023-01-01', periods=100, freq='D')
categories = ['Electronics', 'Clothing', 'Groceries', 'Furniture']

data = {
    'Date': np.random.choice(dates, 200),
    'Category': np.random.choice(categories, 200),
    'Sales Amount': np.random.randint(100, 1000, 200),
    'Units Sold': np.random.randint(1, 20, 200)
}

df = pd.DataFrame(data)
df['Date'] = pd.to_datetime(df['Date'])
print(df.describe())

plt.figure(figsize=(12, 6))
line_data = df.groupby('Date')['Sales Amount'].sum().reset_index()
sns.lineplot(data=line_data, x='Date', y='Sales Amount')
plt.title('Sales Trend over Time')
plt.xlabel('Date')
plt.ylabel('Total Sales')
plt.xticks(rotation=45)
plt.show()

plt.figure(figsize=(10, 5))
bar_data = df.groupby('Category', as_index=False)['Sales Amount'].sum()
sns.barplot(data=bar_data, x='Category', y='Sales Amount', palette='viridis')
plt.title('Total Sales by Category')
plt.xlabel('Category')
plt.ylabel('Sales Amount')
plt.show()

plt.figure(figsize=(10, 5))
sns.histplot(df['Sales Amount'], bins=20, kde=True, color='blue')
plt.title('Distribution of Sales Amounts')
plt.xlabel('Sales Amount')
plt.ylabel('Frequency')
plt.show()

plt.figure(figsize=(10, 5))
sns.scatterplot(data=df, x='Units Sold', y='Sales Amount', hue='Category', palette='coolwarm')
plt.title('Sales Amount vs Units Sold')
plt.xlabel('Units Sold')
plt.ylabel('Sales Amount')
plt.show()



5.Apply the What-If analysis for data visualization design & generate yearly report from the data where have data use Excel.

Step 1
Open Microsoft Excel.
Step 2
Create a simple table with data
Example:
Year	Units Sold	Price	Total Sales
2022	100	50	
2023	120	50	
2024	150	50	
Step 3
Calculate Total Sales.
In the Total Sales column type the formula:
=Units Sold * Price
Example:
=B2*C2
Press Enter and copy the formula for other rows.
Step 4
Select the Total Sales values.
Step 5
Go to the Data tab in Excel.
Step 6
Click What-If Analysis in the Data Tools group.
Step 7
Select Scenario Manager.
Step 8
Click Add to create a new scenario.
Example scenarios:
Scenario 1 → Sales Increase 10%
Scenario 2 → Sales Increase 20%
Scenario 3 → Sales Increase 30%
Choose the changing cell (Units Sold or Price).
Step 9
Enter new values for each scenario and click OK.
Step 10
Click Show to view the result of each scenario.
Excel will automatically calculate the new Total Sales.
Generate Yearly Report
Step 11
Select the entire data table.
Step 12
Go to Insert → Charts.
Choose a chart like:
Column Chart
Line Chart
Step 13
Excel will display a yearly sales visualization report.





7A.Import data warehouse data in an Excel. Create the pivot table
#Using Microsoft Excel
Step 1
Open Microsoft Excel.
Step 2
Click Data tab.
Step 3
Click Get Data.
Step 4
Select From Database.
Step 5
Choose From SQL Server Database.
Step 6
Enter:
Server Name
Database Name
Click OK.
Step 7
Select the data warehouse table you want.
Click Load.
Create Pivot Table
Step 8
Select the imported data.
Step 9
Go to Insert tab.
Step 10
Click Pivot Table.
Step 11
Choose:
New Worksheet
Click OK.
Step 12
Drag fields in Pivot Table Fields:
Rows → Category / Product
Columns → Year / Region
Values → Sales / Revenue
Pivot Table will be created.

7B.Import data warehouse data in an Excel. Create the pivot table
#Using Power BI
Steps
Step 1
Open Power BI Desktop.
Step 2
Click Get Data.
Step 3
Select SQL Server.
Step 4
Enter:
Server name
Database name
Click OK.
Step 5
Select the data warehouse table.
Click Load.
Create Pivot Style Table (Matrix)
Step 6
Go to Report View.
Step 7
Select Matrix visual.
Step 8
Drag fields:
Rows → Product / Category
Columns → Year
Values → Sales / Revenue
 

8.Import the data warehouse in MS. Perform visualization on any sales data

Step 1
Open Microsoft Excel.
Step 2
Go to the Data tab on the top menu.
Step 3
Click Get Data.
Step 4
Select From Database.
Step 5
Choose From SQL Server Database (or the database used).
Step 6
Enter the Server Name and Database Name.
Click OK.
Step 7
Select the sales data table from the data warehouse.
Click Load.
The data will be imported into the Excel sheet.
Creat Visualization (Chart)
Step 8
Select the sales data table.
Step 9
Go to the Insert tab.
Step 10
Choose a chart type such as:
Column Chart
Bar Chart
Line Chart
Pie Chart
Step 11
Excel will automatically create a sales visualization chart.
Step 12
Add a chart title like:
Sales Data Visualization


12.To perform Power Query – Sales data.

Step 1
Open Microsoft Excel.
Step 2
Click the Data tab on the top menu.
Step 3
Click Get Data.
Step 4
Choose the source of sales data:
From File → From Excel Workbook
or
From File → From Text/CSV
Step 5
Select the Sales Data file from your computer.
Click Open.
Step 6
A preview window will appear.
Click Transform Data to open Power Query Editor.
Step 7
Clean the sales data using Power Query tools:
You can do actions like:
Remove unwanted columns
Remove duplicate rows
Change column data type
Filter data
Rename columns
Step 8
After cleaning the data, click Close & Load.
Step 9
The cleaned sales data will be loaded into Excel sheet.
