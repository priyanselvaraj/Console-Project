# Banking Management System - Week 3

## Topic
**LinkedHashMap Storage**

## Objective
Upgrade the banking application to use `LinkedHashMap<Integer, Account>` so that accounts can be accessed by Account ID while preserving the order in which accounts were created.

## Core Features
- Create a new bank account
- Deposit money
- Withdraw money
- Check account balance
- Prevent duplicate Account IDs
- View all accounts
- Preserve insertion order
- Maintain clean separation between account data and banking operations

## Technical Focus
- Use `LinkedHashMap<Integer, Account>` as the main storage structure.
- Use Account ID as the key.
- Use `.get()` for direct account lookup.
- Use `.containsKey()` to prevent duplicate IDs.
- Use iteration over `entrySet()` or `values()` for the **View All Accounts** operation.
- Maintain a clean DAO-style separation for storage-related operations where appropriate.

## Why LinkedHashMap?
A normal `HashMap` provides efficient key-based access but does not guarantee insertion order. `LinkedHashMap` maintains the order in which entries were inserted.

Example:

```text
Created:
1003
1001
1002

View All Accounts:
1003
1001
1002
```

## Operations

### 1. Create Account
- Read Account ID and account-holder details.
- Check whether the ID already exists.
- Add the account using `put()`.

### 2. Deposit
- Find the account using `get(accountId)`.
- Increase the balance by the deposit amount.

### 3. Withdraw
- Find the account using `get(accountId)`.
- Verify sufficient balance.
- Deduct the amount when valid.

### 4. Balance Check
- Retrieve the account using its Account ID.
- Display the current balance.

### 5. View All Accounts
Iterate through the `LinkedHashMap` and display every account in its exact insertion order.

Example:

```text
Account ID: 1001
Name: Arun
Balance: 5000.0

Account ID: 1002
Name: Kumar
Balance: 3000.0
```

## Acceptance Criteria
- Create, deposit, withdraw, and balance-check operations work correctly.
- Duplicate Account IDs are rejected.
- Accounts are retrieved directly using their keys.
- **View All Accounts** displays records in the exact order they were inserted.
- Storage is implemented using `LinkedHashMap`.
- Account and storage logic remain cleanly organized.

## Example Test Cases

| Test | Expected Result |
|---|---|
| Create 1001 | Account created |
| Create 1002 | Account created |
| Create 1001 again | Duplicate rejected |
| Deposit into 1001 | Balance updated |
| Withdraw from 1002 | Balance updated |
| View All Accounts | 1001 then 1002 |
| Create 1003 | Added at the end |
| View All Accounts again | 1001, 1002, 1003 |

## Technologies
- Java
- `LinkedHashMap`
- Classes and Objects
- Collections
- Iteration
- DAO-style organization
- Console input/output

## Run

```bash
javac BankingManagementSystem.java
java BankingManagementSystem
```

## Week 3 Outcome
A banking application using **LinkedHashMap** that provides direct account lookup while preserving **exact insertion order for the View All Accounts feature**.
