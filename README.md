# Flight Delay Analysis:
## Content:

1. [Introduction](#introduction)
2. [Objective](#objective)
3. [About the Dataset](#about-the-dataset)
4. [Code Documentation](#code-documentation)
    1. [Importing Libraries and Spark Setup](#importing-libraries-and-spark-setup)
    2. [Loading the Dataset](#loading-the-dataset)
    3. [Understanding the Data](#understanding-the-data)
    4. [Optimization](#optimization)
    5. [Data Preprocessing](#data-preprocessing)
    6. [Dataset Analysis](#dataset-analysis)
5. [How to Run the Code](#how-to-run-the-code)

## Introduction:

In today's fast-paced world, air travel has become an indispensable part of modern life. However, flight delays can disrupt travel plans and create challenges for passengers, airlines, and airports alike. Understanding the causes and patterns of flight delays is key to enhancing the overall air travel experience and identifying areas for improvement.

## Objective:

The objective of this project is to perform a comprehensive Data Analysis using a vast dataset of flight information. My primary focus is to gain insights into flight delay patterns, ultimately shedding light on the dynamics of air travel.

## About the Dataset:

The dataset spans from 2018 to 2023-04, containing extensive information regarding scheduled and actual arrival and departure times, with a specific emphasis on delays rather than cancellations or diversions. This dataset comprises a staggering 30,132,672 records, underlining the sheer volume of data I am dealing with.

You can access the dataset on Kaggle [here](https://www.kaggle.com/datasets/arvindnagaonkar/flight-delay/).

## Code Documentation:

### 1. Importing Libraries and Spark Setup:

I kickstart my project by importing essential libraries and configuring the Spark session. Given the limitations of my local machine (8GB RAM, 4 cores), I'm running the code locally. My configuration includes:

- Setting executor memory to 5GB.
- Configuring executor cores to 3.
- Defining 4 executor instances.
- Allocating 2GB of driver memory.
- Setting a single driver core.
- Enhancing the maximum number of fields displayed when printing a plan to 100.

### 2. Loading the Dataset:

The dataset is loaded into a DataFrame. However, due to the limitations of local resources, I extract a sample from it using a fraction ratio of 0.001, resulting in approximately 30,000 records. The bulk of the data transformations are completed locally, with the possibility of shifting to a cloud-based solution for processing the full dataset.

### 3. Understanding the Data:

To gain insights, I begin with a schema presentation of the data, highlighting the number of null values and duplicates. A description of the DataFrame provides details on data types for each column, ensuring data consistency.

### 4. Optimization:

- **Data Sampling**: Given resource constraints, I extract a sample of the dataset using a fraction ratio.
- **Data Partitioning**: To enhance parallel processing, the number of partitions is increased from 6 to 10.
- **Caching**: After numerous data transformations, the final DataFrame is cached to improve processing efficiency.
- **Memory Management**: Driver and executor memory are specified to optimize resource utilization.

### 5. Data Preprocessing:

I undertake several data preprocessing steps:

- Converting the "Flight_Date" from a string type to a date type.
- Creating a new column, "TotalDelay," to compute the total delay for each flight by summing "DepDelay" and "ArrDelay."
- Introducing a "Carrier Name" column to map the carrier shortcuts to their full names.
- Introducing "Origin_City" and "Dest_City" columns to map airport city shortcuts to full city names.

### 6. Dataset Analysis:

My analysis focuses on addressing key questions based on the dataset:

- What is the average delay time for each airline?
- Which are the top 10 airlines with the most delay time?
- What is the most common cause of delays?
- How does distance relate to delay time?
- Which airport experiences the highest flight volume?
- What is the average delay time by day of the week?
- What is the average delay time by month?

## Project Presentation:

I have created a detailed presentation that provides an overview of my project, key findings, and visual insights. You can access the project presentation [here](https://github.com/alaahgag/BigData_Processing_Using_Spark/blob/main/FlightDelayAnalysis.pptx).

The presentation complements the documentation and provides a visual representation of my analysis and its results. I encourage you to explore it for a more immersive understanding of my project.

## How to Run the Code:

I have attached two Jupyter files to the repository:

- **FlightDelayAnalysis_on_SampleOfData.ipynb**: If you run the code on your local machine.
- **FlightDelayAnalysis_on_WholeData.ipynb**: If you run the code on the cloud.

You can choose the appropriate file based on your computing resources and preferences. Happy analyzing!
