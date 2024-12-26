
# SQL Injection (SQLi)

## Title Slide
**Title:** SQL Injection (SQLi)  
**Subtitle:** Understanding, Exploitation, and Mitigation  
**Presented by:** [Student Name]  
**Group Project:** Vulnerabilities and Attack Vectors  
**Tools Used:** OWASP Bricks, Burp Suite  

---

## What is SQL Injection?
**Definition:**  
SQL Injection is a web security vulnerability that allows an attacker to interfere with the queries an application makes to its database.

**Impact:**  
- Unauthorized data access, modification, or deletion.  
- Exposure of sensitive information such as usernames, passwords, or credit card details.  

**Example:**  
An attacker extracts sensitive information by injecting malicious SQL commands into input fields.

---

## How SQL Injection Arises
**Causes:**  
- Improper input validation.  
- Direct execution of user input in SQL queries.  
- Use of dynamic SQL without parameterization.  

**Example Code:**
```sql
SELECT * FROM users WHERE username = 'user' AND password = 'password';
```
**Malicious Input:** `' OR '1'='1`  
Resulting Query:  
```sql
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '' OR '1'='1';
```

---

## Detailed Exploitation of SQL Injection
**Types of SQL Injection:**
- **Error-based SQLi:** Exploits database error messages.  
- **Union-based SQLi:** Combines results from multiple queries.  
- **Blind SQLi:** Exploits true/false responses without visible output.  

**Exploitation Steps:**
1. Identify input fields vulnerable to SQLi (e.g., login forms, search bars).  
2. Test for vulnerability using payloads (e.g., `' OR '1'='1`).  
3. Extract data by crafting malicious queries.  

---

## Tools Used in Exploitation
**OWASP Bricks:**  
- A deliberately vulnerable web application for practicing SQLi.  
- Provides various levels of SQLi vulnerabilities.

**Burp Suite:**  
- Intercepts and manipulates HTTP requests.  
- Useful for automating and refining SQLi payloads.

**SQLMap:**  
- Automates SQLi exploitation.  
- Extracts database schema and data.

---

## Live Demonstration
**Environment Setup:**
- VirtualBox with Kali Linux.  
- OWASP Bricks hosted locally.

**Demonstration Steps:**
1. Identify a vulnerable input field.  
2. Exploit it using Burp Suite and SQLMap.

---

## Mitigation Strategies
**Best Practices:**
- Use prepared statements and parameterized queries.  
- Employ input validation and sanitization.  
- Implement robust error handling.  
- Regularly update and patch databases and web applications.

**Example of Parameterized Query:**
```python
cursor.execute("SELECT * FROM users WHERE username = ? AND password = ?", (username, password))
```

---

## Conclusion
**Summary:**
- SQL Injection is a critical vulnerability with severe consequences.  
- Exploitation requires knowledge of input fields and SQL syntax.  
- Tools like Burp Suite and SQLMap simplify the exploitation process.  
- Adopting mitigation strategies is essential for securing applications.

**Q&A:**  
Ready to answer any questions.
