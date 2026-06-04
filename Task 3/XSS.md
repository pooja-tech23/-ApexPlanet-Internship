# Cross-Site Scripting (XSS)

## Objective

To understand and demonstrate the Cross-Site Scripting (XSS) vulnerability using DVWA and learn how improper input validation can allow malicious scripts to execute in a user's browser.

---

## What is Cross-Site Scripting (XSS)?

Cross-Site Scripting (XSS) is a web application vulnerability that allows attackers to inject malicious client-side scripts into web pages viewed by other users. These scripts execute in the victim's browser and can steal information, manipulate web content, or perform actions on behalf of the user.

XSS is one of the most common web vulnerabilities and is included in the OWASP Top 10.

---

## How XSS Works

Web applications often accept user input and display it on web pages. If the input is not properly validated or encoded, malicious JavaScript code can be executed in the browser.

### Vulnerable Example

```html
Welcome, <user_input>
```

If an attacker enters:

```html
<script>alert('XSS')</script>
```

The browser executes the script and displays an alert box.

---

## Types of XSS

### 1. Reflected XSS

Malicious script is reflected from the web server and executed immediately when a victim clicks a crafted link.

### 2. Stored XSS

Malicious script is permanently stored in the application's database and executed whenever users view the affected page.

### 3. DOM-Based XSS

The vulnerability exists in client-side JavaScript code where user input modifies the Document Object Model (DOM).

---

## Impact of XSS

* Session cookie theft
* User impersonation
* Credential theft
* Website defacement
* Keylogging attacks
* Redirection to malicious websites
* Execution of unauthorized actions

---

## XSS in DVWA

DVWA provides modules to demonstrate different XSS vulnerabilities.

### Environment

* Attacker Machine: Kali Linux
* Target Application: DVWA
* Browser: Firefox/Chrome
* Security Level: Low

### Demonstration

In the XSS module, entering the following payload:

```html
<script>alert('XSS')</script>
```

causes a JavaScript alert box to appear, proving that arbitrary scripts can be executed in the browser.

For Stored XSS, the payload is saved in the application and executes whenever the affected page is loaded.

---

## Attack Process

1. Attacker injects malicious JavaScript code.
2. Application stores or reflects the script.
3. Victim visits the vulnerable page.
4. Browser executes the malicious script.
5. Attacker gains access to sensitive information or performs unauthorized actions.

---

## Prevention Techniques

### Input Validation

Validate and restrict user input before processing.

### Output Encoding

Convert special characters into safe HTML entities.

Example:

```html
<script>
```

becomes

```html
&lt;script&gt;
```

### Additional Security Measures

* Content Security Policy (CSP)
* HttpOnly cookies
* Secure coding practices
* Input sanitization
* Regular security testing

---

## Results

The DVWA XSS module demonstrates how malicious scripts can be executed when user input is not properly validated. At the Low Security Level, the vulnerability is easily exploitable, emphasizing the importance of secure input handling and output encoding.

---

## Conclusion

Cross-Site Scripting (XSS) is a serious web application vulnerability that allows attackers to execute malicious scripts in users' browsers. Proper input validation, output encoding, Content Security Policies, and secure development practices are essential to protect web applications from XSS attacks.
