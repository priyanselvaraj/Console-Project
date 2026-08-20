# Banking Management System - Week 1

## Topic
**ArrayList Storage**

## Objective
Build the basic Banking Management System using Java's `ArrayList<Account>` as the in-memory data store.

## Core Features
- Create a new bank account
- Deposit money
- Withdraw money
- Check account balance
- Prevent duplicate Account IDs
- Search for accounts using manual iteration
- Store data only during the current program execution

## Technical Focus
- Use `ArrayList<Account>` for storage.
- Use manual `for` or `while` loops to search for an account.
- Validate the Account ID before creating a new account.
- Separate account data from banking operations using an `Account` class and appropriate methods.

## Suggested Account Structure
An account can contain:
- Account ID
- Account holder name
- Balance

## Operations

### 1. Create Account
The user enters account details. Before adding the account, the program searches the `ArrayList` to make sure the Account ID is not already present.

### 2. Deposit
- Ask for the Account ID.
- Search the `ArrayList`.
- Add the deposit amount to the account balance.

### 3. Withdraw
- Ask for the Account ID.
- Search the `ArrayList`.
- Check whether sufficient balance is available.
- Deduct the withdrawal amount if valid.

### 4. Balance Check
- Ask for the Account ID.
- Search the `ArrayList`.
- Display the current balance.

## Acceptance Criteria
- Duplicate Account IDs are rejected using iteration.
- Create, deposit, withdraw, and balance-check operations work correctly.
- Account data is stored in an `ArrayList`.
- Manual search loops (`for`/`while`) are used for lookup.
- Data resets when the program is restarted because Week 1 does not use file/database persistence.

## Example Test Cases

| Test | Expected Result |
|---|---|
| Create Account ID 1001 | Account created |
| Create Account ID 1001 again | Duplicate ID rejected |
| Deposit 500 into 1001 | Balance increases by 500 |
| Withdraw 200 from 1001 | Balance decreases by 200 |
| Withdraw more than balance | Withdrawal rejected |
| Check balance for 1001 | Correct balance displayed |
| Restart program | Previous data is cleared |

## Technologies
- Java
- `ArrayList`
- Classes and Objects
- Loops
- Conditional statements
- Console input/output

## Run
Compile and execute the Java program using any Java-supported IDE or terminal.

```bash
javac BankingManagementSystem.java
java BankingManagementSystem
```

## Week 1 Outcome
A working console-based banking application with **ArrayList-based storage and manual account searching**.
