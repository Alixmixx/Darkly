**Vulnerability Type: Hidden Input Manipulation in HTML**

**Explanation of the Exercise:**

In this exercise, the focus is on the password recovery page of a website. Through the use of Burp Repeater, the attacker identifies a hidden input field within the HTML form:

```html
<form action="#" method="POST">
    <input type="hidden" name="mail" value="webmaster@borntosec.com" maxlength="15">
    <input type="submit" name="Submit" value="Submit">
</form>
```

By inspecting the page, the hidden input is discovered and manipulated. The attacker removes the original value and replaces it with "admin," leading to successful exploitation and obtaining a flag:

```
The flag is: 1d4855f7337c0c14b6f44946872c4eb33853f40b2d54393fbe94f49f1e19bbb0
```

**Impact:**

The impact of this hidden input manipulation is significant, as unauthorized users can exploit the vulnerability to gain access to sensitive information or perform actions on behalf of another user. In this case, the attacker successfully altered the hidden input to reveal a password recovery flag, demonstrating the potential for unauthorized access.

**Demonstration to Avoid the Problem:**

To mitigate this issue, developers should employ proper server-side validation and verification mechanisms. Hidden inputs should not be solely relied upon for security. Additionally, implementing strong authentication practices, such as multi-factor authentication, can add an extra layer of protection.

In this specific case, the server should validate the submitted values on the server side and ensure that the request is legitimate. Input validation should be performed on both client and server sides to prevent malicious manipulation.

By adopting secure coding practices and validating user inputs thoroughly, developers can minimize the risk of hidden input manipulation and similar attacks.

