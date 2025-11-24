# datawarehouse
The flow of the data:

Source -> Bronze Layer -> Silver Layer -> Gold Layer

Bronze Layer:
The Bronze layer will have the raw, unprocessed data as if the source
Purpose: Traceability and debugging
Object type: Tables
Load Method: Full Load (Truncate and Insert)
Data Transformation: No Transformation
Data Manipulation: None
Target Audience: Data Engineer


Silver Layer:
The Silver layer will have the clean and unstandarized data
Purpose: prepare data for analytics
Object type: Tables
Load Method: Full Load (Truncate and Insert)
Data Transformation: Data clean, standarization,normalization
Data Manipulation: None
Target Audience: Data Engineer,Data Analysts


Gold Layer:
The Gold layer will have the business ready data
Purpose: provide data to be consumed for reporting and analytics
Object type: views (virtual)
Load Method: No
Data Transformation:Data integration,data aggregation, business logic and rules
Data Manipulation: Star schema, Aggregated Object, flat tables
Target Audience: Data Analysts, Business Users


Separation of Concerns (SOC)
There must be difference between the responsibilty of one layer to another.


Naming conventions: Set of rules for naming => snake_case
Bronze and Silver: <souressystem>_<entity>. If source system is present example: crm_customer_info
Gold Layer:<category>_<entity>. Ex: dim_customer(dimensions), fact_sales(fact)
