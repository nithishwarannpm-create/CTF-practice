# CTF Day 4 - SQL Injection

## What I Did

Today I solved **3 SQL Injection labs** from PortSwigger Web Security Academy using **Burp Suite**.

## Tools Used

* PortSwigger Web Security Academy
* Burp Suite
* Web Browser

## Concepts I Learned

### 1. Basic SQL Injection

I learned how SQL Injection works when user input is directly included in a SQL query.

A basic example I practiced was:

```sql
' OR 1=1--
```

`1=1` is always true, and `--` can comment out the remaining part of the SQL query.

This helped me understand how the original SQL query logic can be changed through user input.

---

### 2. Login Bypass

I solved a lab where SQL Injection could be used to bypass the login mechanism and access the administrator account without knowing the password.

I learned that SQL Injection can affect authentication when the application does not properly handle user input.

---

### 3. UNION SQL Injection

I learned how the `UNION` keyword can be used in SQL Injection.

```sql
UNION SELECT
```

One important step is finding the **number of columns** in the original SQL query.

The number of columns in the `UNION SELECT` must match the original query.

---

## Burp Suite Technique

I used Burp Suite to intercept and modify HTTP requests.

```text
Browser
   ↓
Burp Suite
   ↓
Intercept Request
   ↓
Modify Parameter
   ↓
Send Request
   ↓
Analyze Response
```

This helped me understand how user input travels from the browser to the server.

---

## Labs Solved

Today I completed **3 SQL Injection labs**:

1. Basic SQL Injection
2. Authentication/Login Bypass
3. UNION-based SQL Injection and Column Count

---

## Key Takeaways

* SQL Injection can change the logic of an SQL query.
* `OR 1=1` is a basic example of manipulating a condition.
* SQL Injection can sometimes bypass authentication.
* `UNION` can combine results from SQL queries.
* UNION attacks require the correct number of columns.
* Burp Suite is useful for intercepting and modifying HTTP requests.
* Understanding the SQL query is more important than memorizing payloads.
* SQL Injection should only be practiced on authorized labs or systems.

## Day 4 Summary

```text
SQL Injection
      ↓
Burp Suite
      ↓
OR 1=1
      ↓
Login Bypass
      ↓
UNION
      ↓
Find Column Count
      ↓
Solve Lab
```

Today I gained my first practical experience with **SQL Injection using Burp Suite**.
