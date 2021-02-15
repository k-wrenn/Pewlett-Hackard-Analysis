# Pewlett-Hackard-Analysis
## Overview
The purpose of this analysis is to assist Pewlett-Hackard with the "silver tsunami" by identifying thousands of job openings as many of their current employees reach retirement age. SQL was used to determine the number of retiring employees per title and also to identify employees who are eligible to participate in a mentorship program to help ease the new transition.

## Resources
Data*: departments.csv, dept_emp.csv, dept_manager.csv, employees.csv, salaries.csv, titles.csv

      *All files are located in "Data" folder

Software: Postgres, pgAdmin

## Results
### Retirement Titles
First, a Retirement Titles table was created. This table holds all the titles of employees who were born between January 1, 1952 and December 31, 1955. Partial table shown below:

<img width="564" alt="retirement_titles" src="https://user-images.githubusercontent.com/74752756/107894069-0d59da00-6ef4-11eb-8706-8315ac734518.PNG">


As you can see, this table had multiple duplicate entries. This is because, over the years, employees have switched titles and this table includes every title the employee held. 

### Unique Title
In order to remove the duplicates and keep only the most recent title of each retiring employee, a **DISTINCT ON** statement was used. Then, a Unique Title table was created, which only had the emplyees most current title. Snap shot shown below:

<img width="583" alt="unique_titles" src="https://user-images.githubusercontent.com/74752756/107894126-32e6e380-6ef4-11eb-8651-6a6e21ce21d7.png">

### Retirement by Title
From there, a table to illustrate the number of retirements by job title was created. This was done by first retrieving the number of titles from the previously created Unique Title table, then creating a Retiring Titles table. The Retiring Titles table was grouped by title then sorted in descending order. Full chart below:

<img width="185" alt="retiring_titles" src="https://user-images.githubusercontent.com/74752756/107894142-4134ff80-6ef4-11eb-8763-e98c4f7abc3d.PNG">

Amongst the largest group of retiring titles are:

    * 29,414 Senior engineers will be retiring
    * 28,255 Senior Staff at Pewlett-Hackard will be retiring
    * 14,222 Engineers are eligible for retirement
    * 12,243 Staff are retiring

### Mentorship Program
Next, a query was written to create a Mentorship Eligibility table that holds the current employees who are eligible to participate in a mentorship program. The current employees who are eligible for this program are born between January 1, 1965 and December 31, 1965. The table was exported to the data folder as mentorship_eligibilty.csv and a snippet is shown below:

<img width="627" alt="mentorship_eligibility" src="https://user-images.githubusercontent.com/74752756/107894464-552d3100-6ef5-11eb-9490-c93eb7938210.PNG">

## Summary
While the employees who are retirement-eligible only hold seven (7) different titles, a total of 90,938 employees who hold those titles are approaching retirement. This is a considerable amount Pewlett-Hackard will be losing if they do not start preparing for their replacements. 

Although a mentorship program may be put in place, based of the current criteria, only 1,549 of the 90,938 total employees would be eligible to participate. This would mean one (1) retirement-ready employee would be responsible for mentoring approximately 58 new hires (90,398 retirement-ready/1,549 mentorship-eligible= 58.35). Such a large training group could prove difficult for one mentor to manage. 

Further analysis would need to be completed to determine how the 1,549 mentorship-eligible employees are divvied up. For example, with only 2 managers eligible for retirement, it would not be beneficial to have 6 retiring managers eligible for the mentorship program. However, if a proportionate number of mentorship-eligible employees hold positions in the title positions that have the most upcoming retirements, the mentorship program has the potential to be successful.
