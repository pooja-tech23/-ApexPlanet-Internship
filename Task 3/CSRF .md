# Cross-Site Request Forgery (CSRF)

## Objective

To understand and demonstrate the Cross-Site Request Forgery (CSRF) vulnerability using DVWA and learn how attackers can trick authenticated users into performing unintended actions.

---

## What is CSRF?

Cross-Site Request Forgery (CSRF) is a web security vulnerability that forces an authenticated user to perform unwanted actions on a web application without their knowledge or consent.

A CSRF attack exploits the trust that a website has in a user's browser. If a user is logged into a website, an attacker can craft a malicious request that is executed using the victim's active session.

CSRF is a well-known web application vulnerability and is recognized by OWASP as a significant security risk.

---

## How CSRF Works

When a user logs into a website, the browser stores a session cookie. If the user visits a malicious website while still authenticated, the attacker can cause the browser to send unauthorized requests to the target application.

### Example Request

```http
POST /change_password HTTP/1.1
Host: vulnerable-site.com

new_password=123456
```

If proper CSRF protection is not implemented, the request may be processed without verifying whether it was intentionally made by the user.

---

## Attack Process

1. User logs into a trusted web application.
2. Session cookies remain active in the browser.
3. User visits a malicious website or clicks a crafted link.
4. Malicious page sends a forged request to the target application.
5. The application accepts the request because it appears to come from the authenticated user.
6. Unauthorized action is performed.

---

## Impact of CSRF

* Unauthorized password changes
* Unauthorized account modifications
* Changing email addresses
* Unauthorized money transfers
* Modification or deletion of user data
* Execution of actions without user consent

---

## CSRF in DVWA

DVWA provides a CSRF module that demonstrates how attackers can exploit applications lacking anti-CSRF protections.

### Environment

* Attacker Machine: Kali Linux
* Target Application: DVWA
* Browser: Firefox/Chrome
* Security Level: Low

### Demonstration

In DVWA's CSRF module, the password change functionality can be abused by creating a malicious request that automatically submits new password values.

Example URL:

```html
http://localhost/DVWA/vulnerabilities/csrf/?password_new=newpass&password_conf=newpass&Change=Change
```

If an authenticated user visits a malicious page containing this request, their password may be changed without their knowledge.

---

## Detection Methods

* Review sensitive actions for CSRF protection.
* Analyze requests for anti-CSRF tokens.
* Perform penetration testing.
* Use web vulnerability scanners.
* Check whether state-changing requests require user verification.

---

## Prevention Techniques

### 1. Anti-CSRF Tokens

Generate unique tokens for each user session and validate them before processing requests.

### 2. SameSite Cookies

Configure cookies with the `SameSite` attribute to prevent cross-site request submission.

```http
Set-Cookie: sessionid=abc123; SameSite=Strict
```

### 3. Re-authentication

Require users to re-enter credentials before performing sensitive actions.

### 4. Verify Origin and Referer Headers

Ensure requests originate from trusted domains.

### 5. Use Secure Framework Protections

Modern frameworks provide built-in CSRF protection mechanisms.

---

## Results

The DVWA CSRF module demonstrates how authenticated users can unknowingly perform actions initiated by attackers. The vulnerability is easily exploitable at the Low Security Level when no anti-CSRF protections are implemented.

---

## Conclusion

Cross-Site Request Forgery (CSRF) is a critical web application vulnerability that exploits a user's authenticated session to perform unauthorized actions. Implementing anti-CSRF tokens, SameSite cookies, origin validation, and secure development practices can effectively protect applications against CSRF attacks.
