# Banking Management System - Overall README

## Project Overview

The **Banking Management System** is a console-based Java application developed to demonstrate the progressive use of Java Collections, file handling, JSON processing, and object serialization.

The project is developed over **8 weeks**. Each week keeps the core banking operations such as account creation, deposit, withdrawal, and balance checking while changing the storage technique and technical implementation.

## Main Objectives

- Create and manage bank accounts.
- Deposit money into an account.
- Withdraw money from an account.
- Check account balance.
- Prevent duplicate Account IDs.
- Retrieve account information efficiently.
- Display accounts in insertion or sorted order where required.
- Store data using text files, CSV, JSON, and Java serialization.
- Demonstrate practical Java Collection Framework and file-handling concepts.

---

# Weekly Development Plan

| Week | Target Objective | Storage / Technology | Main Feature |
|---|---|---|---|
| Week 1 | ArrayList Storage | `ArrayList<Account>` | Manual search using loops |
| Week 2 | HashMap Storage | `HashMap<Integer, Account>` | Direct lookup using Account ID |
| Week 3 | LinkedHashMap Storage | `LinkedHashMap<Integer, Account>` | Preserve insertion order |
| Week 4 | TreeMap Storage | `TreeMap<Integer, Account>` | Sorted Account ID ledger |
| Week 5 | File Storage - Text File | `.txt` + `BufferedReader/Writer` | Persistent structured text |
| Week 6 | File Storage - CSV | `.csv` | CSV parsing and updating |
| Week 7 | File Storage - JSON | JSON | Convert objects to/from JSON |
| Week 8 | Serialization | `.dat` / `.ser` | Binary object persistence |

---

# Week 1 - ArrayList Storage

## Objective

Implement the Banking Management System using:

```java
ArrayList<Account>
```

## Features

- Create Account
- Deposit
- Withdraw
- Balance Check

## Technical Focus

Accounts are stored in an `ArrayList`. Manual `for` or `while` loops are used to search for an Account ID.

## Duplicate Validation

Before creating an account, the program iterates through the list and checks whether the Account ID already exists.

## Acceptance Criteria

- Duplicate Account IDs are prevented using iteration.
- Create, deposit, withdraw, and balance-check operations work.
- Data is stored only in memory.
- Data is lost when the program restarts.

---

# Week 2 - HashMap Storage

## Objective

Replace the ArrayList implementation with:

```java
HashMap<Integer, Account>
```

## Features

- Create Account
- Deposit
- Withdraw
- Balance Check

## Technical Focus

The Account ID becomes the key in the HashMap.

```java
accounts.get(accountId);
```

This allows direct retrieval without manually searching through the collection.

## Duplicate Validation

Use:

```java
accounts.containsKey(accountId);
```

to detect duplicate Account IDs.

## Acceptance Criteria

- No manual search loops are used for account lookup.
- Accounts are retrieved directly using their keys.
- Duplicate IDs are rejected.
- Data is still in memory and resets after restart.

---

# Week 3 - LinkedHashMap Storage

## Objective

Use:

```java
LinkedHashMap<Integer, Account>
```

to maintain direct key-based lookup while preserving account insertion order.

## Features

- Create Account
- Deposit
- Withdraw
- Balance Check
- View All Accounts

## Technical Focus

`LinkedHashMap` maintains the order in which accounts were inserted.

Example:

```text
Created:
1003
1001
1002

View All:
1003
1001
1002
```

## Acceptance Criteria

- Account lookup uses the Account ID key.
- Duplicate IDs are rejected.
- View All Accounts displays records in exact insertion order.
- Account and storage responsibilities remain cleanly organized.

---

# Week 4 - TreeMap Storage

## Objective

Use:

```java
TreeMap<Integer, Account>
```

to automatically maintain accounts in sorted Account ID order.

## Features

- Create Account
- Deposit
- Withdraw
- Balance Check
- View Sorted Ledger

## Technical Focus

`TreeMap` naturally sorts integer Account IDs.

Example:

```text
Insertion:
1050
1002
1010
1001

Sorted Ledger:
1001
1002
1010
1050
```

