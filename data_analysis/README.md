## Data analysis notebooks for COMM318 _Stories from data_ Final Project

* This folder should contain the a series of Jupyter notebooks you create to do the data analysis.

* Update this README file to document the notebooks and give a short description of what each one does.


## Notebooks (please read/run them in this order)

### 1. stock.ipynb:
This is a custom Stock class that stores a ticker, company name, and a dataframe of historical stock data. 

### 2. collect_data.ipynb: 
This uses `yfinance` to collect historical data of stocks by a ticker. The resulting dataframe is stored into a custom Stock object that is saved in the data/FAANG_stocks directory. The data is already in the data folder so there is no need to run this notebook.

### 3. get_functions.ipynb: 
This is primarily for retrieving the downloaded information from the `collect_data.ipynb` notebook. There are also some functions that are used throughout the different notebooks, such as `graph_x_and_y_list()`, so there is less code duplication. 

### 4. analysis_notebook_01_first_look.ipynb
This notebook imports the downloaded stocks for the FAANG analysis and graphs them to make sure they are being imported properly. 

### 5. analysis_notebook_02_trading_analysis.ipynb
This notebook imports the downloaded stocks for the FAANG analysis, subsets the dataframes by the year 2020, and creates two moving averages of the closing columns of each stock's dataframe. These two moving averages are used to run a simple trading strategy that shows buy and sell signals based on the intersection points of the lines. It also outputs the count of the buy and sell points.

### 6. analysis_notebook_03_google_trends_analysis.ipynb
This notebook takes a list of keywords to search in Google Trends using the pytrends library. Each query results in a dataframe that we use to graph. We also calculate a linear regression using the sklearn library, which is used to give us a clear metric of whether the trend had a positive or negative trend over the time period.

### 7. get_aws_client_data.ipynb:
This notebook scrapes an Amazon website with articles for companies that have partnered with Amazon to use their AWS services. The program goes through each page and collects relevant information from each article of the company's name, sector, and year the article was published. This information is stored in a custom Company class that is saved using the pickle library to the data/company_data directory.

### 8. analysis_notebook_04_aws_client_stock_analysis.ipynb
This notebook reads all company objects saved in the data/company_data directory and groups them by sector. Once we can find the sector with the highest amount of companies that have integrated AWS into their business, we handpick some of the companies and download their stock information to the data/aws_client_stocks directory and graph them to see their trends.
