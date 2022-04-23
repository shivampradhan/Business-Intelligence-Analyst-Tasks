## Business Intelligence Analyst Tasks

#### Data description

You are provided with the spend, revenue and install associated with installs accumulated between 01-12-2021 and 15-12-2021 on different countries for the application named 'Fruit Battle'. The spend and revenue events provided in the datasets are associated with the users installed the app in different countries in the given time period. 

`installs.csv` contains 6 columns: 
    "user_install_id": a unique identifier of the user
    "client": denotes the name of the app
    "country": country of install
    "year": year of install event
    "month": month of install event
    "day": day of install event

`spend.csv` contains 6 columns: 
    "client": denotes the name of the app
    "country_id": unique id of the country
    "country": country of spend event
    "year": year of spend event
    "month": month of spend event
    "day": day of spend event
    "spend": dollar value of the spend event

`revenue.csv` contains 6 columns: 
    "user_install_id": a unique identifier of the user
    "client": denotes the name of the app
    "country": country of revenue event
    "year": year of revenue event
    "month": month of revenue event
    "day": day of revenue event
    "revenue": dollar value of the revenue event


#### Goals

You are given 3 csv files named revenue, spend, installs. Please use SQLite to create a local database named test and store these 3 csv files in 3 different tables. 

Tasks:

1- Using Sqlite, create a database named "test" and create 3 tables named revenue, spend and installs storing the associated csv files.
2- Combine datasets using SQL queries to generate a summary table which contains columns for Ad Spend, Installs, CPI, ARPI_D1, ARPI_D14, ROAS_D14 for each client(app), country and install date between 01-12-2021 and 15-12-2021. 
    Info:
        ARPI_D1: Average revenue value a user has made within the first 1 day after the install (day revenue - day install <= 1)
        ARPI_D14: Average revenue value a user has made within the first 14 day after the install (day revenue - day install <= 14)
        ROAS_D14: ROAS after 14 days from the install.
        CPI: Cost per install

    Present your findings in a Jupyter Notebook as a DataFrame and store the resulting csv in a folder named results. Additionally the queries you have used should be found within the results folder.
    Bonus: Using Google Sheet API with Python, to send the summary table to a Google Sheet file, results can be stored in a sheet named 'results'. Define a Google Sheet class to interact with the API. Here it would be nice to see your object oriented programming skills. 

3- Do an analysis with few bullet points for the current state and the developments observed in Fruit Battle on the top three countries, which have the highest average ARPI_D14 between 01-12-2021 and 15-12-2021, using the metrics you have derived in the second question. Please also define recommendations for the next steps in few bullet points for those countries you have picked. You may use visualisations to support your reasoning. 
4- The LTV of users are accounted by the revenue they generate over their lifetime afther they have installed. The data you are given has the revenue events for each user up until the first 14 days after each user has installed the app. However, users continue to generate revenue until their lifetime is reached. In the dataset, the revenue events from the 14th day until the lifetime after the install for each user are removed on purpose. Form a regression using ARPI values to estimate the average lifetime value (LTV) for US. In this step, please document how you approach the task. Hint: Assume the lifetime of the user is reached at 28 days. Please use the aggregated ARPI values on country level during the estimation process. You can estimate the LTV for every cohort day (install date) or come up with an overall estimate for the UA activity between 01-12-2021 and 15-12-2021.


