# Business Intelligence

If only this will make me more intelligent…

## Chapter 1

### What is Business Intelligence?

Business Intelligence is the technologies that transform the data of a business into meaningful information and provide guidance on the actions it can take to achieve its business goals.

BI is not a single tool or methodology. It is an umbrella term which encompasses various tools and methods that can make data useful to business.

### Why use BI?

- Cut costs
- Increase profit
- Provides easy to read formats such as reports and data visualizations
- Make business decisions more accurately and more speedily
- Prevent “Data Rich, Information Poor”

### What can BI do for businesses

- Handle large amount of data
- Provide Historical, Current and Predictive views of business operations
- Support both Operational (Short Term) and Strategic (Long Term) business decisions
  - Operating decision includes product positioning and pricing
  - Strategic decisions include priorities or goals and directions

### 4 Main Purposes of BI

- Reporting 
  - track the key performance indicator (KPI) about their business in dashboards and reports.
- Investigative 
  - analyze and find out the reasons why a certain results is not as they expected
- Monitoring
  - keep updated in real-time about what is happening and be alerted when an anomaly happens
- Discovery / Predictive
  - make strategic decisions based on predictive recommendations by the BI engine or discover interesting trends that might open up new business opportunities

### 4 V of Big Data (Challenges)

- Volume
  - Scale of data
- Variety
  - Different forms of data
- Velocity
  - Analysis of streaming data
- Veracity 
  - Uncertainty of data

### 5 Components of BI Solution

1. Data Sources
   - Before a BI solution can be implemented, the BI team must identify the raw data that will be processed. This is often the transactional data captured by the company during its operations, e.g. Point-of-sales
2. Data Preparation
   - Cleaning of data
3. Data Warehouse
   - Loading the cleansed data into a central repository
4. Data Analytics
   - Performing analysis on the data using OLAP or data mining to discover useful patterns or relationships, which can be used to predict future behaviour
5. Data Presentation
   - Presenting of the insights from the  analysis in an easy-to-digest format using reporting / dashboard tools

### BI Process

1. Identify business issue
2. Formulate business questions
3. What information do I need
4. Where do I find the information
5. Retrieve information
6. Analyze Information
7. Report Answers
8. Take actions

# Chapter 2 Data Warehousing Fundamentals

### What is a Data Warehouse (DW)

DW is a very huge database specially designed to enable BI activities. Data stored in DW is uploaded from both internal operational system and external sources. DW keeps historical data which can be used to create annual / quarterly trends reports for management. 

DW integrate all of the company important data residing in different systems to a central location - With a SINGLE VERSON OF TRUTH.

A data warehouse is a subject-oriented, integrated, time-variant and non-volatile collection of data in support of management's decision making process

DW only involves 2 operations, the initial loading of data and access of data (read)

DW contains Summary Data, Metadata and Raw data. Raw data is data that has not been transformed, to the multi-dimensional format that is optimized for fast-response. Summary data is data that has been transformed, to the multi-dimensional format that is optimized for fast-response. Metadata is information about the data stored in the DW. E.g. Who can access the data, where is the source of the data etc.

DW uses Multidimensional Data Model instead of ER model to store its data. Multidimensional data model views data in the form of a data cube

### Characteristics of DW

- Subject-Oriented
  - Organized around the subjects the business users are interested to analyse
- Integrated
  - Integrate data from heterogenous sources
  - Must ensure the data is consistent in format, naming and other aspects before integrating
- Non Volatile
  - Data in the DW will never be changed. (No updates or delete)
- Time Variant
  - DW keeps historical data

### Data Warehouse Architectures

- Centralized Data Warehouse (2 layers)
- Hub-and-Spoke (3 Layers)
- Independent Data Marts
- Data Mart Bus Architecture
- Federated Architecture

#### Centralized Data Warehouse

- Consists of 2 components
  - Data warehouse and staging area
- Staging area is used for cleansing and transforming before loading into DW

#### Hub and Spoke

- Consists of 3 components
  - DW, Staging area and several Data Marts
- End-user does not query the DW directly, they queries the data marts
- Data marts contain subsets of data tailored for a specific line of business. e.g. sales data mart is for sales related queries

