# 🔥XSS & CSRF Attacks

<img src="./assets/images/xss_csrf.png" alt="xss_csrf" width="700">

## ⚡Cross-Site Scripting (XSS)

> Refer **xss section** in Injection Attacks 🚀

## ⚡Cross-Site Request Forgery (CSRF)

?> **Cross-Site Request Forgery (CSRF)** is an attack that forces an end user to execute unwanted actions on a web application in which they’re currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request. If the victim is a normal user, a successful CSRF attack can force the user to perform state changing requests like transferring funds, changing their email address, and so forth. If the victim is an administrative account, CSRF can compromise the entire web application.

## ⚡Protect against XSS & CSRF attacks

* Escape special characters, validate and sanitize inputs
* [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
* [Secure + HTTPOnly Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
* Using CSRF-token

## Playgrounds to test XSS and CSRF Attacks

[CSRF Playground](https://www.hacksplaining.com/exercises/csrf)

[XSS Playground](https://www.hacksplaining.com/exercises/xss-stored)
