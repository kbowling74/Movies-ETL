### Movies-ETL
## Extract, Transform, Load Movie Data

This repository contains files with functions in python to extract, transform, and load different file types through Jupyter notebook and to a sql database in pgAdmin 4 ready for use. Each file is described below.

## ETL_function_test

The extract_transform_load function loads in local data from both a csv file and structured json file. It then converts the data and returns three seperate dataframes, with the respective names: wiki_movies_df, kaggle_metadata, and ratings. <br><br>
Example of wiki_movies_df.<br>
<img width="1011" alt="Screen Shot 2022-09-02 at 11 24 44 AM" src="https://user-images.githubusercontent.com/106560606/188323658-1eb51162-6125-4f88-a817-b0726a89c04e.png"><br><br>


## ETL_clean_wiki_movies

The functions in this file will return a DataFrame with cleaned data from the wikipedia-movies.json file. Using the extract_transform_load, clean_movie, change_column_name, and parse_dollars functions on the columns for box office, budget, release date, and run time results in having clean, uniform data types. A try-except block is used when parsing to notify of any errors that may occur. The data is cleaned using regular expressions, list comprehension, and lambda functions as well as various native panda methods. An example of the data before and after the transformation is below.<br><br> 
![Screen Shot 2022-09-02 at 1 48 42 PM](https://user-images.githubusercontent.com/106560606/188323711-29d0fcac-7485-4384-ac1a-9fa867e68fef.png)<br><br>

<img width="830" alt="Screen Shot 2022-09-02 at 1 45 37 PM" src="https://user-images.githubusercontent.com/106560606/188323719-8c901efe-e9d2-4ca0-bf46-9fb716ce755d.png">
<br><br>

## ETL_clean_kaggle_data

When the functions are ran in this file it will return a DataFrame that includes the kaggle data, wikipedia data, and MoveLens data merged into one. This file has added the function fill_missing_kaggle_data that uses wikipedia data to fill in data for the runtime, budget, and revenue columns for data that was missing from the kaggle data. While changing data types on columns in the kaggle data set, "errors='raise'" is used to notify of any errors. Columns that are not needed such as 'adult' are filtered and removed. The result is a comprehensive dataframe with usable data for further analysis. <br><br>

## ETL_create_database

The dataframe created in the earlier files are added to a sql database resulting in two tables: movies and ratings. A SQL database engine is created and a for loop with print statement to notify of status (at 1,000,000 row increments) both during running the code and once importing has completed. <br><br>
Screenshot of print statement notifying completion and time elapsed. 
<img width="721" alt="Screen Shot 2022-09-02 at 3 44 53 PM" src="https://user-images.githubusercontent.com/106560606/188323730-53ba4936-bbdd-4a2d-ac98-b7d40fc7d279.png">
<br><br>
