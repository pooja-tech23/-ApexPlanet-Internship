
# SQL Injection (SQLi)

## Objective

To understand and demonstrate the SQL Injection vulnerability using DVWA and learn how improper input validation can lead to unauthorized database access.

---

## What is SQL Injection?

SQL Injection (SQLi) is a web security vulnerability that allows an attacker to manipulate SQL queries executed by a database. It occurs when user-supplied input is directly included in SQL statements without proper validation or sanitization.

SQL Injection is one of the most critical web application vulnerabilities and is included in the OWASP Top 10 Web Security Risks.

---

## Vulnerable Query Example

A web application may use a query such as:

```sql
SELECT first_name, last_name 
FROM users 
WHERE user_id = '$id';
```

If the application accepts user input without validation, an attacker can modify the query structure.

### Malicious Input

```sql
1' OR '1'='1
```

Resulting Query:

```sql
SELECT first_name, last_name
FROM users
WHERE user_id = '1' OR '1'='1';
```

Since the condition `'1'='1'` is always true, the database returns all records.

---

## SQL Injection Attack Process

1. User enters malicious input into a form field.
2. Application sends the input directly to the database.
3. Database interprets the injected SQL code as part of the query.
4. Unauthorized data is displayed or database actions are performed.

---

## Impact of SQL Injection

* Authentication bypass
* Disclosure of sensitive information
* Extraction of usernames and passwords
* Modification of database records
* Deletion of important data
* Complete database compromise

---

## SQL Injection in DVWA

DVWA provides a vulnerable SQL Injection module for learning purposes.

### Environment

* Attacker Machine: Kali Linux
* Target Application: DVWA
* Database: MariaDB/MySQL
* Security Level: Low

### Demonstration

In the SQL Injection page of DVWA, entering a normal user ID:

```sql
1
```

returns information about a single user.

By supplying crafted SQL input, an attacker can manipulate the database query and retrieve additional information that should not be accessible.

---

## Types of SQL Injection

### 1. Error-Based SQL Injection

Uses database error messages to gather information about the database structure.

### 2. Union-Based SQL Injection

Uses the UNION operator to combine results from multiple queries and extract data.

### 3. Boolean-Based Blind SQL Injection

Determines information by observing application responses to TRUE/FALSE conditions.

### 4. Time-Based Blind SQL Injection

Uses database delays to infer information when no output is displayed.

---

## Detection Methods

* Manual testing of input fields
* Error message analysis
* Automated vulnerability scanners
* Penetration testing tools

---

## Prevention Techniques

### Prepared Statements

```php
$stmt = $pdo->prepare(
    "SELECT * FROM users WHERE id = ?"
);
$stmt->execute([$id]);
```

### Additional Security Measures

* Input validation
* Input sanitization
* Parameterized queries
* Least privilege database accounts
* Secure error handling
* Web Application Firewall (WAF)

---

## Results

The DVWA SQL Injection module demonstrates how insecure coding practices can allow attackers to access database information. The vulnerability is easily exploitable at the Low Security Level, highlighting the importance of secure input handling and parameterized queries.

---

## Conclusion

SQL Injection is a critical web application vulnerability that can lead to unauthorized access, data leakage, and database compromise. By implementing prepared statements, proper input validation, and secure coding practices, organizations can effectively protect their applications from SQL Injection attacks.
