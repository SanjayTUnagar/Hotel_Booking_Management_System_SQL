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


<br clear="both">
<div>
  <h2>🗄️ Step 2: Create Table</h2>

The following SQL script creates the **tbl_Employee** table.

```sql
USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Employee]  ******/
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

```

### 🆕 Insert the data in the Table 

```sql
INSERT INTO tbl_Employee (EmployeeCode, EmployeeName, Gender, DOB, EmailID, MobileNo, Address, City, State, Graduation, PostGraduation, Designation, JoiningDate, LeavingDate, PanNo, AadharNo, Salary, Status, EntryDate, EntryBy)
VALUES 
('EMP002', 'Priya Verma', 'Female', '1992-08-22', 'priya.verma@gmail.com', '9876543211', '45 Park Street', 'Kolkata', 'West Bengal', 'B.Sc', 'M.Sc IT', 'Software Developer', '2020-03-15', NULL, 'ABCPS2345K', '123456789013', 65000, 'Active', GETDATE(), 'Admin'),
('EMP003', 'Amit Kumar', 'Male', '1988-01-10', 'amit.kumar@gmail.com', '9876543212', '78 Sector 15', 'Noida', 'Uttar Pradesh', 'B.Tech', 'M.Tech', 'Team Lead', '2026-06-20', NULL, 'ABCPS3456K', '123456789014', 95000, 'Active', GETDATE(), 'HR'),
('EMP004', 'Sneha Patil', 'Female', '1995-03-05', 'sneha.patil@gmail.com', '9876543213', '23 FC Road', 'Pune', 'Maharashtra', 'BBA', 'MBA HR', 'HR Executive', '2026-07-01', NULL, 'ABCPS4567K', '123456789015', 40000, 'Active', GETDATE(), 'HR'),
('EMP005', 'Vikram Singh', 'Male', '1985-12-18', 'vikram.singh@gmail.com', '9876543214', '56 Civil Lines', 'Jaipur', 'Rajasthan', 'B.A', NULL, 'Sales Manager', '2025-02-10', '2026-05-30', 'ABCPS5678K', '123456789016', 70000, 'Inactive', GETDATE()-3, 'Admin'),
('EMP006', 'Anjali Gupta', 'Female', '2000-06-25', 'anjali.gupta@gmail.com', '9876543215', '90 Gomti Nagar', 'Gandhinagar', 'Gujarat', 'B.Com', 'M.Com', 'Housekeeping', '2001-09-01', NULL, 'ABCPS6789K', '123456789017', 30000, 'Active', GETDATE()-50, 'HR'),
('EMP007', 'Rohit Mehta', 'Male', '1991-11-11', 'rohit.mehta@gmail.com', '9876543216', '34 SG Highway', 'Ahmedabad', 'Gujarat', 'B.E', 'M.E', 'Hotel Manager', '2026-01-15', NULL, 'ABCPS7890K', '123456789018', 98000, 'Active', GETDATE()-5, 'HR'),
('EMP008', 'Kavita Joshi', 'Female', '1989-09-09', 'kavita.joshi@gmail.com', '9876543217', '67 Model Town', 'Delhi', 'Delhi', 'B.Sc', 'M.Sc', 'Receptionist', '2025-05-20', NULL, 'ABCPS8901K', '123456789019', 45000, 'Active', GETDATE()-10, 'Admin'),
('EMP009', 'Manoj Yadav', 'Male', '1987-04-17', 'manoj.yadav@gmail.com', '9876543218', '12 Banjara Hills', 'Sugar', 'Gujarat', 'B.Com', NULL, 'Housekeeping', '2023-08-01', NULL, 'ABCPS9012K', '123456789020', 20000, 'Active', GETDATE()-15, 'HR'),
('EMP010', 'Neha Reddy', 'Female', '1994-02-28', 'neha.reddy@gmail.com', '9876543219', '89 Jubilee Hills', 'Ahmedabad', 'Gujarat', 'B.Tech', 'MBA', 'HR Executive', '2000-10-10', NULL, 'ABCPS0123K', '123456789021', 55000, 'Active', GETDATE()-25, 'HR'),
('EMP011', 'Suresh Nair', 'Male', '1986-07-19', 'suresh.nair@gmail.com', '9876543220', '45 Marine Drive', 'Rajkot', 'Gujarat', 'B.Com', 'M.Com', 'Accountant', '2010-04-05', NULL, 'ABCPS1235K', '123456789022', 45000, 'Active', GETDATE()-20, 'Admin'),
('EMP012', 'Pooja Iyer', 'Female', '1996-10-02', 'pooja.iyer@gmail.com', '9876543221', '23 T Nagar', 'Surat', 'Gujarat', 'BCA', 'MCA', 'Waiter', '2012-01-25', NULL, 'ABCPS2346K', '123456789023', 35000, 'Active', GETDATE()-9, 'Admin'),
('EMP013', 'Deepak Chauhan', 'Male', '1990-01-30', 'deepak.chauhan@gmail.com', '9876543222', '67 Sadar Bazar', 'Bhavnagar', 'Gujarat', 'B.A', NULL, 'Restaurant Supervisor', '2024-03-01', '2023-06-15', 'ABCPS3457K', '123456789024', 60000, 'Inactive', GETDATE()-5, 'Admin'),
('EMP014', 'Ritu Malhotra', 'Female', '1992-05-08', 'ritu.malhotra@gmail.com', '9876543223', '12 DLF Phase 3', 'Gandhinagar', 'Gujarat', 'B.Com', 'PTC', 'Laundry Staff', '2022-06-12', NULL, 'ABCPS4568K', '123456789025', 62000, 'Active', GETDATE()-50, 'HR'),
('EMP015', 'Arjun Rao', 'Male', '1988-08-08', 'arjun.rao@gmail.com', '9876543224', '34 Koramangala', 'Surat', 'Gujarat', 'B.E', 'M.Tech', 'Kitchen Helper', '2026-02-18', NULL, 'ABCPS5679K', '123456789026', 65000, 'Active', GETDATE()-30, 'HR'),
('EMP016', 'Shalini Desai', 'Female', '1993-12-12', 'shalini.desai@gmail.com', '9876543225', '56 Satellite Road', 'Ahmedabad', 'Gujarat', 'B.Sc', 'M.Sc', 'Waiter', '2021-09-09', NULL, 'ABCPS6780K', '123456789027', 48000.00, 'Active', GETDATE()-40, 'HR'),
('EMP017', 'Karan Kapoor', 'Male', '1991-03-23', 'karan.kapoor@gmail.com', '9876543226', '78 Rajouri Garden', 'Delhi', 'Delhi', 'BBA', 'MBA', 'Executive Chef', '2019-11-11', NULL, 'ABCPS7891K', '123456789028', 80000.00, 'Active', GETDATE()-10, 'HR'),
('EMP018', 'Meena Pillai', 'Female', '1987-06-06', 'meena.pillai@gmail.com', '9876543227', '90 MG Road', 'Vadodara', 'Gujarat', 'B.Com', 'CA', 'Assistant Manager', '2025-07-07', NULL, 'ABCPS8902K', '123456789029', 92000.00, 'Active', GETDATE()-15, 'Admin'),
('EMP019', 'Nikhil Bansal', 'Male', '1994-09-19', 'nikhil.bansal@gmail.com', '9876543228', '23 Civil Lines', 'Jamnagar', 'Gujarat', 'B.Tech', NULL, 'Kitchen Helper', '2025-04-04', NULL, 'ABCPS9013K', '123456789030', 38000.00, 'Active', GETDATE()-18, 'HR'),
('EMP020', 'Divya Menon', 'Female', '1995-11-27', 'divya.menon@gmail.com', '9876543229', '45 Anna Nagar', 'Surat', 'Gujarat', 'B.A', 'M.A', 'Housekeeping', '2026-05-05', NULL, 'ABCPS0124K', '123456789031', 18000, 'Active', GETDATE(), 'HR')

```

> ✅ **Result:** The `tbl_Employee` table data is inserted successfully ready for the next step.


### 🆕 Verify Table Creation  

```sql

select * from tbl_Employee

```

<img width="1877" height="452" alt="image" src="https://github.com/user-attachments/assets/c6a2a583-d700-4635-a114-837dc99c6fa4" />
<br clear="both">

> ✅ **Result:** The `tbl_Employee` table is successfully created and ready for the next step.
 
</div>