## Acceptance Criteria

- Account lookup is performed directly using the Account ID.
- Duplicate IDs are rejected.
- The sorted ledger always displays accounts in Account ID order.
- Sorting does not depend on insertion order.

---

# Week 5 - File Storage Using Text File

## Objective

Add persistent storage using a text file.

## Technology

- `.txt` file
- `BufferedReader`
- `BufferedWriter` or `FileWriter`
- Delimiter-based parsing

## Features

- Create Account
- Deposit
- Withdraw
- Balance Check

## Technical Focus

Account information is written to a text file in a structured format.

Example:

```text
1001|Arun|5000.0
1002|Kumar|3000.0
1003|Ravi|7500.0
```

The program reads the file when starting and writes updated account information back to the file.

## Acceptance Criteria

- Data persists after program restart.
- The text file contains readable structured account data.
- Account records can be loaded correctly.
- Deposit and withdrawal updates are reflected in the file.

---

# Week 6 - File Storage Using CSV

## Objective

Replace delimiter-based text storage with standard CSV storage.

## Technology

- `.csv` file
- CSV parsing
- File reading and writing

## Features

Same core features as Week 5:

- Create Account
- Deposit
- Withdraw
- Balance Check

## Example CSV Format

```csv
AccountID,HolderName,Balance
1001,Arun,5000.0
1002,Kumar,3000.0
1003,Ravi,7500.0
```

## Technical Focus

The program must correctly handle:

- Commas
- Spaces
- Header rows
- Numeric conversion
- Reading records
- Updating records

## Acceptance Criteria

- CSV file is updated correctly.
- Data can be loaded after restarting the program.
- Records are parsed without corruption.
- Account information remains consistent.

---

# Week 7 - File Storage Using JSON

## Objective

Store account objects using JSON format.

## Technology

- `.json` file
- JSON conversion
- JSON parsing
- Manual JSON handling or a suitable Java JSON library

## Features

Same core banking operations:

- Create Account
- Deposit
- Withdraw
- Balance Check

## Example JSON Structure

```json
[
  {
    "accountId": 1001,
    "holderName": "Arun",
    "balance": 5000.0
  },
  {
    "accountId": 1002,
    "holderName": "Kumar",
    "balance": 3000.0
  }
]
```

## Technical Focus

The application converts account objects into JSON for storage and parses JSON back into Java objects when loading data.

## Acceptance Criteria

- Valid JSON structure is stored.
- JSON can be parsed correctly.
- Account objects are restored correctly.
- Data remains available after program restart.

---

# Week 8 - Java Serialization

## Objective

Use Java object serialization for binary storage.

## Technology

- `Serializable`
- `ObjectOutputStream`
- `ObjectInputStream`
- `.dat` or `.ser` file

## Features

Same core banking operations:

- Create Account
- Deposit
- Withdraw
- Balance Check

## Technical Focus

The `Account` class implements:

```java
Serializable
```

Objects are written directly to a binary file using `ObjectOutputStream` and restored using `ObjectInputStream`.

## Example

```java
ObjectOutputStream out =
    new ObjectOutputStream(new FileOutputStream("accounts.dat"));

out.writeObject(accounts);
out.close();
```

Loading:

```java
ObjectInputStream in =
    new ObjectInputStream(new FileInputStream("accounts.dat"));

Object data = in.readObject();
in.close();
```

## Acceptance Criteria

- Object data persists in `.dat` or `.ser`.
- Serialized data can be loaded correctly.
- Account objects are restored after restart.
- Banking operations continue to work with restored data.

---

# Common Account Structure

All weeks are based on the same basic `Account` concept.

## Attributes

| Attribute | Type | Description |
|---|---|---|
| `accountId` | `int` | Unique Account ID |
| `holderName` | `String` | Account holder name |
| `balance` | `double` | Current account balance |

## Main Methods

```java
createAccount()
deposit()
withdraw()
checkBalance()
```

Additional methods may be added according to the storage implementation.

---

# Common Banking Operations

## 1. Create Account

