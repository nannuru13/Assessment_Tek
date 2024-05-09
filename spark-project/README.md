
****Provider Report****


**Overview**
The Provider Report project is a Spark application developed to analyze healthcare provider data and generate reports on the total number of visits per provider and per month. This application utilizes Apache Spark's DataFrame API to efficiently process large datasets and perform aggregations.

**Requirements**
To run the Provider Report application, you need:

Apache Spark (version 3.5.1)
java version "16.0.2" 2021-07-20
Scala (version 3.4.1)

**Input data files**:
providers.csv: Contains information about healthcare providers, including their IDs, specialties, and names.
visits.csv: Contains information about visits made to healthcare providers, including visit IDs, provider IDs, and dates of service.

**Usage**
1. Clone the repository to your local machine.
2. Place the input data files (**providers.csv** and **visits.csv**) in the data directory.
3. Modify the application as needed (e.g., update file paths, and adjust configurations).
4. Build the application using **sbt**
                  **sbt compile**
                  **sbt package**
5. Run the application using **spark-submit**:
         **spark-submit --class ProviderReport --master 'local[*]' /Users/saikumarreddynannuru/spark-project/target/scala-2.12/spark-project_2.12-0.1.0-SNAPSHOT.jar**

6. View the generated reports in the **output** directory. The reports will be partitioned by provider specialty (total_visits_per_provider) and by month (visits_per_provider_per_month).
7. 
**Functionality**

**Problem 1:** Total Number of Visits per Provider
Calculates the total number of visits made to each healthcare provider.
Joins the visit data with provider data to include provider names and specialties.
Outputs the report partitioned by provider specialty in JSON format.

**Problem 2:** Total Number of Visits per Provider per Month
Calculates the total number of visits made to each healthcare provider per month.
Outputs the report partitioned by month in JSON format.

**Error Handling**
The application includes error handling for the following scenarios:

File not found: If the input data files are not found at the specified paths.
Analysis error: If an error occurs during data processing and analysis.
