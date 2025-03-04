# AirBnB-Data-Engineering-Pipeline
## Overview
- This project offers an end-to-end data pipeline. It begins with importing CSV data into PostgreSQL as a **staging area**. Next, **Python** is used to extract data from the staging area, followed by transformation using the Pandas library. The transformed data is loaded back into a **designed data warehouse** on **PostgreSQL**. Finally, actionable business insights are derived from the loaded data.
  
- The data engineering pipeline of the project:

![Screenshot 2024-02-22 070320](https://github.com/Arwa0/AirBnB-Data-Engineering-Project/assets/74055031/73b4422f-5faa-4ee4-895f-21beecf04926)

## Designing The Data Warehouse
- appling **Dimensional modeling** to design a **galaxy-schema** model depending on our business processes
- ***Dimensional Modeling steps*** :
  - **(1) The business process** revolves around leveraging the data warehouse to gain insights and make informed decisions related to the asked business questions ,Most fact tables focus on the results of a single business process
  - **(2) Identifying Granularity**:
      - Fact Tables: Data stored at the daily level, with each row representing a specific listing on a specific date.
      - Dimension Tables: Aggregate or summarize data at varying levels of granularity, based on specific dimensions and metrics included in each table. For example, summarizing key metrics such as price, number of reviews, and availability at the listing level.
  - **(3) Identifying Dimensions**:
    - `Listing Dimension`: Includes all attributes related to listings such as ID, name, description, host details, location, property type, room type, and amenities.
    - `Date Dimension`: Represents date-related attributes such as date, month, year, and day of the week for analyzing trends and patterns over time.
  - **(4) Identifying Facts**:
    - `Reservations Fact`: Contains data related to listing availability, price, and minimum/maximum nights for each listing on specific dates.
    - `Reviews Fact`: Stores data related to reviews for each listing, including review ID, date, reviewer details, and comments.
 - [See the Data Warehouse Design here](https://github.com/Arwa0/AirBnB-Data-Engineering-Project/tree/main/Data%20Warehouse%20Design#readme)

## ETL process:
- This process includes extracting data from the staging layer, converting each table into a **pandas DataFrame**, performing transformations such as removing leading and trailing whitespace from columns, changing some column datatypes to match the data warehouse, adding surrogate keys, etc. Then, the data is loaded back to the data warehouse on PostgreSQL.
- You can find the code for the ETL process in [this](https://github.com/Arwa0/AirBnB-Data-Engineering-Project/blob/main/ETL%20using%20python%20script.ipynb) jupyter notebook file

## Actionable Business Insights
- Now, you can turn business questions into actionable business insights.
- You can find the questions, along with their queries used to answer them, and the CSV files containing these insights in [this folder](https://github.com/Arwa0/AirBnB-Data-Engineering-Project/tree/main/Actionable%20Business%20Insights)
