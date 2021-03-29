# Movies-ETL

## Purpose
1. Delivery 1: ETL_function_test.ipynb
First, we create a function, called extract_transform_load, that takes in three arguments which are directories where files are saved. The function will retrieve data according to the arguments and provide outputs as wiki_movies_df, kaggle_metadata variable. After excuting the function, we then assign three variables in the same name with the variables results we get from function. At the step, we turn the result from local variables into gloabl variables. Since the function convert data into dataframe format, we can check them easily.

2. Delivery 2: ETL_clean_wiki_movies.ipynb
We extend the code from delivery 1 to clean data from JOSN format to dataframe format and clean imdb id, clean null data in box office, budget, release date and running time columns.

3. Delivery 3: ETL_clean_kaggle_movies.ipynb
We extend the code from delivery 2 to import cvs data to dataframe format. On Kaggle file, we drop adult column, keep "True" value in video column, convert data in budget column into integer instead of string, convert data in id and popularity into numeric, and change release date into datetime format. Then, merge kaggle data with delivery 1 on imdb_id and keep the columns we want and name it movies_df. On rating file, we pivot the data into movieID as index, rating as columns and values as count after groupbying the data. Next, merge rating file with movies_df on kaggle_id.


4. Delivery 4: ETL_create_database.ipynb
Delivery 4 is a copy of delivery 3. We refactor the extract_transform_load function. Insteaf of providing three variable results, we connect to pgAdmin4 and add the movies_df and uploading ratings.csv.
