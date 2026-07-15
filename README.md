<div>
<h1>  🏨 Hotel Booking Management System – SQL Project</h1>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/SQL_Server-Database-red?style=for-the-badge&logo=microsoftsqlserver&logoColor=white">
  <img src="https://img.shields.io/badge/SSMS-Management_Studio-blue?style=for-the-badge">
 <img src="https://img.shields.io/badge/Status-In%20Progress-yellow?style=for-the-badge">
  <img src="https://img.shields.io/badge/Project-SQL-orange?style=for-the-badge">
</p>
<br clear="both">
<div>
<h2>📌 Project Overview</h2>
 
The **Hotel Booking Management System** is a SQL-based database project designed to automate hotel operations such as customer registration, room booking, check-in/check-out, payment processing, and business reporting.

This project demonstrates practical SQL concepts used in real-world database applications.
</div>

<br clear="both">

<div>
<h2>🎯 Objectives</h2>
</div>
<table align="center" width="100%">

  <tr>
    <td valign="top" width="50%">
      <ul>
        <li>Manage hotel room bookings</li>
        <li>Store customer information</li>
        <li>Track room availability</li>
        <li>Manage employees</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <ul>
        <li>Generate invoices</li>
        <li>Process payments</li>
        <li>Create business reports</li>
        <li>Improve hotel management efficiency</li>
      </ul>
    </td>
  </tr>
</table>


<br clear="both">
<div>
<h2>🛠️ Technologies Used</h2>
</div>
<table align="center">
 <tr>
    <th align="left"><b>Technology</b></th>
    <th align="left"><b>Description</b></th>
  </tr>
  <tr>
    <td valign="top" width="350">
      <ul>
        <li>Microsoft SQL Server</li>
        <li>SQL Server Management Studio</li>
        <li>SQL</li>
        <li>GitHub</li>
      </ul>
    </td>
    <td valign="top" width="350">
      <ul>
        <li>Database</li>
        <li>Database Development</li>
        <li>Query Language</li>
        <li>Project Repository</li>
      </ul>
    </td>
  </tr>
</table>

<br clear="both">

<div>
  <h2>🗄️ Create Database</h2>

The following SQL script creates the **Hotel_DB** database.

**Check if the database already exists** 

IF DB_ID('Hotel_DB') IS NOT NULL
BEGIN
    DROP DATABASE Hotel_DB;
END;
GO

**Create Database**

```sql
CREATE DATABASE Hotel_DB;
GO

USE Hotel_DB;
GO
```


  
</div>










