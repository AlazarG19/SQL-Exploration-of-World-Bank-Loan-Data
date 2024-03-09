# **SQL Exploration of World Bank Loan Data**
This project aims to conduct a comprehensive analysis of the World Bank's loan data using SQL queries. The World Bank provides extensive financial information about its loans to various countries for diverse development projects.

With an ever-growing volume of financial data related to loans granted for diverse development projects across countries, there is a critical need to harness the power of SQL queries for systematic exploration and analysis.

The primary challenge is to design and implement SQL queries capable of extracting pertinent information from the dataset. These queries should cover a spectrum of analytical dimensions, including temporal trends, regional patterns, risk assessments, and comparative analyses among countries and sectors

## Objectives
#### Data Retrieval 
Retrieve the World Bank Loan dataset from the data_worldbank.csv file that is stored in csv format

#### Data Cleaning
Cleaning the dataset to address missing,inconsistent,duplicate
#### Data Prepartion and Column Transformation 
Preparing dataset for analysis by removing any unnecessary columns and renaming some columns to improve calrity and consistency.
#### Data Conversion and Export
Converting different colummns to their appropriate format 
#### Importing Data to Database and Creating Database Conneciton
Importing data to sql inorder to make the analysis.
#### Trend Analysis
Identifying and analysing trends in World Bank Loan Distribution over time and exploring patterins in loan allocation across different regions and sectors
## Dataset
The dataset, sourced from the World Bank's comprehensive financial records, provides a detailed overview of international development loans. With a focus on lending activities across countries, this dataset encompasses a range of critical information related to loans granted for diverse projects. The dataset is structured with the following columns:

__End of Period__:

Indicates the closing date of the period for which the financial data is reported.

__Credit Number__:

A unique identifier assigned to each credit, facilitating traceability and reference.

__Region__:

Categorizes the geographical region to which the country belongs, offering insights into continental or regional trends.

__Country Code__:

A standardized code representing the specific country in the dataset.

__Country__:

The name of the country for which the loan data is recorded, providing the context for the financial transactions.

__Credit Status__:

Describes the current status of the credit, indicating whether it is active, cancelled, or completed.

__Project ID__:

A unique identifier associated with each development project, connecting the loan to its intended purpose.

__Project Name__:

The name or title of the development project associated with the loan.

__Original Principal Amount (US$)__:

Represents the initial loan amount disbursed for the project in US dollars.

__Cancelled Amount (US$)__:

Indicates the amount of the loan that has been cancelled or voided.

__Undisbursed Amount (US$)__:

The remaining loan amount that has not yet been disbursed for the project.

__Disbursed Amount (US$)__:

Reflects the total amount of the loan that has been disbursed to date.

__Repaid to IDA (US$)__:

The amount repaid to the International Development Association (IDA), a part of the World Bank Group.

__Due to IDA (US$)__:

Represents the outstanding amount due to the International Development Association.

__Borrower's Obligation (US$)__:

The total financial obligation of the borrowing country, including the principal amount and any outstanding repayments.

__Board Approval Date__:

The date on which the project and associated loan received approval from the governing board.

__Effective Date (Most Recent)__:

Indicates the most recent date on which the loan became effective, marking the commencement of project activities.

## Tools 

We'll be using the the library pandas from the python function to facilitate data manipulation and perform inital assessment of the dataset's strucutre. Once that is complete We'll be using mysql to formulate SQL queries to extract relevant information for trend analysis. 

## Approach
#### Data Import and Initial Exploration
In data analysis, the initial step of importing a dataset and exploring its initial content is akin to opening a door to valuable insights. This is essential because it allows us to ensure we have the right data foundation for uncovering key information and patterns in the context of our project.

#### Identifying Duplicate Data

In this step, we aim to identify and quantify the presence of 
duplicate data within our dataset. The count of duplicates 
(referred to as 'duplicates' in the code) is an important metric. It helps us understand the extent of redundancy in our dataset, which is crucial for data quality and accuracy in our analysis. By recognizing and handling duplicate records, we ensure that our insights and conclusions are based on unique, meaningful data, preventing any potential distortions caused by repeated entries.


#### Removing Duplicate Data
In this step, we are removing duplicate data from our dataset by utilizing the drop_duplicates function with the inplace=True parameter. Duplicate data can introduce noise and inaccuracies into our analysis, and removing them ensures that we work with unique and non-repetitive records. This process improves the quality and reliability of our data, setting the stage for more accurate and meaningful insights.


#### Identifying Missing Data¶
Here, we're examining our dataset for missing values, indicated by 'null' values. The 'null_values' variable holds the count of missing data points for each column. Identifying and quantifying missing data is crucial as it helps us understand the completeness of our dataset. Dealing with missing values appropriately is essential for accurate analysis and decision-making. By knowing the extent of missing data, we can take measures to handle them effectively and ensure the reliability of our results.



#### Handling Missing Data
In this step, we're addressing missing data in specific columns, namely 'Board Approval Date' and 'Effective Date (Most Recent).' We use the dropna function with the subset parameter to remove rows with missing values in these columns, setting inplace=True. Handling missing data is crucial to maintain data integrity and accuracy in our analysis. By removing rows with missing values in these specific columns, we ensure that the dataset remains reliable and complete for our subsequent analysis.


#### Data Preparation and Column Transformation
In this step, we are preparing the dataset for analysis. We remove unnecessary columns and rename some columns to improve clarity and consistency. This ensures that the dataset is optimized for our analysis, making it more concise and easier to work with in the next stages of our project.



