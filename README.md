# apply-filters-to-sql-queries

Utilize SQL to filter through different datasets and investigate the potential security issues within my imaginary organization.

## Project Description

I am responsible for enhancing the security of my organization's system. My role involves ensuring the system's safety, examining potential security concerns, and updating employee computers as required. The following examples will demonstrate the process of how I used SQL with filters to perform security-related tasks.

## Retrieve after hours failed login attempts

There was a potential security incident that occurred after business hours (18:00). These login times after business hours need to be investigated.

The following code illustrates my process of creating an SQL query to filter for failed login attempts happening after regular business hours.

![log-in attempts past 6 PM](https://i.imgur.com/f51fjxo.png)

The query shown in the screenshot consists of two parts. The first part is my query, while the second part displays a section of the output.

In order to filter for failed login attempts that happened after 18:00, I began by selecting all the data from the log_in_attempts table. In order to achieve this, I used the following code: ```SELECT * FROM log_in_attempts```. 
In order to display specific columns from the table, I can utilize the ```SELECT``` command. To extract all the data from the table ```log_in_attempts```, I will use ```*``` as a wildcard symbol that selects all the columns. To indicate the source of the data, I will include ```FROM log_in_attempts``` in the query.


Subsequently, I employed a ```WHERE``` clause with an ```AND``` operator to further narrow down the results. This ensured that only login attempts occurring after 18:00 and being unsuccessful were displayed. To achieve this, the first condition utilized was login_time > '18:00'. This condition filters for login attempts occurring strictly after 18:00. The second condition, success = FALSE, was used to filter for failed login attempts.

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09; all login attempts that occurred on the day and the day before need investigation.

![Specific login dates](https://i.imgur.com/wHihv7U.png)

The query shown in the screenshot consists of two parts. The first part is my query, while the second part displays a section of the output.

The above query will return all login attempts from 2022-05-08 or 2022-05-09. The first thing I did was select all of the data from the ```log_in_attempts``` table using ```SELECT * FROM log_in_attempts```. Afterward, I utilized a ```WHERE``` clause with an ```OR``` operator to filter my output to display login attempts on 2022-05-08 or 2022-05-09. The first condition is ```login date = ‘2022-05-09’```. This will filter the logins for 2022-05-09. Then, the second condition input is ```login_date = ‘2022-05-08’``` which will filter the logins for 2022-05-08.

## Retrieve login attempts outside of Mexico

After a careful review of the login attempts via the data, I have determined that the activity did not originate in Mexico. I will now have to filter my searches for login attempts outside of Mexico.

The following code was used to filter out any login attempts that occurred outside of Mexico.

![Login attempts outside of Mexico](https://i.imgur.com/ervBxbE.png)

The query shown in the screenshot consists of two parts. The first part is my query, while the second part displays a section of the output.

The query that I have entered will return an output of all the login attempts from countries outside of Mexico. In order to do this, I first started by selecting all the data from the ```log_in_attempts table``` using ```SELECT * FROM log_in_attempts```. The next step I did was to use a ```WHERE``` clause with a ```NOT``` filter, allowing me to filter out countries that are not Mexico. Utilizing ```LIKE``` with ```MEX%```, I am able to search for both MEX and MEXICO because both can be represented in the dataset. The percentage sign (```%```) after ```MEX``` is a wildcard that represents any number of unspecified characters when used with LIKE.

## Retrieve employees in Marketing

My team wants to perform security updates on specific employee machines in the Marketing department.

The following code was used to SQL query filter for employee machines from employees within the marketing department that are in the East building.

![Employees in marketing and in the east office](https://i.imgur.com/zk7Hoh7.png)

The query shown in the screenshot consists of two parts. The first part is my query, while the second part displays a section of the output.

I start by selecting all the data from the ```employees``` table using ```SELECT * FROM employees```. After that, I used a ```WHERE``` clause with an ```AND``` filter for any employee who works in the Marketing department and is located in the East building. 

To filter for employees who are in the Marketing department as well as being located in the East building, I used the pattern ```East%``` with the ```LIKE``` operator. I used the wild card ```%``` to find any specific amount of characters after ```East``` because there are multiple East buildings within the ```office``` column. 

In my first condition, using the ```WHERE``` clause with the ```AND``` filter, I search for employees in the Marketing department using ```department = ‘Marketing’```. Then, in the second condition, I used ```office LIKE ‘East%’``` to filter for employees in the East building.

## Retrieve employees in Fiance or Sales

Additionally the employees in the Sales and Finance departments also require security updates. However, they require a different update. Therefore, I will need to obtain information on employees from only these two departments.

The following code shows how I filtered out employee machines from employees in the Marketing or Sales department.

![sales or finance department](https://i.imgur.com/gUGgf7p.png)