1. Read Account ID.
2. Check whether the Account ID already exists.
3. Reject duplicate IDs.
4. Read account-holder name.
5. Read initial balance.
6. Create the Account object.
7. Store the account.

## 2. Deposit

1. Read Account ID.
2. Find the account.
3. Read deposit amount.
4. Validate the amount.
5. Add the amount to the balance.
6. Save updated data if persistent storage is being used.

## 3. Withdraw

1. Read Account ID.
2. Find the account.
3. Read withdrawal amount.
4. Validate the amount.
5. Check available balance.
6. Deduct the amount if sufficient.
7. Save updated data if persistent storage is being used.

## 4. Balance Check

1. Read Account ID.
2. Find the account.
3. Display account details.
4. Display current balance.

---

# Project Architecture

```text
Banking Management System
|
+-- Account
|   +-- accountId
|   +-- holderName
|   +-- balance
|
+-- Banking Operations
|   +-- Create Account
|   +-- Deposit
|   +-- Withdraw
|   +-- Balance Check
|   +-- View Accounts
|
+-- Storage Layer
    |
    +-- Week 1: ArrayList
    +-- Week 2: HashMap
    +-- Week 3: LinkedHashMap
    +-- Week 4: TreeMap
    +-- Week 5: Text File
    +-- Week 6: CSV
    +-- Week 7: JSON
    +-- Week 8: Serialization
```

---

# Data Storage Progression

```text
Week 1
ArrayList
   |
   v
Week 2
HashMap
   |
   v
Week 3
LinkedHashMap
   |
   v
Week 4
TreeMap
   |
   v
Week 5
Text File
   |
   v
Week 6
CSV File
   |
   v
Week 7
JSON File
   |
   v
Week 8
Java Serialization
```

---

# Acceptance Criteria Summary

| Week | Main Verification |
|---|---|
| 1 | Duplicate IDs prevented using ArrayList iteration |
| 2 | Direct HashMap lookup without search loops |
| 3 | View All Accounts preserves insertion order |
| 4 | Sorted Ledger always displays Account IDs in order |
| 5 | Data persists and text file contains readable structured data |
| 6 | CSV is correctly updated and parsed |
| 7 | Valid JSON is stored and restored into objects |
| 8 | Serialized objects persist and reload correctly |

---

# Technologies Used

- Java
- Object-Oriented Programming
- Java Collections Framework
- ArrayList
- HashMap
- LinkedHashMap
- TreeMap
- File I/O
- BufferedReader
- BufferedWriter
- CSV
- JSON
- Java Serialization
- Scanner
- Exception Handling

---

# How to Compile and Run

For a Java program named `BankingManagementSystem.java`:

```bash
javac BankingManagementSystem.java
java BankingManagementSystem
```

For later weeks, make sure the required storage file or JSON library is available before running the program.

---

# Project Outcomes

By completing all 8 weeks, the project demonstrates:

1. Basic Java collection usage.
2. Manual searching with `ArrayList`.
3. Efficient key-based lookup with `HashMap`.
4. Insertion-order preservation with `LinkedHashMap`.
5. Automatic sorting with `TreeMap`.
6. Persistent text-file storage.
7. CSV-based storage and parsing.
8. JSON object conversion and restoration.
9. Java binary object serialization.
10. Progressive improvement of a real-world banking application.

---

# Future Enhancements

Possible future improvements include:

- Database connectivity using JDBC.
- MySQL or PostgreSQL storage.
- User login and authentication.
- Transaction history.
- Fund transfer between accounts.
- Interest calculation.
- ATM-style interface.
- JavaFX graphical user interface.
- REST API integration.
- Role-based access for customers and administrators.

---

# Conclusion

The Banking Management System is a progressive Java project that starts with simple in-memory collections and develops into persistent data-storage solutions.

Across Weeks 1 to 4, the project demonstrates the differences between `ArrayList`, `HashMap`, `LinkedHashMap`, and `TreeMap`. Weeks 5 to 8 extend the project into persistent storage using text files, CSV, JSON, and Java serialization.

This progression provides practical experience with **Java Collections, object-oriented programming, searching, sorting, file handling, data persistence, parsing, JSON processing, and serialization**.
