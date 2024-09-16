# PA 3 - PYTHON DATA ANALYSIS
This repository makes use ofthe Pandas Library in the programming Problems

### Needed for the Programming Assignment

1. the cars.csv file as this will be the main data source that the student will use in the problem.

# Problems

### 1. Csv Dataframe loading and Row Viewing
In this problem, the programmer is tasked to open a .csv file named "cars" and load into a data frame. It has to reveal the first five and last five rows of the data frame. 


### 2. Slicing, Subsetting, and Indexing in Pandas
After loading the cars.csv file, the following instructions are to be followed

1. Display the first five rows that has an odd-numbered columns in cars i.e columns 1,3,5,7..
2. Display the row that contains the 'Model' of 'Mazda RX4'
3. Display how many cylinders ('cyl') does the car model of 'Camaro Z28' have
4. Determine how many cylinders(cyl) and what gear type(gear) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic' have.

# Solutions
Welcome to the solutions! the following code blocks are the solutions to the problems stated in the previous section.

### 1. Dataframe Loading and Row view
 ```python

 import pandas as pd
cars = pd.read_csv('cars.csv')#reads the excel file
print("The first five rows are: \n",   cars.head()) #prints the first 5 rows
print("The last five rows are: \n", cars.tail()) #prints the last 5 rows

cars.to_csv('Maitim_Pandas-P1.py') #prints to a csv file or excel file
```

## Output

![image](https://github.com/user-attachments/assets/f129f582-d17b-495b-a566-1a7152428604)


### 2. Odd-Numbered Columns
```

cars = cars.iloc[:5,::2]  #selects the first 5 rows of the dataframe, skips every 2 columns to get the odd number
cars #prints the odd numbers rows
```

### Output
![image](https://github.com/user-attachments/assets/040267cf-411e-41db-b00b-f708c06c0b98)


### 2. Display row that contains Model 'Mazda RX4'
```
cars.loc[cars['Model']=='Mazda RX4'] #prints the row that contains the model Mazda RX4
```

### Output
![image](https://github.com/user-attachments/assets/2287f6a5-966c-425a-9468-4bce49ef6421)


### 3. Display how many cylinders does Camaro Z28 have.

```
cars.loc[cars['Model']== 'Camaro Z28', ['Model','cyl']] #prints the dataframe of the model Camayo Z28 and the cyl 8
```
### Output

![image](https://github.com/user-attachments/assets/8982deb0-8d48-4b91-acae-d05506d7184b)

### 4. Cylinders and Gears of ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic'.

```
models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic'] #put in a list of the needed to find models
column = ['Model','cyl','gear'] #puts in a list of what should be included in the row
for model in models: #for loop to find each models
    x = cars.loc[cars['Model'] == model, column] #locates the car model with the arguments
    print(x) #prints the car model, cyl, and gear.

```

### Output
![image](https://github.com/user-attachments/assets/2bffd92e-8eac-46b8-bfd6-ab76b4aac5ca)














