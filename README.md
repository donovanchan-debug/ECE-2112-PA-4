# ECE-2112-PA-4

Name: Donovan C. Chan  
Section: 2ECE-A  

# SETTING UP THE TABLE:
1. Import library for data structures and tools:   
`import pandas as pd`

2. Display csv file:   
`df = pd.read_csv('board2.csv')`

3. Find the average for every row and display:
`df['Average'] = df[['Math', 'Electronics']].mean(axis=1)`
`df`

# A. VISAYAS COMMUNICATION DATAFRAME
Create a DataFrame named VisComm containing students whose Hometown is Visayas and whose Track
is Communication. Retain only these columns, in the stated order: Name, Gender, Math, Electronics, Average  

Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.  

**How it works:**
1. Filter Visayas and Communication from table:   
`Filtered = df[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication')]`

2. Retain the display of "Name", "Gender", "Math", "Electronics", and "Average":   
`Viscomm = Filtered[['Name','Gender', 'Math', 'Electronics', 'Average' ]]`

3. Display the table:   
`Viscomm`   

3. Display the number of rows of Viscomm:   
`print("\nNumber of rows:", len(Viscomm))`   

   
# B. VISAYAS FEMALE DATAFRAME
Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only:  

Name, Track, GEAS, Electronics, Average  

Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.   

**How it works:**   
1. Filter Female from Viscomm table:   
`FViscomm = Viscomm[(Viscomm['Gender'] == 'Female')] `   

2. Retain the display of "Name", "Track", "GEAS", "Electronics", and "Average":   
`VisFemale = FViscomm[['Name','Track', 'GEAS', 'Electronics', 'Average' ]]`

3. Display the table:    
`VisFemale`

4. Show Female students with an Average above 60:
`VisFemale.loc[(VisFemale['Average']>60)]`

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
1. Import library tool for displaying 2D Visualization Graphs:   
`import matplotlib.pyplot as plt`   

2. Include the Average for every row in the table:   
`df['Average'] = df[['Math', 'Electronics']].mean(axis=1)`   

*a. For each feature, compute the mean of Average for every category using Pandas.*   
`Trackmean = df.groupby('Track')['Average'].mean()`   
`Gendermean = df.groupby('Gender')['Average'].mean()`   
`Hometownmean = df.groupby('Hometown')['Average'].mean()`   

*b. Display the three summary tables.*   
`Trackmean`   
`Gendermean`   
`Hometownmean`   

*c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by Hometown.*
1. Create 1 figure with 1 row and 3 columns of subplots:   
`fig, axes = plt.subplots(1, 3, figsize=(15, 5))`

2. Plot mean average by track for the 1st bar chart:   
`Trackmean.plot(kind='bar', ax=axes[0], color='skyblue', edgecolor='black')`   

3. Add labels for the 1st bar chart:   
`axes[0].set_title('Mean Average by Track')`   
`axes[0].set_ylabel('Average Score')`   
`axes[0].set_xlabel('Track')`   

4. Plot mean average by gender for the 2nd bar chart:   
`Gendermean.plot(kind='bar', ax=axes[1], color='lightgreen', edgecolor='black')`

5. Add labels for the 2nd bar chart:
`axes[1].set_title('Mean Average by Gender')`

6. Plot mean average by hometown for the 3rd bar chart:   
`Hometownmean.plot(kind='bar', ax=axes[2], color='salmon', edgecolor='black')`

7. Add labels for the 3rd bar chart:

