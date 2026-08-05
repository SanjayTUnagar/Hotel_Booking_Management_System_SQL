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

<img width="100%" height="1024" alt="Hotel_Booking_Management_System_SQL" src="https://github.com/user-attachments/assets/72d72d6c-dd63-429d-a6cb-35b5f93b5d25" />


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

### 🆕 Create table for tbl_Customer  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Customer]   ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Customer](
	[CustomerID] [int] IDENTITY(1,1) NOT NULL,
	[CustomerCode] [varchar](10) NULL,
	[CustomerName] [varchar](50) NULL,
	[Gender] [varchar](10) NULL,
	[DateOfBirth] [date] NULL,
	[MaritalStatus] [varchar](15) NULL,
	[MobileNo] [varchar](15) NULL,
	[EmailID] [varchar](100) NULL,
	[Address] [varchar](200) NULL,
	[City] [varchar](50) NULL,
	[State] [varchar](50) NULL,
	[Country] [varchar](50) NULL,
	[Nationality] [varchar](50) NULL,
	[IDProofType] [varchar](20) NULL,
	[IDProofNumber] [varchar](30) NULL,
	[MembershipType] [varchar](20) NULL,
	[RegistrationDate] [datetime] NULL,
	[PreferredRoomType] [varchar](20) NULL,
	[CheckInDateTime] [datetime] NULL,
	[CheckOutDateTime] [datetime] NULL,
	[PackageID] [int] NULL,
	[Status] [varchar](20) NULL,
 CONSTRAINT [PK_tbl_Customer] PRIMARY KEY CLUSTERED 
