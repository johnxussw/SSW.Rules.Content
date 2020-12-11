---
type: rule
archivedreason: 
title: Schema - Do you have a rowversion column?
guid: fda895fe-2c8c-4e8d-9db7-ced3717bae64
uri: schema---do-you-have-a-rowversion-column
created: 2019-11-06T17:27:42.0000000Z
authors:
- id: 1
  title: Adam Cogan
- id: 96
  title: Alex Breskin
- id: 99
  title: Christian Morford-Waite
related: []

---

SQL Server rowversions are a data type available which are binary numbers that indicate the relative sequence in which data modifications took place in a database. See the MSDN article on rowversions here: [rowversion (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/data-types/rowversion-transact-sql?view=sql-server-ver15)

<!--endintro-->

All tables should have a rowversion column called "RecordVersion" to aid concurrency checking. A rowversion improves update performance because only one column needs to be checked when performing a concurrency check (instead of checking all columns in a table for changes).
<dl class="ssw15-rteElement-ImageArea"><img src="NoRowversionOnTable.png" alt="" style="margin:5px;"></dl>

::: bad
Figure: Bad Example - No rowversion available in this table

:::




CREATE TABLE MyTest (myKey int PRIMARY KEY 
    ,myValue int, RecordVersion rowversion); 
GO
 
INSERT INTO MyTest (myKey, myValue) VALUES (1, 0);  
INSERT INTO MyTest (myKey, myValue) VALUES (2, 0); 
INSERT INTO MyTest (myKey, myValue) VALUES (3, 0); 
UPDATE MyTest SET myValue = 1 WHERE myKey = 2
 
SELECT \* FROM MyTest ORDER BY RecordVersion DESC


::: good
Figure: Good Example - A create statement which builds a table with a rowversion

:::



<dl class="ssw15-rteElement-ImageArea"><img src="RecordsWithRowversion.jpg" alt="" style="margin:5px;"></dl>

::: good
Figure: Good Example - A set of records with a rowversion available
:::