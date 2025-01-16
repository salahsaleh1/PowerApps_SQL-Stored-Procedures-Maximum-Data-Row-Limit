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
- Second gallery uses a stored procedure that does a Select * from People and then displays again only the ID of each record.
