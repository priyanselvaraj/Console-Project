# Week 6 -- CSV Banking System

## 📌 Project Overview

The **CSV Banking System** is a Java console-based application that
stores bank account data in a **CSV file**.

Users can:

-   Create an account
-   Deposit money
-   Withdraw money
-   Check account balance

All data is stored in `accounts.csv`, so it remains available even after
restarting the program.

------------------------------------------------------------------------

## 🎯 Week 6 Objective

**Target Objective:** File Storage (CSV)

**Technical Focus:**

-   Use CSV file format
-   Use `BufferedReader`
-   Use `BufferedWriter`
-   Parse comma-separated data correctly
-   Store and restore account objects

------------------------------------------------------------------------

## ✨ Features

1.  Create Account
2.  Deposit Money
3.  Withdraw Money
4.  Balance Check
5.  Prevent Duplicate Account IDs
6.  Save Data to CSV
7.  Load Data Automatically After Restart

------------------------------------------------------------------------

## 🛠️ Technologies Used

-   Java
-   ArrayList
-   BufferedReader
-   BufferedWriter
-   FileReader
-   FileWriter
-   CSV File Storage

------------------------------------------------------------------------

## 📂 Project Structure

``` text
Week6_CSV_Banking_System/
│
├── Main.java
├── accounts.csv
└── README.md
```

------------------------------------------------------------------------

## 💾 CSV File Format

``` csv
ID,Name,Balance
101,Priyan,5000.0
102,Arun,2500.0
```

------------------------------------------------------------------------

## ⚙️ Requirements

Make sure Java is installed.

``` bash
java -version
javac -version
```

Recommended: **Java 17 or later**.

------------------------------------------------------------------------

## ▶️ How to Run

### Step 1: Open the project folder

``` powershell
cd Week6_CSV_Banking_System
```

### Step 2: Compile the program

``` powershell
javac Main.java
```

### Step 3: Run the program

``` powershell
java Main
```

------------------------------------------------------------------------

## 🖥️ Application Menu

``` text
===== CSV BANKING SYSTEM =====
1. Create Account
2. Deposit
3. Withdraw
4. Balance Check
5. Exit
Enter Choice:
```

------------------------------------------------------------------------

## 🧪 Sample Execution

### Create Account

``` text
Enter Choice: 1
Enter Account ID: 101
Enter Account Name: Priyan

Account created successfully.
```

### Deposit Money

``` text
Enter Choice: 2
Enter Account ID: 101
Enter Deposit Amount: 5000

Deposit successful.
Current Balance: ₹5000.0
```

### Withdraw Money

``` text
Enter Choice: 3
Enter Account ID: 101
Enter Withdrawal Amount: 1000

Withdrawal successful.
Current Balance: ₹4000.0
```

### Balance Check

``` text
Enter Choice: 4
Enter Account ID: 101

----- ACCOUNT DETAILS -----
Account ID : 101
Name       : Priyan
Balance    : ₹4000.0
```

------------------------------------------------------------------------

## 💾 Data Persistence

After creating or updating an account, the data is automatically saved
in:

``` text
accounts.csv
```

Example:

``` csv
ID,Name,Balance
101,Priyan,4000.0
```

When the program is restarted, the application reads the CSV file and
restores the account data.

✅ Data persists after restart.

------------------------------------------------------------------------

## 🔐 Validations

The application checks:

-   Duplicate Account IDs are not allowed
-   Account must exist before deposit
-   Account must exist before withdrawal
-   Deposit amount must be greater than zero
-   Withdrawal amount must be greater than zero
-   Withdrawal cannot exceed available balance

------------------------------------------------------------------------

## 📋 Week 6 Acceptance Criteria

  Requirement               Status
  ------------------------- --------
  Create Account            ✅
  Deposit                   ✅
  Withdraw                  ✅
  Balance Check             ✅
  CSV File Storage          ✅
  BufferedReader            ✅
  BufferedWriter            ✅
  CSV Parsing               ✅
  Data Persistence          ✅
  Duplicate ID Prevention   ✅
  Single Java File          ✅

------------------------------------------------------------------------

## 🧠 Concepts Used

-   Java Classes and Objects
-   ArrayList
-   Methods
-   Loops
-   Conditional Statements
-   Exception Handling
-   File Handling
-   CSV Parsing
-   Data Persistence

------------------------------------------------------------------------

## 🚀 Future Improvements

-   View All Accounts
-   Delete Account
-   Update Account Details
-   Money Transfer
-   Transaction History
-   Login System
-   MySQL Database Integration
-   JavaFX GUI

------------------------------------------------------------------------

## 👨‍💻 Project Information

**Subject:** Java\
**Semester:** 5\
**Week:** 6\
**Topic:** File Storage (CSV)\
**Application Type:** Console-Based Banking System

------------------------------------------------------------------------

## 📄 License

This project is created for **educational and academic purposes**.