(
	[CustomerID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO

```

### 🆕 Insert the data in the Table 

```sql
insert into tbl_Customer(CustomerCode,CustomerName,Gender,DateOfBirth,MaritalStatus,MobileNo,EmailID,Address,City,
    State,Country,Nationality,IDProofType,IDProofNumber,MembershipType,RegistrationDate,PreferredRoomType,CheckInDateTime,
    CheckOutDateTime,PackageID,Status)
values
('CUST001','Rahul Sharma','Male','1992-05-12','Single','9876543210','rahul.sharma@gmail.com','Satellite Road','Ahmedabad','Gujarat','India','Indian','Aadhar Card','123456789012','Gold','2026-01-10','Deluxe',GETDATE(),GETDATE()+2,1,'Confirmed'),

('CUST002','Priya Patel','Female','1995-08-18','Married','9876543211','priya.patel@gmail.com','Navrangpura','Ahmedabad','Gujarat','India','Indian','Passport','P1234567','Silver','2026-01-15','Suite',GETDATE(),GETDATE()+4,2,'Confirmed'),

('CUST003','Amit Shah','Male','1990-03-25','Married','9876543212','amit.shah@gmail.com','SG Highway','Ahmedabad','Gujarat','India','Indian','Aadhar Card','456789123456','Regular','2026-02-01','Executive',GETDATE(),GETDATE()+1,3,'Checked In'),

('CUST004','Neha Joshi','Female','1998-11-21','Single','9876543213','neha.joshi@gmail.com','Maninagar','Ahmedabad','Gujarat','India','Indian','Passport','P2345678','Platinum','2026-02-10','Suite',GETDATE(),GETDATE()+5,4,'Confirmed'),

('CUST005','Rohan Mehta','Male','1993-09-10','Single','9876543214','rohan.mehta@gmail.com','Paldi','Ahmedabad','Gujarat','India','Indian','Aadhar Card','789456123789','Gold','2026-02-15','Deluxe',GETDATE(),GETDATE()+4,5,'Checked Out'),

('CUST006','Sneha Desai','Female','1997-06-05','Single','9876543215','sneha.desai@gmail.com','Bopal','Ahmedabad','Gujarat','India','Indian','Passport','P3456789','Silver','2026-03-01','Executive',GETDATE(),GETDATE()+3,2,'Confirmed'),

('CUST007','Karan Singh','Male','1989-04-17','Married','9876543216','karan.singh@gmail.com','Thaltej','Ahmedabad','Gujarat','India','Indian','Aadhar Card','963852741852','Regular','2026-03-10','Suite',GETDATE(),GETDATE(),3,'Cancelled'),

('CUST008','Pooja Verma','Female','1994-12-30','Married','9876543217','pooja.verma@gmail.com','Vastrapur','Ahmedabad','Gujarat','India','Indian','Passport','P4567891','Gold','2026-03-15','Deluxe',GETDATE(),GETDATE()+2,1,'Confirmed'),

('CUST009','Arjun Kumar','Male','1996-01-20','Single','9876543218','arjun.kumar@gmail.com','Naranpura','Ahmedabad','Gujarat','India','Indian','Aadhar Card','852963741258','Silver','2026-04-01','Suite',GETDATE(),GETDATE()+3,4,'Checked In'),

('CUST010','Kavita Shah','Female','1991-10-08','Married','9876543219','kavita.shah@gmail.com','Gota','Ahmedabad','Gujarat','India','Indian','Passport','P5678912','Regular','2026-04-10','Executive',GETDATE(),GETDATE()+6,2,'Confirmed'),

('CUST011','Vikas Patel','Male','1988-07-07','Married','9876543220','vikas.patel@gmail.com','Chandkheda','Ahmedabad','Gujarat','India','Indian','Aadhar Card','741852963147','Gold','2026-04-15','Suite',GETDATE(),GETDATE()+7,5,'Confirmed'),

('CUST012','Anjali Sharma','Female','1999-02-14','Single','9876543221','anjali.sharma@gmail.com','Isanpur','Ahmedabad','Gujarat','India','Indian','Passport','P6789123','Silver','2026-05-01','Deluxe',GETDATE(),GETDATE()+4,1,'Checked In'),

('CUST013','Deepak Rana','Male','1992-09-19','Single','9876543222','deepak.rana@gmail.com','Nikol','Ahmedabad','Gujarat','India','Indian','Aadhar Card','369852147852','Regular','2026-05-10','Executive',GETDATE(),GETDATE()+2,3,'Confirmed'),

('CUST014','Meera Joshi','Female','1995-11-11','Married','9876543223','meera.joshi@gmail.com','Memnagar','Ahmedabad','Gujarat','India','Indian','Passport','P7891234','Gold','2026-05-15','Suite',GETDATE(),GETDATE()+1,4,'Confirmed'),

('CUST015','Suresh Yadav','Male','1987-05-25','Married','9876543224','suresh.yadav@gmail.com','Ranip','Ahmedabad','Gujarat','India','Indian','Aadhar Card','258963147852','Platinum','2026-05-20','Executive',GETDATE(),GETDATE(),5,'Checked Out'),

('CUST016','Ritu Kapoor','Female','1993-08-09','Single','9876543225','ritu.kapoor@gmail.com','Sabarmati','Ahmedabad','Gujarat','India','Indian','Passport','P8912345','Silver','2026-06-01','Deluxe',GETDATE(),GETDATE()+3,2,'Confirmed'),

('CUST017','Harsh Trivedi','Male','1991-12-18','Married','9876543226','harsh.trivedi@gmail.com','Bapunagar','Ahmedabad','Gujarat','India','Indian','Aadhar Card','357159258456','Gold','2026-06-05','Suite',GETDATE(),GETDATE()+2,1,'Confirmed'),

('CUST018','Nisha Patel','Female','1998-04-16','Single','9876543227','nisha.patel@gmail.com','Naroda','Ahmedabad','Gujarat','India','Indian','Passport','P9123456','Regular','2026-06-10','Executive',GETDATE(),GETDATE()+1,3,'Checked In'),

('CUST019','Manoj Gupta','Male','1989-06-28','Married','9876543228','manoj.gupta@gmail.com','Ellisbridge','Ahmedabad','Gujarat','India','Indian','Aadhar Card','654123987456','Silver','2026-06-15','Deluxe',GETDATE(),GETDATE()+10,2,'Confirmed'),

('CUST020','Aisha Khan','Female','1997-01-30','Single','9876543229','aisha.khan@gmail.com','Prahlad Nagar','Ahmedabad','Gujarat','India','Indian','Passport','P9988776','Platinum','2026-06-20','Suite',GETDATE(),GETDATE()+2,5,'Confirmed');

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Customer

```

<img width="1877" height="456" alt="image" src="https://github.com/user-attachments/assets/c964ceac-ae2b-42b0-aec9-2617384ed381" />

<br clear="both">

> ✅ **Result:** The `tbl_Customer` table is successfully created and ready for the next step.
 

### 🆕 Create table for tbl_Orders  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Orders]  ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Orders](
	[OrderID] [int] IDENTITY(1,1) NOT NULL,
	[OrderCode] [varchar](50) NULL,
	[BookingID] [int] NULL,
	[CustomerID] [int] NULL,
	[PackageID] [int] NULL,
	[MenuID] [int] NULL,
	[OrderDate] [datetime] NULL,
	[Quantity] [int] NULL,
	[TotalAmount] [int] NULL,
	[OrderStatus] [varchar](50) NULL,
	[PaymentMode] [varchar](50) NULL,
 CONSTRAINT [PK_tbl_Orders] PRIMARY KEY CLUSTERED 
(
	[OrderID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO




```

### 🆕 Insert the data in the Table 

```sql
insert into tbl_Orders 
(OrderCode, BookingID, CustomerID, PackageID, MenuID, OrderDate, Quantity, TotalAmount, OrderStatus, PaymentMode)
values
--('ORD001', 1, 1, 1, 1, '2026-07-01 08:30:00', 2, 450.00, 'Delivered', 'Cash'),
('ORD002', 2, 2, 2, 3, GETDATE()-5, 1, 350.00, 'Delivered', 'Online'),
('ORD003', 3, 3, 1, 5, GETDATE()-2, 3, 900.00, 'Preparing', 'Cash'),
('ORD004', 4, 4, 3, 2, GETDATE()-10, 2, 600.00, 'Pending', 'Online'),
('ORD005', 5, 5, 2, 6, GETDATE()-12, 1, 280.00, 'Delivered', 'Cash'),
('ORD006', 6, 6, 1, 4, GETDATE()-3, 2, 720.00, 'Cancelled', 'Online'),
('ORD007', 7, 7, 4, 8, GETDATE()-4, 4, 1200.00, 'Delivered', 'Cash'),
('ORD008', 8, 8, 3, 7, GETDATE()-15, 2, 540.00, 'Preparing', 'Online'),
('ORD009', 9, 9, 2, 9, GETDATE()-10, 3, 960.00, 'Delivered', 'Cash'),
('ORD010', 10, 10, 5, 10, GETDATE()-1, 2, 650.00, 'Pending', 'Online'),
('ORD011', 11, 11, 1, 11, GETDATE(), 1, 300.00, 'Delivered', 'Cash'),
('ORD012', 12, 12, 4, 12, GETDATE()-3, 5, 1750.00, 'Preparing', 'Online'),
('ORD013', 13, 13, 3, 13, GETDATE()-1, 2, 580.00, 'Delivered', 'Cash'),
('ORD014', 14, 14, 2, 14, GETDATE()-20, 1, 320.00, 'Cancelled', 'Cash'),
('ORD015', 15, 15, 5, 15, GETDATE()-14, 3, 990.00, 'Delivered', 'Online'),
('ORD016', 16, 16, 1, 16, GETDATE()-5, 2, 740.00, 'Preparing', 'Cash'),
('ORD017', 17, 17, 4, 17, GETDATE()-8, 4, 1400.00, 'Delivered', 'Online'),
('ORD018', 18, 18, 3, 18, GETDATE()-2, 2, 680.00, 'Pending', 'Cash'),
('ORD019', 19, 19, 2, 19, GETDATE()-1, 1, 260.00, 'Delivered', 'Online'),
('ORD020', 20, 20, 5, 20, GETDATE(), 3, 1050.00, 'Delivered', 'Cash');

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Orders

```
<img width="947" height="457" alt="image" src="https://github.com/user-attachments/assets/fb83a7f1-ea7d-4c8f-b54a-4ee6a4c427f8" />

<br clear="both">

> ✅ **Result:** The `tbl_Orders` table is successfully created and ready for the next step.


### 🆕 Create table for tbl_Booking  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Booking] ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Booking](
	[BookingID] [int] IDENTITY(1,1) NOT NULL,
	[BookingCode] [varchar](20) NULL,
	[CustomerID] [int] NULL,
	[PackageID] [int] NULL,
	[OrderID] [int] NULL,
	[BookingDate] [datetime] NULL,
	[CheckInDate] [datetime] NULL,
	[CheckOutDate] [datetime] NULL,
	[Adults] [int] NULL,
	[Children] [int] NULL,
	[TotalDays] [int] NULL,
	[PaymentIntrument] [varchar](50) NULL,
	[TransactionNo] [varchar](100) NULL,
	[TransactionDate] [datetime] NULL,
	[BookingStatus] [varchar](50) NULL,
	[TotalAmount] [int] NULL,
 CONSTRAINT [PK_tbl_Booking] PRIMARY KEY CLUSTERED 
(
	[BookingID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO




```

### 🆕 Insert the data in the Table 

```sql
INSERT INTO tbl_Booking
(BookingCode, CustomerID, PackageID, OrderID, BookingDate, CheckInDate, CheckOutDate,
 Adults, Children, TotalDays, PaymentIntrument, TransactionNo, TransactionDate,
 BookingStatus, TotalAmount)
VALUES
('BK001', 1, 1, 1, GETDATE()+1, GETDATE()+3, GETDATE()+2, 2, 1, 2, 'UPI', 'TXN1001', GETDATE()+4, 'Confirmed', 12000),
('BK002', 2, 2, 2, GETDATE()+2, GETDATE()+3, GETDATE()+3, 2, 0, 3, 'NEFT', 'TXN1002', GETDATE()+4, 'Confirmed', 18000),
('BK003', 3, 3, 3, GETDATE()+1, GETDATE()+4, GETDATE()+5, 4, 2, 4, 'Cheque', 'TXN1003', GETDATE()+6, 'Pending', 35000),
('BK004', 4, 4, 4, GETDATE()+2, GETDATE()+3, GETDATE()+4, 2, 2, 3, 'Net Banking', 'TXN1004', GETDATE()+5, 'Confirmed', 22000),
('BK005', 5, 5, 5, GETDATE(), GETDATE(), GETDATE()+1, 3, 1, 4, 'UPI', 'TXN1005', GETDATE()+2, 'Confirmed', 28000),
('BK006', 6, 1, 6, GETDATE()+1, GETDATE()+2, GETDATE()+3, 2, 0, 2, 'Cheque', 'TXN1006', GETDATE()+4, 'Pending', 15000),
('BK007', 7, 2, 7, GETDATE()+2, GETDATE()+4, GETDATE()+5, 4, 2, 3, 'UPI', 'TXN1007', GETDATE()+6, 'Confirmed', 25000),
('BK008', 8, 3, 8, GETDATE()+4, GETDATE()+2, GETDATE()+3, 2, 1, 4, 'NEFT', 'TXN1008', GETDATE()+5, 'Confirmed', 30000),
('BK009', 9, 4, 9, GETDATE()+5, GETDATE()+2, GETDATE()+3, 1, 0, 2, 'Net Banking', 'TXN1009', GETDATE()+6, 'Pending', 16000),
('BK010', 10, 5, 10, GETDATE(), GETDATE(), GETDATE()+1, 2, 2, 4, 'UPI', 'TXN1010', GETDATE()+3, 'Confirmed', 42000),
('BK011', 11, 1, 11, GETDATE()+2, GETDATE()+3, GETDATE()+4, 2, 0, 2, 'Cheque', 'TXN1011', GETDATE()+5, 'Confirmed', 14000),
('BK012', 12, 2, 12, GETDATE()+7, GETDATE()+1, GETDATE()+2, 3, 1, 3, 'NEFT', 'TXN1012', GETDATE()+3, 'Pending', 26000),
('BK013', 13, 3, 13, GETDATE()+1, GETDATE()+2, GETDATE()+3, 2, 2, 4, 'UPI', 'TXN1013', GETDATE()+4, 'Confirmed', 34000),
('BK014', 14, 4, 14, GETDATE()+4, GETDATE()+6, GETDATE()+8, 2, 0, 2, 'Net Banking', 'TXN1014', GETDATE()+7, 'Confirmed', 17000),
('BK015', 15, 5, 15, GETDATE()+3, GETDATE()+4, GETDATE()+5, 4, 2, 4, 'Cheque', 'TXN1015', GETDATE()+5, 'Pending', 45000),
('BK016', 16, 1, 16, GETDATE()+2, GETDATE()+4, GETDATE()+6, 2, 1, 2, 'UPI', 'TXN1016', GETDATE()+7, 'Confirmed', 13000),
('BK017', 17, 2, 17, GETDATE()+4, GETDATE()+5, GETDATE()+6, 3, 0, 3, 'NEFT', 'TXN1017', GETDATE()+8, 'Confirmed', 21000),
('BK018', 18, 3, 18, GETDATE(), GETDATE()+1, GETDATE()+2, 2, 2, 4, 'UPI', 'TXN1018', GETDATE()+3, 'Pending', 33000),
('BK019', 19, 4, 19, GETDATE()+1, GETDATE()+2, GETDATE()+3, 2, 0, 2, 'Cheque', 'TXN1019', GETDATE()+4, 'Confirmed', 19000),
('BK020', 20, 5, 20, GETDATE()+2, GETDATE()+3, GETDATE()+4, 5, 2, 4, 'Net Banking', 'TXN1020', GETDATE()+5, 'Confirmed', 52000);

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Booking

```
<img width="1626" height="456" alt="image" src="https://github.com/user-attachments/assets/f5389cb3-5ee0-4bcd-ba8c-609ab56ba564" />

<br clear="both">

> ✅ **Result:** The `tbl_Booking` table is successfully created and ready for the next step.
 

### 🆕 Create table for tbl_Package  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Package]    ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Package](
	[PackageID] [int] IDENTITY(1,1) NOT NULL,
	[PackageCode] [varchar](50) NULL,
	[PackageName] [varchar](150) NULL,
	[PackageType] [varchar](300) NULL,
	[NoOfDays] [int] NULL,
	[BreakfastIncluded] [varchar](10) NULL,
	[LunchIncluded] [varchar](10) NULL,
	[DinnerIncluded] [varchar](10) NULL,
	[PackagePrice] [int] NULL,
	[DiscountPercent] [int] NULL,
	[Availability] [varchar](20) NULL,
	[CreatedDate] [datetime] NULL,
	[Status] [varchar](30) NULL,
 CONSTRAINT [PK_tbl_Package] PRIMARY KEY CLUSTERED 
(
	[PackageID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO

```

### 🆕 Insert the data in the Table 

```sql
insert into tbl_Package
(
    PackageCode,PackageName,PackageType,NoOfDays,BreakfastIncluded,LunchIncluded,DinnerIncluded,PackagePrice,DiscountPercent,
    Availability,CreatedDate,Status
)
values
('PKG001','Economy Stay','Normal',1,'Yes','No','No',1999,5,'Available',GETDATE()-5,'Active'),
('PKG002','Economy Stay','Standard',2,'Yes','No','No',3500,10,'Available',GETDATE(),'Active'),
('PKG003','Family Fun','Standard',3,'Yes','Yes','No',6000,12,'Available',GETDATE()-9,'Active'),
('PKG004','Family Fun','Delux',5,'Yes','Yes','Yes',12999,15,'Available',GETDATE()-1,'Active'),
('PKG005','Honeymoon Romance','Luxury Suite',3,'Yes','Yes','Yes',15000,20,'Available',GETDATE()-3,'Active'),
('PKG006','Honeymoon Romance','Executive',2,'Yes','Yes','Yes',18000,10,'Available',GETDATE()-7,'Active'),
('PKG007','Summer Holiday','Standard',4,'Yes','Yes','No',8000,8,'Available',GETDATE()-10,'Active'),
('PKG008','Summer Holiday','Delux',6,'Yes','Yes','Yes',9000,18,'Available',GETDATE()-3,'Active'),
('PKG009','Festival Special','Normal',2,'Yes','No','No',5500,5,'Available',GETDATE()-7,'Active'),
('PKG010','Festival Special','Luxury Suite',4,'Yes','Yes','Yes',3500,25,'Available',GETDATE()-6,'Active'),
('PKG011','Business Stay','Executive',3,'Yes','Yes','No',15000,10,'Not Available',GETDATE()-3,'Inactive'),
('PKG012','Business Stay','Luxury Suite',5,'Yes','Yes','Yes',21000,15,'Available',GETDATE()-1,'Active'),
('PKG013','Weekend Escape','Standard',2,'Yes','No','No',8000,10,'Available',GETDATE(),'Active'),
('PKG014','Weekend Escape','Delux',3,'Yes','Yes','Yes',7500,12,'Available',GETDATE()-7,'Active'),
('PKG015','Luxury Retreat','Luxury Suite',7,'Yes','Yes','Yes',35000,20,'Available',GETDATE()-5,'Active'),
('PKG016','Corporate Package','Executive',4,'Yes','Yes','No',50000,15,'Not Available',GETDATE()-12,'Inactive'),
('PKG017','Couple Special','Delux',2,'Yes','Yes','Yes',20000,10,'Available',GETDATE()-10,'Active'),
('PKG018','Family Vacation','Luxury Suite',6,'Yes','Yes','Yes',8000,22,'Available',GETDATE(),'Active'),
('PKG019','Holiday Special','Standard',3,'Yes','Yes','No',7499,8,'Not Available',GETDATE()-3,'Inactive'),
('PKG020','Premium Escape','Luxury Suite',7,'Yes','Yes','Yes',10000,30,'Available',GETDATE()-4,'Active');

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Package

```
<img width="1326" height="471" alt="image" src="https://github.com/user-attachments/assets/6ff7dc18-15ec-46e9-a0b1-a831f2b72019" />

<br clear="both">

> ✅ **Result:** The `tbl_Package` table is successfully created and ready for the next step.


 
### 🆕 Create table for tbl_MenuMaster  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_MenuMaster]    Script Date: 06-08-2026 03:03:51 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_MenuMaster](
	[MenuID] [int] IDENTITY(1,1) NOT NULL,
	[MenuCode] [varchar](50) NULL,
	[MenuName] [varchar](500) NULL,
	[MenuCategory] [varchar](50) NULL,
	[MenuType] [varchar](50) NULL,
	[Quantity] [int] NULL,
	[MenuPrice] [int] NULL,
	[Availability] [varchar](50) NULL,
	[CreatedDate] [datetime] NULL,
 CONSTRAINT [PK_tbl_MenuMaster] PRIMARY KEY CLUSTERED 
(
	[MenuID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO

```

### 🆕 Insert the data in the Table 

```sql

INSERT INTO tbl_MenuMaster
(MenuCode, MenuName, MenuCategory, MenuType, Quantity, MenuPrice, Availability, CreatedDate)
VALUES
('MN001','Paneer Butter Masala','Veg','Lunch',50,250,'Available',GETDATE()+2),
('MN002','Veg Biryani','Veg','Dinner',40,220,'Available',GETDATE()+3),
('MN003','Chicken Biryani','Non-Veg','Dinner',35,320,'Available',GETDATE()),
('MN004','Butter Naan','Veg','Lunch',100,40,'Available',GETDATE()+1),
('MN005','Dal Tadka','Veg','Lunch',60,180,'Available',GETDATE()-3),
('MN006','Chicken Curry','Non-Veg','Lunch',45,300,'Available',GETDATE()-5),
('MN007','Fish Fry','Non-Veg','Dinner',30,350,'Available',GETDATE()-4),
('MN008','Veg Fried Rice','Veg','Dinner',50,200,'Available',GETDATE()-2),
('MN009','Hakka Noodles','Veg','Dinner',40,190,'Available',GETDATE()),
('MN010','Mutton Curry','Non-Veg','Dinner',25,450,'Available',GETDATE()+2),
('MN011','Masala Dosa','Veg','Breakfast',70,120,'Available',GETDATE()+3),
('MN012','Idli Sambhar','Veg','Breakfast',80,90,'Available',GETDATE()-10),
('MN013','Poha','Veg','Breakfast',60,80.00,'Available',GETDATE()-2),
('MN014','Omelette','Non-Veg','Breakfast',50,100,'Available',GETDATE()+2),
('MN015','Grilled Chicken','Non-Veg','Dinner',30,400,'Available',GETDATE()),
('MN016','Veg Manchurian','Veg','Lunch',45,210,'Available',GETDATE()),
('MN017','Pav Bhaji','Veg','Lunch',55,150,'Available',GETDATE()+1),
('MN018','Prawn Curry','Non-Veg','Dinner',20,480,'Not-Available',GETDATE()+1),
('MN019','Caesar Salad','Veg','Lunch',35,170,'Available',GETDATE()),
('MN020','Chocolate Brownie','Veg','Dinner',40,160,'Available',GETDATE()+1)

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_MenuMaster

```
<img width="877" height="457" alt="image" src="https://github.com/user-attachments/assets/16b3a705-f224-4d83-ba64-b1ef9fb3b411" />

<br clear="both">

> ✅ **Result:** The `tbl_MenuMaster` table is successfully created and ready for the next step.
 

### 🆕 Create table for tbl_Billing  

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Billing]    Script Date: 06-08-2026 03:08:16 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Billing](
	[BillID] [int] IDENTITY(1,1) NOT NULL,
	[BillCode] [varchar](50) NULL,
	[OrderID] [int] NULL,
	[BillDate] [datetime] NULL,
	[CheckInDate] [datetime] NULL,
	[CheckOutDate] [datetime] NULL,
	[TotalDays] [int] NULL,
	[BillingStatus] [varchar](50) NULL,
	[TotalAmount] [int] NULL,
	[PaymentIntrument] [varchar](50) NULL,
	[TransactionNo] [varchar](50) NULL,
	[TransactionDate] [datetime] NULL,
 CONSTRAINT [PK_tbl_Billing] PRIMARY KEY CLUSTERED 
(
	[BillID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO


```

### 🆕 Insert the data in the Table 

```sql

INSERT INTO tbl_Billing
(
BillCode,OrderID,BillDate,CheckInDate,CheckOutDate,TotalDays,BillingStatus,TotalAmount,PaymentIntrument,TransactionNo,
TransactionDate)
VALUES
('BILL001',1,GETDATE()+2,GETDATE()-2,GETDATE()+2,3,'Active',8500.00,'UPI','TXN100001',GETDATE()+2),
('BILL002',2,GETDATE()+4,GETDATE()-2,GETDATE()+4,2,'Active',6200.00,'Cash','TXN100002',GETDATE()+4),
('BILL003',3,GETDATE()+1,GETDATE()-1,GETDATE()+1,3,'Active',9800.00,'Card','TXN100003',GETDATE()+1),
('BILL004',4,GETDATE()+3,GETDATE(),GETDATE()+3,3,'Cancelled',0.00,'Cheque','TXN100004',GETDATE()+3),
('BILL005',5,GETDATE()+4,GETDATE()-2,GETDATE()+4,2,'Active',7500.00,'NEFT','TXN100005',GETDATE()+4),
('BILL006',6,GETDATE(),GETDATE()-2,GETDATE(),2,'Active',5600.00,'UPI','TXN100006',GETDATE()),
('BILL007',7,GETDATE(),GETDATE()-3,GETDATE(),4,'Active',14200.00,'Card','TXN100007',GETDATE()),
('BILL008',8,GETDATE()+3,GETDATE()-2,GETDATE()+3,4,'Active',13500.00,'Cash','TXN100008',GETDATE()+3),
('BILL009',9,GETDATE(),GETDATE()-1,GETDATE(),3,'Cancelled',0.00,'Cheque','TXN100009',GETDATE()),
('BILL010',10,GETDATE()+2,GETDATE()-3,GETDATE()+2,4,'Active',16800.00,'UPI','TXN100010',GETDATE()+2),
('BILL011',11,GETDATE(),GETDATE(),GETDATE(),3,'Active',8900.00,'Card','TXN100011',GETDATE()),
('BILL012',12,GETDATE(),GETDATE(),GETDATE(),3,'Active',10200.00,'NEFT','TXN100012',GETDATE()),
('BILL013',13,GETDATE(),GETDATE()-5,GETDATE(),4,'Active',14900.00,'Cash','TXN100013',GETDATE()),
('BILL014',14,GETDATE(),GETDATE()-2,GETDATE(),3,'Active',9600.00,'UPI','TXN100014',GETDATE()),
('BILL015',15,GETDATE(),GETDATE()-4,GETDATE(),4,'Cancelled',0.00,'Cheque','TXN100015',GETDATE()),
('BILL016',16,GETDATE(),GETDATE()-1,GETDATE(),3,'Active',11200.00,'Card','TXN100016',GETDATE()),
('BILL017',17,GETDATE(),GETDATE(),GETDATE(),3,'Active',9400.00,'NEFT','TXN100017',GETDATE()),
('BILL018',18,GETDATE()-1,GETDATE()-3,GETDATE()-1,4,'Active',17500.00,'UPI','TXN100018',GETDATE()-1),
('BILL019',19,GETDATE(),GETDATE()-2,GETDATE(),3,'Active',8800.00,'Cash','TXN100019',GETDATE()),
('BILL020',20,GETDATE(),GETDATE()-1,GETDATE(),4,'Active',19400.00,'Card','TXN100020',GETDATE())

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Billing

```
<img width="1287" height="458" alt="image" src="https://github.com/user-attachments/assets/a58f2550-b633-4301-98e6-df7b032072ea" />

<br clear="both">

> ✅ **Result:** The `tbl_Billing` table is successfully created and ready for the next step.

 
### 🆕 Create table for tbl_Salary 

```sql

USE [Hotel_DB]
GO

/****** Object:  Table [dbo].[tbl_Salary]    Script Date: 06-08-2026 03:12:58 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[tbl_Salary](
	[SalaryID] [int] IDENTITY(1,1) NOT NULL,
	[SalaryCode] [varchar](50) NULL,
	[EmployeeID] [int] NULL,
	[SalaryMonth] [varchar](20) NULL,
	[BasicSalary] [int] NULL,
	[Bonus] [varchar](200) NULL,
	[OvertimeAmount] [int] NULL,
	[NetSalary] [int] NULL,
	[PaymentIntrument] [varchar](100) NULL,
	[BankName] [varchar](200) NULL,
	[AccountNumber] [varchar](50) NULL,
	[IFSCCode] [varchar](50) NULL,
	[SalarytDate] [datetime] NULL,
	[SalaryStatus] [varchar](50) NULL,
	[CreatedDate] [datetime] NULL,
 CONSTRAINT [PK_tbl_Salary] PRIMARY KEY CLUSTERED 
(
	[SalaryID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO


```

### 🆕 Insert the data in the Table 

```sql

INSERT INTO tbl_Salary
(SalaryCode,EmployeeID,SalaryMonth,BasicSalary,Bonus,OvertimeAmount,NetSalary,PaymentIntrument,BankName,AccountNumber,
IFSCCode,SalarytDate,SalaryStatus)
VALUES
('SAL001',1,'January-2026',30000,3000,1500,34500,'Net Banking','State Bank of India','123456789001','SBIN0001001',GETDATE(),'Paid'),
('SAL002',2,'January-2026',32000,2500,1200,35700,'Net Banking','HDFC Bank','123456789002','HDFC0001002',GETDATE(),'Paid'),
('SAL003',3,'January-2026',35000,4000,1800,40800,'Net Banking','ICICI Bank','123456789003','ICIC0001003',GETDATE(),'Paid'),
('SAL004',4,'January-2026',28000,2000,800,30800,'Net Banking','Axis Bank','123456789004','UTIB0001004',GETDATE(),'Paid'),
('SAL005',5,'January-2026',45000,5000,2500,52500,'Net Banking','Bank of Baroda','123456789005','BARB0001005',GETDATE(),'Paid'),
('SAL006',6,'February-2026',30000,2500,1200,33700,'Net Banking','Punjab National Bank','123456789006','PUNB0001006',GETDATE(),'Paid'),
('SAL007',7,'February-2026',36000,3500,1500,41000,'Net Banking','Canara Bank','123456789007','CNRB0001007',GETDATE(),'Paid'),
('SAL008',8,'February-2026',42000,4000,2000,48000,'Net Banking','Union Bank','123456789008','UBIN0001008',GETDATE(),'Paid'),
('SAL009',9,'February-2026',28000,1500,1000,30500,'Net Banking','Indian Bank','123456789009','IDIB0001009',GETDATE()+10,'Pending'),
('SAL010',10,'February-2026',39000,3000,1800,43800,'Net Banking','Bank of India','123456789010','BKID0001010',GETDATE(),'Paid'),
('SAL011',11,'March-2026',41000,4500,2000,47500,'Net Banking','Kotak Mahindra Bank','123456789011','KKBK0001011',GETDATE(),'Paid'),
('SAL012',12,'March-2026',29000,2000,700,31700,'Net Banking','Yes Bank','123456789012','YESB0001012',GETDATE(),'Hold'),
('SAL013',13,'March-2026',33000,2500,1500,37000,'Net Banking','IndusInd Bank','123456789013','INDB0001013',GETDATE(),'Paid'),
('SAL014',14,'March-2026',50000,6000,3000,59000,'Net Banking','HDFC Bank','123456789014','HDFC0001014',GETDATE()+2,'Paid'),
('SAL015',15,'April-2026',27000,1500,600,29100,'Net Banking','ICICI Bank','123456789015','ICIC0001015',GETDATE(),'Pending'),
('SAL016',16,'April-2026',38000,3500,2000,43500,'Net Banking','Axis Bank','123456789016','UTIB0001016',GETDATE(),'Paid'),
('SAL017',17,'April-2026',34000,2500,1200,37700,'Net Banking','State Bank of India','123456789017','SBIN0001017',GETDATE()+7,'Paid'),
('SAL018',18,'April-2026',46000,5000,2200,53200,'Net Banking','Bank of Baroda','123456789018','BARB0001018',GETDATE(),'Paid'),
('SAL019',19,'May-2026',31000,2200,900,34100,'Net Banking','Punjab National Bank','123456789019','PUNB0001019',GETDATE()+15,'Hold'),
('SAL020',20,'May-2026',55000,7000,3500,65500,'Net Banking','ICICI Bank','123456789020','ICIC0001020',GETDATE(),'Paid');

```

### 🆕 Verify Table Creation  

```sql

select * from tbl_Salary

```
<img width="1360" height="450" alt="image" src="https://github.com/user-attachments/assets/cd9294cd-62db-4790-8049-c8f9b10613c5" />

<br clear="both">

> ✅ **Result:** The `tbl_Salary` table is successfully created and ready for the next step.
 













