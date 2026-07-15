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
  <h2>🗄️ Step 1: Create Database</h2>

The following SQL script creates the **Hotel_DB** database.

### 🎯 Check if the database already exists..

```sql
IF DB_ID('Hotel_DB') IS NOT NULL
BEGIN
    DROP DATABASE Hotel_DB;
END;
GO
```

### 🆕 Create Database

```sql
CREATE DATABASE Hotel_DB;
GO

USE Hotel_DB;
GO
```
> ✅ **Result:** The `Hotel_DB` database is successfully created and ready for the next step.

</div>



<div>
  <h2>🗄️ Step 2: Create Table</h2>

The following SQL script creates the **tbl_Employee** table.

```sql
USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Employee]    Script Date: 16-07-2026 03:05:59 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Employee](
	[EmployeeID] [int] IDENTITY(1,1) NOT NULL,
	[EmployeeCode] [varchar](10) NULL,
	[EmployeeName] [varchar](50) NULL,
	[Gender] [varchar](50) NULL,
	[DOB] [date] NULL,
	[EmailID] [varchar](50) NULL,
	[MobileNo] [varchar](10) NULL,
	[Address] [varchar](500) NULL,
	[City] [varchar](50) NULL,
	[State] [varchar](50) NULL,
	[Graduation] [varchar](50) NULL,
	[PostGraduation] [varchar](50) NULL,
	[Designation] [varchar](50) NULL,
	[JoiningDate] [date] NULL,
	[LeavingDate] [date] NULL,
	[PanNo] [varchar](12) NULL,
	[AadharNo] [varchar](15) NULL,
	[Salary] [int] NULL,
	[Status] [varchar](50) NULL,
	[EntryDate] [date] NULL,
	[EntryBy] [varchar](50) NULL,
 CONSTRAINT [PK_tbl_Employee] PRIMARY KEY CLUSTERED 
(
	[EmployeeID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO


### 🆕 Create Database

```sql
CREATE DATABASE Hotel_DB;
GO

USE Hotel_DB;
GO
```
> ✅ **Result:** The `Hotel_DB` database is successfully created and ready for the next step.


  
</div>










