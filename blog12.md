## Blog Twelve: Performing an SQL based attack with Unions


### Breaking into databases and database servers 

SQL injection is a basic attack used to either gain unauthorized access to a database or retrieve information immediately from the database. It is a flaw in internet apps and now not a database or internet server issue. 

SQL injection is the most common website vulnerability on the Internet and is used to take advantage of invalid input vulnerabilities to execute SQL commands through a web application, to run through a backend database. SQL injection is a code injection technique that exploits security vulnerabilities in a website's software. SQL injection attacks use malicious SQL queries or a series of SQL statements to manipulate the database directly. Applications often use SQL statements to authenticate users, verify roles and access levels, store, retrieve information for the app and the user, and link to other data sources. The reason SQL injection attacks work is that they do not verify the application properly before sending it to the SQL Statement.

### The technical goal list
```
Understanding when and how internet software connects to a database server with read access to data Extracting primary SQL Injection flaws and vulnerabilities 
Testing internet programs for Blind SQL Injection vulnerabilities
```

### SQL Injection Attacks on an Microsoft SQL Database

SQL injection is one of the most common and dangerous attacks on a website's software experience. This attack occurs on SQL databases that contain weak codes and can be used by attackers to collect sensitive information, modify database entries, or execute database queries to attach malicious code, resulting in compromising sensitive data.

We will test web applications running on the MS SQL Server database for vulnerabilities and errors.

The webserver is already staged and ready to use for testing. Launch Chrome.

![Image](https://i.imgur.com/B8BwhUJ.png)

I am accessing my personal webserver laboratory. 

![Image](https://i.imgur.com/CFiYswe.png)

Type the query blah' or 1=1 -- in the Username field (as your login name), and leave the password field empty. 

![Image](https://i.imgur.com/DprX5ev.png)

### Access Granted via Simple Logic

![Image](https://i.imgur.com/LnhtkuZ.png)

### Checking our account database on the local server

Before performing the next task, create a user account with the SQL injection query, first verify with Goodshop's login database. I will switch to the Windows Server 2016 machine which hosts the database, then click Windows Server 2016 and launch Microsoft SQL Server Management Studio.

The Microsoft SQL Server Management Studio window appears with the Connect to Server pop-up, in the Authentication field, select Windows Authentication and click Connect.

![Image](https://i.imgur.com/j7C56yS.png)

![Image](https://i.imgur.com/lzMv7fL.png)

![Image](https://i.imgur.com/6D9z9mh.png)

### Create a backdoor SQL user

![Image](https://i.imgur.com/kL2yWeT.png)

After executing the query, to verify that your login has been successfully created, click the Login tab, enter John 123 in the username field and Apple 123 in the password field, and then click Login.

You will be successfully logged in with the login you created. Now you can access all the features of the website. After browsing the required pages, click Logout and close the browser window.

I hope you have enjoyed this simple demonstration on SQL injection techniques!

Thank you!