#### Independent Data Marts

- Consists of Staging area and several independent Data Marts
- Absence of central DW to control data structure compliance, hence each data mart diff from another
- Analytic tools query data directly from data mart and present information to user

#### Data Mart Bus Architecture

- Consists of Staging Area and several dimensional Data Marts
- Absence of central DW
- Each Dimensional data marts conforms to an agreed set of dimensions at the enterprise level
- AKA Kimball Bus Architecture

#### Federated Architecture

- Existing structures are left in place
- A single Database is set up to act as a federated database server which receive requests from users, get the data from different data sources and return the results to the users.

### Staging Area

- Temporary location where data from source system resides
- May exist for timing reason; due to varying business cycle, data processing cycles, hardware and network resource limitations and geographical factors, cannot extract data at same time.

### Data Mart

- Simple form of DW that is focused on a single subject
- Often built and controlled by a single department within an organization
- Usually draw data from only a few sources specific to the needs of the department who initiated it

### ETL (Extract-Transform-Load)

- Important component of Data Warehousing Architecture
- The process that enables data to be transferred from Operational Applications to the Staging Area, to the DW and finally from DW into a set of Data Marts
- Also the process that transform data to the format that is eventually useful to the business user. (Data cleansing, filtering, loading)

### Data Marts Architecture

- Dependent 
  - Data Marts draws data from a central data warehouse that has already been created
  - Data is derived from the enterprise data warehouse
  - Data in the dependent data mart is reshaped and restructured into a form that very specifically meets the needs of the end user
  - Data marts are not separate databases. but logical views of the data warehouse
- Independent
  - Data Marts are standalone systems built by drawing data directly from operational or external sources of data or both
  - Focuses on 1 subject area, not designed in an enterprise context
  - Manufacturing and HR has their own Data Mart etc.
  - Gets data from multiple transaction systems in one subject area or department to support specific business needs

### Data Warehouse vs Data Marts

| **Category**                  | **Data Warehouse** | **Data Mart**    |
| ----------------------------- | ------------------ | ---------------- |
| **Scope**                     | Corporate          | Line of Business |
| **Subject**                   | Multiple           | Single           |
| **Data   Sources**            | Many               | Few              |
| **Size   (Typical)**          | 100 GB-TB+         | <100GB           |
| **Implementation**   **Time** | Months to years    | Months           |

### Why use Data Marts

- Lower the risk for companies as it can be implemented in a much shorter time and with less financial resources
- Give right user the right access to the right data
- Provide data in the desired form that matches the collective view of data by a group or users in a department or business function
- Improve end-user response time

### Active Data Warehouse (ADW)

- Specialized form of data warehouse that can support near real-time data insights
- Support BI reports used by Operational staff
- Lag time between transfer between operational data sources to the data warehouse is much shorter
- System is able to response to real-time business events as they occur, completing complex analyses upon demand, and alerting people or systems to take action
- Closed loop system: Events are analyzed as they occur, and intelligent decisions are promptly initiated
- Allows an organization to automatically respond to opportunities with agility, often without the need for human intervention
- Used by operational staff to make real-time operational decisions
  - Cross selling by Customer Service Representatives
  - Point-of-sale fraud detection
  - Personalized next best offer on web sites
  - Retail out of stock monitoring on promotional items
  - Labor and crew scheduling
  - Dynamic pricing and yield managament
  - Real-time manufacturing line quality alerts

### OLTP (On-line Transaction Processing)

- Designed to capture and store data related to day to day business such as ERP, CRM, SCM, POS and for increasing the efficiency of an organization
- Characteristics
  - Involves a large number of short on-line transactions (insert, update, delete)
  - Requires data integrity in multi-access environments
  - Stores current data
  - Uses the 3NF (Third-Normal-Form) Schema

### OLAP (On-line Analytical Processing)

- Designed to facilitate analysis of business data and increase effectiveness of organization
- Characteristics
  - Involves a relatively low volume of transactions
  - Requires ability to store large amounts of data and to handle complex queries
  - Contains aggregated. historical data
  - Uses multi-dimensional schemas such as Star Schema, Snowflake Schema

