# Pewlett-Hackard-Analysis 

Click here to view the SQL query: [Employee_Database_challenge](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Queries/Employee_Database_challenge)

Click here to open the folder of the CSV files: [Data](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/tree/main/Data)

# Overview
We received several CSV files containing the data of the employees of a company, and the provided data is about their demographics, salaries, titles, departments.
The purpose of our analysis is to answer two questions, 
•	The first one, what is the number of retiring employees per title? 
•	Who are the employees who are eligible to participate in a mentorship program?

I created an ERD showing how the primary key and foreign keys have been linked together to join tables in the right way on the right keys, and you will be able to check it by looking at the following image:

The ERD of the main tables: ![](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Resources/EmployeeDB.png)


# Results
## The first question, what is the number of retiring employees per title?
I used the employees table and the titles table. I the used (DISTINCT ON) statement to remove duplicates and used count() function to get the number of people that are going to retire for each title.

You will be able to find the code and results in the images below:

![](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Resources/The%20Number%20of%20Retiring%20Employees%20by%20Title.png)

We can notice the following:

•	The people that are going to retired come under 7 titles

•	The title with the highest number of people is Senior Engineer

•	The title with the lowest number of people is the Manager

•	The title with the highest count (Senior Engineer) and the second-highest count represent more than 60% of the retiring employees.

## The second question is, who are the employees eligible for the mentorship program?
I used to answer this question three tables the employees, dep_emp, and the titles table, and I joined them together to get the needed fields into one table, then used the ‘where’ clause to add some conditions to the query, those conditions helped me to filter the data and get to the current employees who were born between January 1, 1965, and December 31, 1965. check the image below:

![](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Resources/The%20Employees%20Eligible%20for%20the%20Mentorship%20Program.png)

Then I created a query that returns the count of the employees who are eligible for the mentorship program by title. Check below:

![](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Resources/The%20Employees%20Eligible%20for%20the%20Mentorship%20Program%20by%20title.png)

And at the end, I created a query showing number of mentees that will be handled by each mentor, considering the number of mentees as the new employees that will be hired to replace the retiring people. Check the image below:

![](https://github.com/ALEIN3/Pewlett-Hackard-Analysis/blob/main/Resources/the%20number%20of%20the%20mentees%20for%20each%20mentor%2C%20the%20average%2C%20and%20%25%20of%20total.png)

Since we don’t have a way to measure how many mentees represent the best number to get the best performance when handled by one mentor, I will consider that each mentor will take the same number of mentees, how much is available of mentors in each title as a percentage of the total mentors, and how many employees are expected to get hired in each title as a percentage of the total, so we get an idea about which title needs to receive more attention.

After running the query in the image above, we find the following:

•	The Senior Engineer segment needs more attention since we have 103 mentees for each mentor, this segment represents 18% of the potential mentors, which means that it comes in the third-lowest place among the studied segments(titles), plus this segment has 33% of the potential new employees under it(Senior Engineer), and that percentage represents the highest percentage of the of all the studied titles.  

•	The Senior Engineer title is far from the average comparing to other titles when considering the average mentees for each mentor.

•	We don’t have mentors to train any managers.

# Summary
To summarize all the previous founds:

•	We can see that we have seven titles included in the study.

•	The title with the highest number of retirees is the Senior Engineer, with 33% of total retiring people.

•	18% of the mentors will be handling 33% of the mentees as we have in the Senior Engineers segment.

•	26% of the mentors will be handling 16% of the mentees as we have in the Engineers segment.

Based on the conditions that we have been provided within this project, and by reviewing the previous analysis, in general, we can see that the number of the available mentors for the senior levels is less than the number of mentors for the mid-levels, the Senior Engineer title is the best case here since the highest number of the retiring employees is from that segment and by considering that every mentor will handle the same number of mentees, we can try to solve the difference between titles by promoting the qualified people from the Engineers segment, to cover some of the retiring people in the Senior Engineers segment, then we hire more engineers since we have more mentors in that segment to take care of them. By doing that we can decrease the load on the senior engineers.

 
