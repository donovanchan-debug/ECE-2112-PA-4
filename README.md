# ECE-2112-PA-4

Name: Donovan C. Chan  
Section: 2ECE-A  

# A. VISAYAS COMMUNICATION DATAFRAME
Create a DataFrame named VisComm containing students whose Hometown is Visayas and whose Track
is Communication. Retain only these columns, in the stated order: Name, Gender, Math, Electronics, Average  

Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.  

**How it works:**
1. Display the cars spreadsheet:   
`cars = pd.read_csv('cars.csv')`      
`cars`   

2. Display the shape and complete list of column names of cars:   
`print("Shape of cars:", cars.shape)`   
`print("Column names:", cars.columns.tolist())`   

3. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.   

`cars_6_to_10 = cars.iloc[5:10]`   
`cars_6_to_10`   

4. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order:   
`selected_columns = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]`   
`selected_columns`   
   
# B. VISAYAS FEMALE DATAFRAME
Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only:  

Name, Track, GEAS, Electronics, Average  

Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.   

**How it works:**   
1. Display the cars spreadsheet:   
`cars = pd.read_csv('cars.csv')`      
`cars`   

2. Display the complete row for Toyota Corolla:   
`toyota = cars[cars['Model'] == 'Toyota Corolla']`  
`toyota`   

3. For Pontiac Firebird, display only Model, mpg, hp, and wt:   
`pontiac = cars[cars["Model"] == "Pontiac Firebird"][["Model", "mpg", "hp", "wt"]]`   
`pontiac`   

# C. CATEGORY-AVERAGE VISUALIZATION
Examine how the recorded Average differs across the three categorical features Track, Gender, and
Hometown.   

a. For each feature, compute the mean of Average for every category using Pandas.   
b. Display the three summary tables.   
c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by
Hometown.   
d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.   

Interpretation rule: Describe the observed dataset only. A difference in group means does not, by
itself, establish that a feature causes a higher board-exam score.     

**How it works:**  
1. Filtering the Rows:   
`models = ["Datsun 710", "Lotus Europa", "Ferrari Dino"]`   
`filtered_cars = cars[cars["Model"].isin(models)]`   

2. Selecting the Columns:   
`columns = ["Model", "mpg", "cyl", "hp", "gear"]`   
`selected_cars = filtered_cars[columns]`   

3. Checking the Size:   
`print("Shape of selected_cars:")`   
`(selected_cars.shape)`   