|                                               | **Transactional database**                | **Data warehouse**                                           |
| --------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------ |
| **Support what system?**                      | Support   OLTP systems                    | Support   OLAP systems                                       |
| **How current is data?**                      | Holds   current data   (30 days - 1 year) | Holds   historic   data (up to 10 years)                     |
| **Granularity?**                              | Stores   detailed data                    | Stores   summarized data                                     |
| **How often does data change?**               | Data   is dynamic and real-time update    | Data   is largely static and periodic update                 |
| **What**   **is the data volume it stores?**  | In   hundreds of gigabytes                | In   hundreds of terabytes or [petabytes](http://www.whatsabyte.com/) |
| **What Data Model / Schema does** **it use?** | Entity-Relation Model in 3NF              | Dimensional   model in denormalized format                   |

|                                     |                                              |                                            |
| ----------------------------------- | -------------------------------------------- | ------------------------------------------ |
| **What decisions does it support?** | Supports   day-to-day (short-term) decisions | Supports   strategic (long-term) decisions |
| **What is it optimized for?**       | Optimised   for transactions                 | Optimised   for query performance          |
| **What is it structured for?**      | Structured   for data integrity              | Structured   for ease in querying          |
| **What is its pattern of usage**    | Predictable   pattern of usage               | Unpredicted   pattern of usage             |

### Requirements of DW

- Load performance
- Load processing
- Data quality
- Query performance
- Volume of data
- Multi-user accessing
- Networked DW
- Dimensional Support
- Warehouse administration

### Reasons for a DW

- Reduce stress on production system
- Faster return of query results
- Integrate many sources of data
- Provide historical intelligence
- One version of truth
- Improve data quality
- Easier to create reporting solutions on it
- High ROI (Return on Investment)

## Chapter 3 Dimensional Modelling for DW

### Dimensional Modelling

- Logical design technique to present data in a framework that is intuitive and allows for high performance access
- Uses relational model but with some modifications
- Every DM consists of a table with a multi-part key called the Fact table and a set of smaller tables called Dimension tables
- Fact table contains measurements called metrics that the users want to capture. They are numeric and can be added up
- Dimension tables are descriptive textual information that capture the attributes of the Dimension
- DM Modelling must include 1 Dimension called Time Dimension
- Dimension tables are entry points into the data warehouse
- The DM produces a star-like structure called a star join

| **Entity-Relationship** **Modelling**                        | **Dimensional** **Modelling**                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Main goal is to remove redundancy from data    •Contains   normalized   data   •High transaction performance   •High data integrity | Main goal is to have high performance of retrieval of data    •Contains   denormalized data   •High query performance |
| Models the relationships among data   •Structures   data from the point of view of a technical user   – harder to understand by a layman   •Involves data rules | Models a business   •Structures data from the point of view of a   business user – easy to understand   •Involves business rules |

### What is a Dimensional Model

- A DM is a database design intended to support end user queries in a data warehouse
- Designed to be easily understood and for high query performance
- Dimensional Modelling uses the concepts of facts and dimensions
- “Facts” are numeric values that a business wishes to count or sum, E.g. Sales, Quantity
- “Dimension” are values that capture information that is of interest to the business, E.g. Customer Name, Product Name, Product Category, Date of Order

### Star Schema

- Simple database design in which dimensional data are separated from fact or event data
- Consists of 2 types of tables: Fact tables and Dimension tables
- Highly de-normalized set of tables
- Query results come back faster due to less JOIN statements in SQL
- Fact table store factual data and the Dimension tables store reference data
- Each dimensional model is made up of
  - At least 1 fact table with a multi-part (composite) key
  - a set of smaller table called dimension tables
- Each dimension table has a single-part primary key that corresponds exactly to one part of the multi-part key in the fact table
- A fact table can be extremely large relative to a dimension table

#### Fact tables

- has a many-to-one relationship to the dimension table
- primary key is multi-part
- has many more rows than those in the dimension tables
- contains primarily numeric data (aka measures) and very few character data

#### Dimension tables

- has one-to-many relationship to fact table
- primary key is single-part
- fewer rows than fact tables
- contains primarily character data

### Snowflake Schema

- Expanded version of a star schema in which dimension tables are normalized into several related tables
- Characteristics
  - Result of either business environment or third-party application or design which cannot be implemented by a star schema
  - Dimension tables are of 2 types: primary and secondary
  - Primary dimension tables are joined to the fact table
  - Secondary dimension are joined to the primary dimension tables
  - It can increase query performance if the users are accessing data stored in the primary dimension tables 80% of the time
  - Snowflake schema may need a number of joins to apply a specific textual constraint to a query

| **Advantages**                                               | **Disadvantages**                                            |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| •Small   savings in storage space   •Normalized   structures are easier to maintain and update   •   • | •Schema   is less intuitive   •More   difficult to browse through the content   •Degraded   query performance because of additional JOINs |



|                                              | **Star schema**                                              | **Snowflake Schema**                                         |
| -------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **How   easy it is to understand the model** | Easier                                                       | More   difficult                                             |
| **Number   of tables**                       | Few                                                          | More                                                         |
| **Query   Complexity**                       | Easy   to construct as there are less tables and hence fewer joins are required | More   complex because there are more tables and hence more joins are required |
| **Query   Performance**                      | Quicker   to access textual values because of fewer joins    | Slower   to access textual values because of more joins      |

### Dimension Hierarchies

- A hierarchy is a logical structure that uses ordered levels to aggregate data (consolidate related data under one group)
- E.g. in a Time dimension, a hierarchy can be used to aggregate data from the Month level to the Quarter level, from the Quarter level to the Year level

### Steps in designing a Star Schema

1. Choose a business process to model, e.g. Sales
2. Choose the grain (lowest level of summary) of the Fact table
3. Identify the dimension for each fact record (Product, Location, Time dimension)
4. Identify the numeric measures or facts (Sales Total) that is at the level of the chosen grain
5. List the columns that describe each dimension (E.g. product name, product brand)

### Surrogate Keys

- A system generated attribute is added to each entity type table and made the primary key. This attribute is often an artificial number. The primary key for each relationship table consists of identifiers from the related entity types

### Natural keys

- A unique combination of application attributes is used to identify each entity. The primary key for each relationship table consists of primary keys from the related entity types
  - The natural keys can be used as candidate keys in the dimensions to facilitate the ETL process

### Why use Surrogate Keys

- **Natural keys (NK)** or **Business keys** are generally alphanumeric values that is not suitable for index as traversing become slower. For example, prod123, prod231 etc
- Business keys are often reused after sometime. It will cause the problem as in data warehouse we maintain historic data as well as current data.
- For example, product codes can be revised and reused after few years. It will become difficult to differentiate current products and historic products. To avoid such a situation, surrogate keys are used.

### 3 Types of Fact tables

- Transaction Grain
  - Measured facts are valid only for that instant and for that event. The next measurement event could happen one millisecond later or next month or never
  - Grocery store beep is a transaction grain
  - Unpredictably sparse or dense
- Periodic Snapshot Grain
  - Corresponds to a predefined span of time, often a financial reporting period.
  - The measured facts summarize activity during or at the end of the time span.
  - Carries a powerful guarantee that all reporting entities will appear in each snapshot even if there is no activity
  - Predictably dense
- Accumulating Snapshot Grain
  - Corresponds to a predictable process that has a well-defined beginning and end. Order processing, claims processing are typical candidates
  - Accumulating snapshots records are revisited and overwritten as the process progress through its steps from beginning to end
  - Generally smaller than the other 2 types

### Advantages of DM

- Predictable standard framework
- Can withstand unexpected
- Adding new unanticipated facts as long as they are consistent with the fundamental grain of the existing Fact table
- Adding completely new dimensions, as long as a single value of that dimension is defined for each existing fact record
- Adding new unanticipated dimension attributes
- Breaking existing dimension records down to lower level of granularity form a certain point in time forward

### 10 Essential Rules to DM

1. Load detailed atomic data into dimensional structures
2. Structure dimensional models around business processes
3. Ensure that every fact table has an associated date dimension table
4. Ensure that all facts in a single fact tables are at the same grain or level of detail
5. Resolve many-to-many relationships in fact tables
6. Resolve many-to-one relationships in dimension tables
7. Store report labels and filter domain values in dimension tables
8. Make certain that dimension tables use a surrogate key
9. Create conformed dimensions to integrate data across the enterprise
10. Continuously balance requirements and realities to deliver a DW/BI solution that is accepted by business users and that supports their decision-making



## Chapter 4 OLAP (Online Analytical Processing)

### What is OLAP

OLAP is the technology that enables business users to perform multidimensional analysis of large volumes of business data easily

### How OLAP works

- Precompute the totals and subtotals need for reporting during idle time (e.g. non-business hours)
- The totals are stored in a special database called an OLAP cube
- OLAP cube does not have to loop through transactions because totals are all pre-calculated, proving instant access

### OLAP Cube

- Multi-dimensional data structure that allows fast-analysis of data
- Capable of efficiently manipulating and analyzing data from multiple perspectives
- Consists of measures and dimensions
  - Measures are numeric values that businesses typically track e.g. Revenue
  - Dimensions are values that identify and categorize the data, e.g. Product, Time, Geography
  - Dimension can be organised as a hierarchy, e.g. data stored in the Time dimension such as 01 Dec 2014 can be sub-categorised into Year (2014), Month (Dec), Day (01), Quarter (4) etc

### 5 Basic OLAP Operations

- Slice
  - Apply a filter on one dimension to create a slice of data
- Dice
  - Apply a filter on two dimensions to create a smaller cube (subset)
- Drill-down
  - Display detailed information (opposite of roll-up)
- Roll-up
  - Display aggregated information (opposite of drill-down)
- Pivot (Rotate)
  - Rotate the cube (switch the axes)

### Variations of OLAP

- MOLAP (Multidimensional OLAP)

  - More traditional way where data is stored in multidimensional cube

  - Storage not in relational database, but in proprietary formats

  - [^]: Components of MOLAP tool

    ![1558762856931](C:\Users\ChoonSiang\AppData\Roaming\Typora\typora-user-images\1558762856931.png)

  - 

  - | **Advantage**                                                | **Disadvantage**                                             |
    | ------------------------------------------------------------ | ------------------------------------------------------------ |
    | Excellent performance: MOLAP cubes are built for fast data   retrieval, and are optimal for slicing and dicing operations. | Limited in the amount of data   it can handle: Because all calculations are performed   when the cube is built, it is not possible to include a large amount of data   in the cube itself. |
    | Can perform complex   calculations:      All   calculations have been pre-generated when the cube is created. Hence, complex   calculations are not only doable, but they return quickly. | Requires additional investment:      Cube   technology are often proprietary and do not already exist in the   organization. Therefore, to adopt MOLAP technology, chances are additional   investments in human and capital resources are needed. |

- ROLAP (Relational OLAP)

  - Manipulates the data stored in the relational database to give the appearance of traditional OLAP’s slicing and dicing functionality

  - Each action of slicing and dicing is equivalent to adding a “WHERE” clause in the SQL statement

  - [^]: Components of ROLAP tool

    ![1558762906409](C:\Users\ChoonSiang\AppData\Roaming\Typora\typora-user-images\1558762906409.png)

  - 

  - | **Advantage**                                                | **Disadvantage**                                             |
    | ------------------------------------------------------------ | ------------------------------------------------------------ |
    | Can handle large amounts of data: The data size limitation of ROLAP   technology is the limitation on data size of the underlying relational   database. In other words, ROLAP itself places no limitation on data amount | Slow performance: ROLAP   gives the poorest query performance because no objects benefit from   multidimensional storage |
    | Can leverage functionalities   inherent in the relational database:      Often,   relational database already comes with a host of functionalities. ROLAP   technologies, since they sit on top of the relational database, can therefore   leverage these functionalities | Limited by SQL functionality:      Since   ROLAP technology mainly relies on generating SQL statements to query the   relational database, ROLAP technologies are limited by what   SQL can do. Vendors   enhance their SQL engines to overcome this problem |

- HOLAP (Hybrid OLAP, combination of MOLAP and ROLAP)

- SOLAP (Spatial OLAP)

- DOLAP (Desktop OLAP)



|                             | **OLTP**                                                     | **OLAP**                                                     |
| --------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Purpose**                 | Carry out day-to-day business   functions                    | Support   decision-making   and provide answers to business and management queries |
| **Data   Source**           | Transaction   database (Normalized data repository   focused on efficiency and consistency) | Data   warehouse or data mart (a non-normalized   data repository primarily focused on accuracy and completeness) |
| **Reporting**               | Routine, periodic, narrowly focused   reports                | Ad-hoc,   multi-dimensional,   broadly focused reports and queries |
| **Resource   Requirements** | Ordinary relational databases                                | Multi-processor, large capacity specialized   databases      |
| **Execution   Speed**       | Fast   (Recording of   business transactions and routine reports) | Slow   (Resource   intensive,   complex, large-scale queries) |



## Chapter 5 Data Integration and ETL Process

### What is ETL

- Process in data warehousing responsible for pulling data out of the source systems and placing it into a data warehouse
- Critical to a successful data warehouse
- Must ensure the data loaded into the data warehouse is high-quality, accurate, relevant, useful and accessible
- Most time consuming phase in building a data warehouse as routines must be developed to select the required fields from numerous sources of data
- Extract
  - Process of reading data from a source database
- Transform
  - Process of converting the extracted data from its previous form into the form it needs to be in so that it can be placed into another database
- Load
  - Process of writing the data into the target database

### Extract

- First phase of ETL
- Required data is identified and extracted from different sources
- Extracted data is then held in temporary storage (Staging Area) until the “Transform” and “Load” phases can be executed
- Validation rules are applied to test whether data has expected values essential to the data warehouse
- Data that fails the validation is rejected and further processed to discover why it failed validation and remediate if possible

### Transform 

- Fetch data from Staging Area and perform data cleansing on it to eradicate incorrect and corrupt values

- Apply transformation rules to the data to convert to a consistent format suitable for loading to the Data Warehouse

- Data Cleansing / Data Scrubbing is the process of detecting and correcting data anomalies to improve the quality of it

- Beside data cleansing, a series of rules or functions are also applied to the data

- Example of DIrty Data:

  |                              |                                                              |
  | ---------------------------- | ------------------------------------------------------------ |
  | **Incorrect** **Data**       | Data with values that are obviously incorrect, e.g. Age = 200 |
  | Inaccurate Data              | Data with   values that are correct but inaccurate e.g. Singapore Polytechnic, Malaysia |
  | **Business Rules Violation** | Data sets that do not comply to business rules,   e.g. Payment Types can only be Cash/CreditCard/Cheque but data has “Card” |
  | Inconsistent Data            | In one table, customer is called “Mary   Tan”, another table, is “Tan Mary” |
  | **Incomplete Data**          | Marketing segmentation data missing because gender of customer was not captured at point of purchase |
  | Non-integrated Data          | Customer A with Primary Key 123 on one   system and Primary Key 321 on another   system |

### Load

- Third phase of ETL
- Data is loaded unto the end target, usually a data warehouse or data mart
- Process varies widely depending on the requirements of the organization
  - Some data warehouse may add new data in an historical form at regular intervals, for example hourly
  - Some data warehouses may overwrite existing information with cumulative information
- Updating extracted data is frequently done on a daily, weekly or monthly basis

### ETL Tools

- Budget is the decision making factor for company
- Manual ETL done by SQL scripting or “eyeballing” of data on spreadsheets is very time-consuming, error-prone, and seldom provide complete test coverage
- A better option is to use a ETL tool which allow the user to specify instructions via a GUI interface and is much less tedious than manual coding
- Many available ETL or data integration tools
- Commercial
  - SQL Server Integration Services (SSIS)
  - Oracle Data Integrator (ODI)
  - IBM Infosphere Information Server
- Open-Source
  - Pentaho Data Integration (Pdi, Kettle)
  - CloverETL
  - Talend
