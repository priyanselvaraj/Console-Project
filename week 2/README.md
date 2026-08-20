# Banking Management System - Week 2

## Topic
**HashMap Storage**

## Objective
Improve the Week 1 banking application by replacing `ArrayList<Account>` with `HashMap<Integer, Account>` for faster direct account lookup.

## Core Features
- Create a new bank account
- Deposit money
- Withdraw money
- Check account balance
- Prevent duplicate Account IDs
- Retrieve accounts directly using the Account ID
- Store data only during the current program execution

## Technical Focus
- Replace `ArrayList<Account>` with `HashMap<Integer, Account>`.
- Use the Account ID as the key.
- Use `.get(accountId)` to retrieve an account.
- Remove manual search loops for account lookup.
- Use `.containsKey(accountId)` to check for duplicate IDs.

## HashMap Structure

```text
Account ID  ->  Account Object

1001        ->  Account(1001, "User", 5000)
1002        ->  Account(1002, "User", 3000)
```

The Account ID becomes the unique key, making lookup simpler than searching through an `ArrayList`.

## Operations

### 1. Create Account
- Read the Account ID.
- Check `containsKey(accountId)`.
- Reject the account if the ID already exists.
- Otherwise create an `Account` object and store it using `put()`.

### 2. Deposit
- Read the Account ID.
- Retrieve the account using `get(accountId)`.
- Add the deposit amount to the balance.

### 3. Withdraw
- Read the Account ID.
- Retrieve the account using `get(accountId)`.
- Verify sufficient balance.
- Deduct the amount when valid.

### 4. Balance Check
- Read the Account ID.
- Use `get(accountId)`.
- Display the account balance.

## Acceptance Criteria
- No manual search loops are used for account lookup.
- Account data is retrieved directly using the Account ID key.
- Duplicate Account IDs are rejected.
- Create, deposit, withdraw, and balance-check operations work correctly.
- Data is lost after program restart because persistence has not yet been introduced.

## Example Test Cases

| Test | Expected Result |
|---|---|
| Create Account ID 1001 | Account created |
| Create Account ID 1001 again | Duplicate ID rejected |
| Deposit 1000 into 1001 | Balance increases |
| Withdraw 300 from 1001 | Balance decreases |
| Search for 1001 | Account retrieved directly |
| Search for unknown ID | Account-not-found message |
| Restart program | Previous data is cleared |

## Technologies
- Java
- `HashMap`
- Classes and Objects
- `containsKey()`
- `put()`
- `get()`
- Console input/output

## Run

```bash
javac BankingManagementSystem.java
java BankingManagementSystem
```

## Week 2 Outcome
A more efficient banking application using **HashMap-based direct account lookup without manual search loops**.