#### Data Conversion and Export
In this step, we are converting date columns to the appropriate datetime format. This is essential for accurate date-based analysis. After the conversion, we export the cleaned dataset to a CSV file for future use and verify the data types to ensure they are in the correct format.



### Trend Analysis
Once we've prepared our data, we'll use sql to analyse any patterns within the data
#### Data Import and Database Connection
We'll start by loading sql libraries and connecting to the sql.
In order to load the data we'll have to use MySQLWorkbench. we'll first login into our Local instance. Once that is complete, we'll have to create a new schema to hold our new table. after the schema is created, use the table data import wizard to load the data into the csv. During the import, MYSQL Workbench will prompt the data type of each dataset. During this process, select the appropriate data types such as datetime , double , string to the needed attributes.

#### Creating the Database Connection
in the next step we create our database connection using the pymysql library


### Asking questions to uncover patterns
We start our analysis by asking questions relevant to the topic

#### Q1: How Many Countires in the world bank have loans


#### Q2: Calculating Total Loan Amount for Each Project

In our analysis of World Bank loan data, we calculate the total loan amount for each project to understand the financial scope of individual initiatives. This helps in prioritizing projects, allocating resources effectively, and making informed budgeting and decision-making decisions, ensuring efficient project management and financial planning.


#### Q3: Calculating Total Original Principal Amount for All Projects

In our analysis of World Bank loan data, the task is to determine the total original principal amount for all projects. This calculation provides an essential snapshot of the combined financial commitment across all projects, offering insights into their overall financial scale. This information is valuable for budgeting, resource allocation, and understanding the collective financial impact of World Bank initiatives, aiding in informed decision-making and financial planning.


#### Q4: Calculating Average Repaid to IDA for Each Region

In our analysis of World Bank loan data, we calculate the average amount repaid to the International Development Association (IDA) for each region. This task is valuable as it allows us to assess the regional repayment performance and financial sustainability of IDA projects.. These insights can guide decisions related to funding allocation and project prioritization.



#### Q5: Identifying Country with Highest Repaid to IDA Ratio

In our World Bank loan data analysis, we aim to find the country with the highest ratio of repaid amounts to the International Development Association (IDA) compared to the original principal amounts. We focus on projects with a "Fully Repaid" credit status. This task provides insights into effective loan management and highlights countries with successful repayment strategies.



#### Q6: Counting Projects by Credit Status for Each Country

In our analysis of World Bank loan data, we aim to determine, for each country, the number of projects with different credit status values, such as "Active," "Fully Repaid," "Cancelled," and others. This task provides a comprehensive view of the distribution of projects across various credit statuses within each country, enabling us to assess the progress and status of projects. This information is essential for tracking project performance and managing the diverse range of projects effectively.



#### Q7: Counting Countries with World Bank Loans by Region

In our World Bank loan data analysis, we count the number of countries within each region that have received loans from the World Bank. This task offers insights into regional lending distribution and the scope of World Bank financial support across different regions. Understanding this distribution is vital for regional financial assessment and decision-making.


#### Q8: Counting Fully Repaid Projects by Region

In our analysis of World Bank loan data, we calculate the total number of fully repaid projects (where "Credit Status" equals 'Fully Repaid') for each region. This task allows us to assess the success of repayment within various regions. By utilizing the provided query, we group the data by region and sum the projects with a "Fully Repaid" credit status. This information provides valuable insights into regional project performance and financial sustainability within the World Bank ecosystem, aiding in regional decision-making and resource allocation.


#### Q9:  Identifying Projects with the Highest "Due to IDA"

In our World Bank loan data analysis, we're searching for projects with the highest "Due to IDA" amounts. We also want to determine the corresponding "Country" and "Effective Date" for these projects. This task helps us identify projects with significant financial commitments to the International Development Association (IDA), providing insights into impactful projects and their financial details.


#### Q10: Identifying Top 5 Countries with Highest Repaid to Principal Ratio

In our World Bank loan data analysis, we aim to find the top 5 countries with the highest "Repaid to IDA" to "Original Principal Amount" ratio for projects that are not fully repaid. This task reveals countries with efficient loan repayment strategies and is essential for financial assessment and sharing best practices.



#### Q11: Identifying Top 5 Countries with the Highest Total Loan Amount

In our World Bank loan data analysis, we're focused on determining the top 5 countries with the highest total loan amounts. This task is essential to understand the countries with significant financial commitments. By employing the provided query to sum the "Original Principal Amount" and subtract the "Cancelled Amount," we calculate the total loan amount in billions for each country. This information provides insights into the financial scale of World Bank loans in different countries, guiding resource allocation and financial assessment.



#### Q12:  Identifying Top 5 Countries with the Highest Due Amount

In our World Bank loan data analysis, we aim to determine the top 5 countries with the highest "Due to IDA" amounts. This task is crucial to understand the countries with significant outstanding obligations to the International Development Association (IDA). By utilizing the provided query to sum the "Due to IDA" amounts for each country, we gain insights into countries with substantial financial commitments. This information is essential for financial assessment and tracking outstanding financial obligations.

## Visualizing the data

Visualizing this data is crucial for several reasons:

__Interactive Exploration__

Power BI offers interactive dashboards and reports that allow users to explore the data dynamically. With just a few clicks, stakeholders can drill down into specific regions, projects, or time periods to uncover insights and trends.

__Comprehensive Analysis__

Power BI provides a wide range of visualization options, including charts, graphs, maps, and tables. These visualizations allow analysts to conduct comprehensive analyses of the World Bank's loan data.

__Storytelling__

Power BI enables users to create compelling data stories by combining visualizations, text, and images into interactive presentations. This storytelling approach helps convey key insights and recommendations to stakeholders in a clear and engaging manner.

