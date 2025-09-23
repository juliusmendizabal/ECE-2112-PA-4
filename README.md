# ECE-2112-PA-4

**Made by: Julius Miguel S. Mendizabal | 2ECE-C**

The content of this repository contains the Programming Assignment 4 for our course "Advance Computer Programming" this S.Y. 2025-2026. This project covers two python problems pertaining to Module 4 - Data Wrangling and Visualization.

*All problems were first initialized with the code below to load Pandas and Matplotlib library, and easily call the functions using 'pd' and 'plt'.
```python
import pandas as pd
import matplotlib.pyplot as plt
```
## **ECE BOARD EXAM PROBLEM: Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given.**

After initializing the needed libraries, the excel file 'board2.xlsx' containing the dataset for the ECE Board Exam Scores was loaded using `pd.read_excel()` and was assigned to the dataframe named 'df'.
```python
df = pd.read_excel('board2.xlsx')
df
```

Note: the 'board2.xlsx' must be in the same folder as the .ipynb file.

<img width="310" height="61" alt="image" src="https://github.com/user-attachments/assets/afb476c3-b42d-4be5-8312-061449ed7394" />

### **Problem 1: Data Wrangling**
#### Create the following data frames based on the format provided:

Example output:

Vis = [“Name”, “Gender”, “Track”, “Math<70”]; hometown is constant as Visayas
<img width="546" height="98" alt="image" src="https://github.com/user-attachments/assets/bb2d5b3a-417a-45e7-a45d-c091b4583d3c" />

**This first problem is divided into two parts, part a and part b:**

*`.style.hide(axis="index")` was used in the two parts of Problem 1 to hide the index column of the dataframe and match the example output provided above.

**In part a,** we're tasked to create the following data frames with the format; Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown as Luzon. We are able to do this using the code below. 
```python
Instru = df.loc[(df['Track']=='Instrumentation') & (df['Hometown']=='Luzon') & (df['Electronics']>70), ['Name','GEAS','Electronics']].style.hide(axis="index")
Instru
```
`df.loc[...]` was used to locate the needed columns according to the format given.

The following conditions such as; Electronics score that are only greater than 70, board takers whose college track is Instrumentation and whose hometown was Luzon were followed.
The output of the code above is as follows:

<img width="228" height="151" alt="image" src="https://github.com/user-attachments/assets/64e1f18d-d2b0-48ae-8cc3-610eb8b77836" />


**In part b,** we're tasked to create the following data frames with the format; Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender as Female. We are able to do this using the code below. 
```python
df['Average'] = df[['Math','Electronics','GEAS','Communication']].mean(axis=1)
Mindy = df.loc[(df['Hometown']=='Mindanao') & (df['Gender']=='Female') & (df['Average']>=55), ['Name','Track','Electronics','Average']].style.hide(axis="index")
Mindy
```

`df['Average'] = df[['Math','Electronics','GEAS','Communication']].mean(axis=1)` - was used to create a new column in the axis 1, named 'Average', containing the average scores of the board takers 

`df.loc[...]` was used to locate the needed columns according to the format given.

The following conditions such as; Average score that are only greater than or equal to 55, board takers whose gender is female and whose hometown was Mindanao were followed.

The output of the code above is as follows:

<img width="395" height="231" alt="image" src="https://github.com/user-attachments/assets/4974cceb-8aa7-4ff2-8eee-b8f867fc6720" />


### **Problem 2: Data Visualization**

**In this part,** we're tasked to create a visualization that shows how the different features contributes to average grade. Does chosen track in college, gender, or hometown contributes to a higher average score?

**To plot by track chosen in college,** the following code was used:
```python
plt.bar(df['Track'], df['Average']) # plots the dataframe column 'Track' and 'Average' to the x & y axis of the bar graph
plt.ylim(65, 85) # set y-axis limits to zoom into the table
# labels
plt.xlabel('Track') 
plt.ylabel('Average')
plt.title('Average by Track')

plt.show()
```
The output of the code above is as follows:

<img width="618" height="455" alt="image" src="https://github.com/user-attachments/assets/d6634d3d-6987-4288-9ca5-cbefb12dbd57" />


**To plot by gender,** the following code was used:
```python
plt.bar(df['Gender'], df['Average']) # plots the dataframe column 'Gender' and 'Average' to the x & y axis of the bar graph
plt.ylim(65, 85) # set y-axis limits to zoom into the table
# labels
plt.xlabel('Track')
plt.ylabel('Average')
plt.title('Average by Track')

plt.show()
```
The output of the code above is as follows:

<img width="597" height="456" alt="image" src="https://github.com/user-attachments/assets/5d1a64c7-92f6-46d3-9479-315f53abf39c" />


**To plot by hometown,** the following code was used:
```python
plt.bar(df['Hometown'], df['Average']) # plots the dataframe column 'Hometown' and 'Average' to the x & y axis of the bar graph
plt.ylim(65, 85) # set y-axis limits to zoom into the table
# labels
plt.xlabel('Track')
plt.ylabel('Average')
plt.title('Average by Track')

plt.show()
```
The output of the code above is as follows:

<img width="607" height="462" alt="image" src="https://github.com/user-attachments/assets/196c0369-746e-465b-81ff-762f9d6b7a5b" />



Thank you for reading! 

To see the main python programs for Programming Assignment 4, click this link https://github.com/juliusmendizabal/ECE-2112-PA-4/blob/main/Programming%20Assignment%204.ipynb and download the .ipynb file or the .py file. Open on Jupyter Notebook, then run all cells.


#### **README file Version History:**

September 21, 2025 - Initial README output uploaded (content + format).

September 23, 2025 - Added few additional details + a README file Version History.
