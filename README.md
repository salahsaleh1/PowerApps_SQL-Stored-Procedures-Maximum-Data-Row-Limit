# PowerApps_SQL-Stored-Procedures-Maximum-Data-Row-Limit

Connectors in PowerApps allow us to read data from lists and libraries and gather 2000 items at once. <br>
However, we can get around this restriction by using SQL Stored Procedures in PowerApps.<br><br>

**PowerApps data row limit**<br><br>
We are familiar with the following Data row limit setting:

<p align="center">
<img src="https://github.com/user-attachments/assets/02665291-f76d-4f69-a8de-b9269e84554f" alt=PowerAutomate">
</p>

<br><br>

And most likely we always set this to the maximum of 2000 rows. Well no need for that anymore!

<h2>Connecting SQL Stored Procedures and SQL Tables</h2><br>
In our app we have setup two data sources. **SPSWRD** is connecting to a SQL stored procedure reading records from my Cars table.<br>
While I have another data source **SWRDTable** reading data directly from the Cars table.
<br>
<br>
<p align="center">
<img src="https://github.com/user-attachments/assets/feab5eb1-9199-4a1a-bb36-3ea63ff6e707" alt=PowerAutomate">
</p>

Now in my application I am creating two galleries.
- One gallery has Cars table as a data source and displayes the ID of each record.
- Second gallery uses a stored procedure that does a Select * from Cars and then displays again only the ID of each record.

<p align="center">
<img src="https://github.com/user-attachments/assets/8c9c0e3a-608b-4e25-9a8e-9dee9935929a" alt=PowerAutomate">
</p>

As we can see the gallery taking the stored procedure data contains all 10000 records.<br>
If we scroll down in the galleries we can find that the left gallery will increase by chunks of 100 records, as the lazy load is kicking in.
<br>
<br>

<h2>CountRows on SQL Datasources</h2>
Now how about the CountRows directly on the data sources?
<br>
<p align="center">
<img src="https://github.com/user-attachments/assets/9a5bb608-9b53-4904-9f95-ad3c61bcd293" alt=PowerAutomate">
</p>

<br><br>
We took this test a bit further. When we count the rows on the Cars datasource, We are getting 500 records. <br>
This is the settings that we looked at in the beginning of this post. For Stored procedures this settings seems to be ignored.

<br><br>
<h2>SQL Stored Procedures and delegation issues</h2>

Now this will be a major change in how we address delegation issues. Dataverse, SharePoint and other datasources are affected by delegation issues. Stored Procedures are not subject to delegation rules as all data is simply loaded and they are not limited to receiving a subset of records.
