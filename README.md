# Homework-1

## Business Problem 
Mei Real Estate Analytics is a data-driven firm seeking to empower real estate professionals. Operating in the dynamic real estate landscape of New York City, our mission is to provide our clients, including investors, developers, and financial institutions, with the tools and information needed to make strategic decisions and thrive in the competitive market. 

### Purpose: Optimizing Investment Strategy for Real Estate Portfolios
Requirements: 
1. Ensure the accuracy and reliability of the NYC Annualized Property Sales dataset
2. Build a scalable data pipeline capable of handling large datasets to accommodate future market data and growth
3. Develop an intuitive and user-friendly Tableau dashboard that allows real estate professionals to easily interpret and derive insights from the presented visualizations.

Missing Requirements:
1. As noted early, ensuring the reliability and accuracy of the system is paramount. While the importance of testing is recognized, the exact testing scenarios, benchmarks, and standards to be employed are not explicitly outlined.

## Business Impact
### Risks: 
* *Data Accuracy and Reliability*: Inaccuracies in the dataset may lead to flawed investment decisions. Implementing thorough data validation processes mitigates this risk.
* *Regulatory Compliance*: Failure to adhere to real estate regulations may result in legal consequences. Regular compliance checks and updates are vital to managing this risk.

### Costs: 
* *Initial setup*: Establishing the data pipeline, developing the Tableau dashboard, and implementing real-time updates entail initial costs.
* *Maintenance*: Ongoing maintenance, data pipeline updates, and server costs contribute to the total cost of ownership.

### Benefits: 
* *Informed Decision-Making*: Real estate professionals gain valuable insights for strategic decision-making, leading to optimized investment strategies.
* *Maximized Returns*: Targeting high-value boroughs and strategic timing of investments can result in maximized returns for investors.

## Business Persona:
* Users: Real estate Analysts, Property Investors, Executives and Decision-Makers
* Actors: Data Engineer, Dashboard Developer, Compliance Officer, IT Support 

## Data Sources
[NYC Citywide Annualized Calendar Sales Update](https://data.cityofnewyork.us/City-Government/NYC-Citywide-Annualized-Calendar-Sales-Update/w2pb-icbu): This data set was obtained from NYC Open Data using a web API. 

The API endpoint used for data extraction is https://data.cityofnewyork.us/resource/w2pb-icbu.json. Python was used to connect to the API and retrieve the data, which was then organized and stored in a Pandas DataFrame for further analysis. 

To access Python script used to source the data, click [here.](Scripts/HW1.py)


## Data Dictionary
You can access the source's data dictionary in the [Annualized_Calendar_Sales_Update_Data_Dictionary.xlsx](Annualized_Calendar_Sales_Update_Data_Dictionary.xlsx) repo file. To download the Excel file directly, click [here.](https://github.com/jmeiws/Homework-1/raw/main/Annualized_Calendar_Sales_Update_Data_Dictionary.xlsx)

#### Dataset Size:
The raw dataset contains approximately 600,000 records. 

#### Strengths:
1. Rich information: The dataset provides a wealth of information about property sales, including sale prices, locations, tax classes, and transaction dates.
2. Historical trends: The dataset's historical nature allows for the analysis of trends over time, enabling users to identify patterns and make informed predictions.

#### Weaknesses: 
1. Data Quality: There exists a decent number of incomplete/inaccurate data entries that may compromise the overall quality of analyses and predictions. This calls for format standardizaiton in columns such as Borough, Address, etc. 
   * Example: Columns like residential_units containing 0, empty values, etc
2. Missing Descriptions: Some column names are hard to comprehend, as they do not appear in the source's provided data dictionary.

## Data Tools: 
* Data dictionary: Excel
* Dimensional Modeling: DbSchema
* Data Storage and Data Warehouse: AWS (Amazon S3 , Amazon Redshift Serverless)
* Data Extraction: Python
* Data Cleaning/Transformations: dbt Cloud
  * For automating our data pipeline, dbt Cloud allows for scheduled runs for orchestrated data transformations.
* Serving Data: Tableau 

## Methods
workflow: gather data -> dbSchema DM -> load into cloud -> create Redshift cluster -> apply dbSchema to Redshift -> insert data from S3 to Redshift -> set up dbt for cleaning and transformations -> data viz 


    




