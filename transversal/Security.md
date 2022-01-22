# Security

* [OWASP](#OWASP)
  * [Top 10 Web Application Security Risks](#Top-10-Web-Application-Security-Risks)
  * [Top 10 Proactive Controls](#Top-10-Proactive-Controls)
  * [Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
* [Other Security Risks](#Other-Security-Risks)
* [MDN web docs](#MDN-web-docs)
  * [Web security](#Web-security)
  * [HTTP Headers](#HTTP-Headers)
  * [Cookies](#Cookies)
  * [Web Storage](#Web-Storage)
* [Secure Core Warrior](https://securecodewarrior.com/): great eLearning Security Platform
* Other resources: 
  [Top 10000 worst passwords](https://github.com/danielmiessler/SecLists/blob/master/Passwords/darkweb2017-top10000.txt) 
  from [SecLists](https://github.com/danielmiessler/SecLists) GitHub project
  * [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token) 
  * [auth0](https://auth0.com/) provide open-source libs to implements JWT and an authentification provider
    * [jwks](https://auth0.com/docs/secure/tokens/json-web-tokens/json-web-key-sets) aka JSON Web Key Sets is set of keys containing the public keys used to verify any JSON Web Token (JWT) issued by the authorization server
  * [RBAC](https://en.wikipedia.org/wiki/Role-based_access_control) Role-based access control is normally sufficient authorization for most applications
* Tools / Library
  * [node-argon2](https://github.com/ranisalt/node-argon2) password hash library
  * [password-validator](https://github.com/tarunbatra/password-validator) library
  
*(Page mainly written in April 2020)*

[*Go to parent page*](../README.md)


# OWASP

The [Open Web Application Security Project (OWASP)](https://owasp.org/) is a nonprofit foundation
that works to improve the security of software


## Top 10 Web Application Security Risks

* [Injection](#Injection)
* [Broken Authentication](#Broken-Authentication)
* [Sensitive Data Exposure](#Sensitive-Data-Exposure)
* [XML External Entities (XXE)](#XML-External-Entities-(XXE))
* [Broken Access Control](#Broken-Access-Control)
* [Security Misconfiguration](#Security-Misconfiguration)
* [Cross-Site Scripting XSS](#Cross-Site-Scripting-XSS)
* [Insecure Deserialization](#Insecure-Deserialization)
* [Using Components with Known Vulnerabilities](#Using-Components-with-Known-Vulnerabilities)
* [Insufficient Logging & Monitoring](#Insufficient-Logging-&-Monitoring)

*source: [OWASP Top Ten](https://owasp.org/www-project-top-ten/)*


## Injection

[Injection](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A1-Injection) 
flaws, such as SQL, NoSQL, OS, and LDAP injection, occur when untrusted data is sent to an 
interpreter as part of a command or query. The attacker’s hostile data can trick the interpreter 
into executing unintended commands or accessing data without proper authorization.

***Preventions:***
* [Secure Database Access](https://owasp.org/www-project-proactive-controls/v3/en/c3-secure-database)
* [Encode and Escape Data](https://owasp.org/www-project-proactive-controls/v3/en/c4-encode-escape-data)
* [Validate All Inputs](https://owasp.org/www-project-proactive-controls/v3/en/c5-validate-inputs)
* ([OWASP ESAPI lib for Java or JavaScript](https://owasp.org/www-project-enterprise-security-api/) 
  seems to be obsolete or no more maintain)
  

***Cheatsheets:***
* [Injection prevention rules](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html#injection-prevention-rules), 
  [Prevention in Java](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet_in_Java.html)
* [Input validation](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html)
* [Query parameterization](https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet.html)
* Injection with... 
  * [SQL ](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)
  * [LDAP](https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet.html)
  * [XPath](https://owasp.org/www-community/attacks/XPATH_Injection)
  * [Scripting languages](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html#scripting-languages)
  * [OS command](https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet.html)
  * [NoSQL](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_in_Java_Cheat_Sheet.html#nosql)
  * [Log](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_in_Java_Cheat_Sheet.html#log-injection)
  * [HTML/JavaScript/CSS](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_in_Java_Cheat_Sheet.html#htmljavascriptcss)
  * [Path Traversal](https://owasp.org/www-community/attacks/Path_Traversal)
  * [Email Header](https://en.wikipedia.org/wiki/Email_injection)
  * [CSS](https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/11-Client_Side_Testing/05-Testing_for_CSS_Injection), 
    see also [Secure CSS](https://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet.html)

[*Go to top*](#Security)


## Broken Authentication

[Broken Authentication](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A2-Broken_Authentication) : 
Application functions related to authentication and session management are often implemented 
incorrectly, allowing attackers to compromise passwords, keys, or session tokens, or to exploit 
other implementation flaws to assume other users’ identities temporarily or permanently.

***Other known risks:***
* [Insufficient Session Expiration](https://cwe.mitre.org/data/definitions/613.html)
* [Weak Session Token Generation](https://owasp.org/www-community/attacks/Session_Prediction)
* [Exposed Session Tokens](https://owasp.org/www-community/attacks/Session_hijacking_attack)


***Preventions:*** [Implement Digital Identity](https://owasp.org/www-project-proactive-controls/v3/en/c6-digital-identity)

***Cheatsheets:*** 
* [Authentication](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html), 
  [Email Address Validation](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html#email-address-validation),
  [Forgot Password](https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html), 
  [Choosing and Using Security Questions](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html#choosing-security-questions), 
  [Error handling](https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet.html), 
  [Multifactor authentication](https://cheatsheetseries.owasp.org/cheatsheets/Multifactor_Authentication_Cheat_Sheet.html), 
  [Credential Stuffing Prevention](https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html), 
  [Cross-Site Request Forgery (CSRF) Prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html), 
  [Session Management](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html)

[*Go to top*](#Security)


## Sensitive Data Exposure

[Sensitive Data Exposure](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A3-Sensitive_Data_Exposure) : 
Many web applications and APIs do not properly protect sensitive data, such as financial, 
healthcare, and PII. Attackers may steal or modify such weakly protected data to conduct credit card 
fraud, identity theft, or other crimes. Sensitive data may be compromised without extra protection, 
such as encryption at rest or in transit, and requires special precautions when exchanged with the 
browser.

***Other known risks:***
* [Unprotected Transport of Credentials](https://cwe.mitre.org/data/definitions/523.html)
* [Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
* [Using a broken or risky cryptographic algorithm](https://owasp.org/www-community/vulnerabilities/Using_a_broken_or_risky_cryptographic_algorithm) 
* [Insecure Randomness](https://owasp.org/www-community/vulnerabilities/Insecure_Randomness)
* [Password Plaintext Storage](https://owasp.org/www-community/vulnerabilities/Password_Plaintext_Storage)

***Preventions:*** [Protect Data Everywhere](https://owasp.org/www-project-proactive-controls/v3/en/c8-protect-data-everywhere)

***Cheatsheets:*** 
* [User Privacy Protection](https://cheatsheetseries.owasp.org/cheatsheets/User_Privacy_Protection_Cheat_Sheet.html)
* [Transport Layer Protection](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)
* [TLS Cipher String](https://cheatsheetseries.owasp.org/cheatsheets/TLS_Cipher_String_Cheat_Sheet.html)
* [HTTP Strict Transport Security - HSTS](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
* [Cryptographic](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html)
* [Password Storage](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
 
[*Go to top*](#Security)


## XML External Entities (XXE)

[XML External Entities (XXE)](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A4-XML_External_Entities_(XXE)) : 
Many older or poorly configured XML processors evaluate external entity references within XML 
documents. External entities can be used to disclose internal files using the file URI handler, 
internal file shares, internal port scanning, remote code execution, and denial of service attacks.

***Preventions:*** The safest way to prevent XXE is always to disable DTDs (External Entities) completely

***Cheatsheets:*** 
* [XML External Entity Prevention](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html)
* [XML Security](https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet.html)

[*Go to top*](#Security)


## Broken Access Control

[Broken Access Control](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A5-Broken_Access_Control) : 
Restrictions on what authenticated users are allowed to do are often not properly enforced. 
Attackers can exploit these flaws to access unauthorized functionality and/or data, such as access 
other users’ accounts, view sensitive files, modify other users’ data, change access rights, etc.

***Preventions***: [Enforce Access Controls](https://owasp.org/www-project-proactive-controls/v3/en/c7-enforce-access-controls)

***Cheatsheets:*** [Access Control](https://cheatsheetseries.owasp.org/cheatsheets/Access_Control_Cheat_Sheet.html)

[*Go to top*](#Security)


## Security Misconfiguration

[Security Misconfiguration](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A6-Security_Misconfiguration) 
is the most commonly seen issue. This is commonly a result of insecure default configurations, 
incomplete or ad hoc configurations, open cloud storage, misconfigured HTTP headers, and verbose 
error messages containing sensitive information. Not only must all operating systems, frameworks, 
libraries, and applications be securely configured, but they must be patched/upgraded in a 
timely fashion.

***Preventions:***
* [Leverage Security Frameworks and Libraries](https://owasp.org/www-project-proactive-controls/v3/en/c2-leverage-security-frameworks-libraries)
* Use [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/) 
  (see also [dependency-check-maven](https://jeremylong.github.io/DependencyCheck/dependency-check-maven/index.html)) 
  and [retire.js](https://retirejs.github.io/retire.js/) to detect libraries with vulnerabilities
* Remove or do not install unused features and frameworks
* Ensure debug mode is not enabled on production

[*Go to top*](#Security)


## Cross-Site Scripting XSS

[Cross-Site Scripting XSS](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A7-Cross-Site_Scripting_(XSS)) : 
XSS flaws occur whenever an application includes untrusted data in a new web page without proper 
validation or escaping, or updates an existing web page with user-supplied data using a browser 
API that can create HTML or JavaScript. XSS allows attackers to execute scripts in the victim’s 
browser which can hijack user sessions, deface web sites, or redirect the user to malicious sites.

***Preventions:*** 
* [Encode and Escape Data](https://owasp.org/www-project-proactive-controls/v3/en/c4-encode-escape-data)
* [Validate All Inputs](https://owasp.org/www-project-proactive-controls/v3/en/c5-validate-inputs)
* [Use Subresource Integrity (integrity attribute of `<script>`)](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity)
* [X-CSS-Protection HTTP Header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection)

***Cheatsheets:***
* [Cross Site Scripting Prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
* [DOM based XSS Prevention](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

[*Go to top*](#Security)


## Insecure Deserialization

[Insecure Deserialization](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization) 
often leads to remote code execution. Even if deserialization flaws do not result in remote 
code execution, they can be used to perform attacks, including replay attacks, injection attacks, 
and privilege escalation attacks.

***Preventions:*** Avoiding native (de)serialization formats; use data format like JSON or XML

***Cheatsheets:*** [Deserialization](https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html)

[*Go to top*](#Security)


## Using Components with Known Vulnerabilities

[Using Components with Known Vulnerabilities](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A9-Using_Components_with_Known_Vulnerabilities) : 
Components, such as libraries, frameworks, and other software modules, run with the same privileges 
as the application. If a vulnerable component is exploited, such an attack can facilitate serious 
data loss or server takeover. Applications and APIs using components with known vulnerabilities 
may undermine application defenses and enable various attacks and impacts.

***Other known risks:***
* [Using Components From Untrusted Source](https://cwe.mitre.org/data/definitions/829.html)

***Preventions:*** [Leverage Security Frameworks and Libraries](https://owasp.org/www-project-proactive-controls/v3/en/c2-leverage-security-frameworks-libraries)

[*Go to top*](#Security)


## Insufficient Logging & Monitoring

[Insufficient Logging & Monitoring](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A10-Insufficient_Logging%252526Monitoring), 
coupled with missing or ineffective integration with incident response, allows attackers to 
further attack systems, maintain persistence, pivot to more systems, and tamper, extract, or 
destroy data. Most breach studies show time to detect a breach is over 200 days, typically detected 
by external parties rather than internal processes or monitoring.

***Preventions:*** [Implement Security Logging and Monitoring](https://owasp.org/www-project-proactive-controls/v3/en/c9-security-logging)

***Cheatsheets:*** [Logging](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)

[*Go to top*](#Security)


## Top 10 Proactive Controls

* [Define Security Requirements](https://owasp.org/www-project-proactive-controls/v3/en/c1-security-requirements)
* [Leverage Security Frameworks and Libraries](https://owasp.org/www-project-proactive-controls/v3/en/c2-leverage-security-frameworks-libraries)
* [Secure Database Access](https://owasp.org/www-project-proactive-controls/v3/en/c3-secure-database)
* [Encode and Escape Data](https://owasp.org/www-project-proactive-controls/v3/en/c4-encode-escape-data)
* [Validate All Inputs](https://owasp.org/www-project-proactive-controls/v3/en/c5-validate-inputs)
* [Implement Digital Identity](https://owasp.org/www-project-proactive-controls/v3/en/c6-digital-identity)
* [Enforce Access Controls](https://owasp.org/www-project-proactive-controls/v3/en/c7-enforce-access-controls)
* [Protect Data Everywhere](https://owasp.org/www-project-proactive-controls/v3/en/c8-protect-data-everywhere)
* [Implement Security Logging and Monitoring](https://owasp.org/www-project-proactive-controls/v3/en/c9-security-logging)
* [Handle All Errors and Exceptions](https://owasp.org/www-project-proactive-controls/v3/en/c10-errors-exceptions)

[Cheatsheets related to Proactive Controls](https://cheatsheetseries.owasp.org/IndexProactiveControls.html)

*source: [OWASP Proactive Controls](https://owasp.org/www-project-proactive-controls/)*

[*Go to top*](#Security)


# Other Security Risks

Non exhausted list of other security risks (from various sources):
* [Unvalidated Redirects and Forwards](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html)
* [File Upload Threats](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html#file-upload-threats)
* [Denial of Service](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html), 
  see also [wikipedia](https://en.wikipedia.org/wiki/Denial-of-service_attack)
  * [Regular expression](https://owasp.org/www-community/attacks/Regular_expression_Denial_of_Service_-_ReDoS)
  * [Uncaught Exception](https://cwe.mitre.org/data/definitions/248.html)
  * [Failure to Release Resources](https://owasp.org/www-community/attacks/Denial_of_Service)
* [Lack of Resources & Rate Limiting (API)](https://github.com/OWASP/API-Security/blob/master/2019/en/src/0xa4-lack-of-resources-and-rate-limiting.md)
* [Forced browsing](https://owasp.org/www-community/attacks/Forced_browsing)
* [Insufficient anti-automation](https://cwe.mitre.org/data/definitions/799.html)
* [Insecure Direct Object Reference](https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html)
* [Server Side Request Forgery](https://owasp.org/www-community/attacks/Server_Side_Request_Forgery)
* [Mass Assignment](https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html)
* [Clickjacking](https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html)
* [Business logic](https://owasp.org/www-community/vulnerabilities/Business_logic_vulnerability)
* [Side-channel attacks](https://en.wikipedia.org/wiki/Side-channel_attack); e.g. [Timing attack](https://en.wikipedia.org/wiki/Timing_attack)
* [Improper Assets Management](https://github.com/OWASP/API-Security/blob/master/2019/en/src/0xa9-improper-assets-management.md)

[*Go to top*](#Security)


# MDN web docs

[MDN web docs](https://developer.mozilla.org/en-US/) is a great place to find resources about
web development.


## Web security
* [Web security of MDN web docs](https://developer.mozilla.org/en-US/docs/Web/Security)
  * [SOP - Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)
  * [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)

[*Go to top*](#Security)

  
## HTTP Headers
Important security HTTP Headers:
* [`X-XSS-Protection: 1; mode=block`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection): 
  enable in-browser XSS filter
* [`X-Content-Type-Options: nosniff`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options): 
  prevent [MIME sniffing](https://en.wikipedia.org/wiki/Content_sniffing)
* [Content-Security-Policy (CSP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy): 
  helps guard against [cross-site scripting attacks (XSS)](https://developer.mozilla.org/en-US/docs/Web/Security/Types_of_attacks#cross-site_scripting_xss).
  * [frame-ancestors 'none'](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors): 
    permit/forbid framing
* [`Content-Type: text/html; charset=UTF-8`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type): 
  to restrict data format that can interact with the resource
* [`X-Frame-Options: SAMEORIGIN`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options): 
  avoid [clickjacking](https://en.wikipedia.org/wiki/Clickjacking) attacks
* [`Server`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server): 
  set to a custom value or generic value
* [`X-Powered-By`](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields) 
  must be removed (detail about technology of the web application)
* [Access-Control-Allow-Origin (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)
* [Access-Control-Allow-Methods (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Methods)

[*Go to top*](#Security)


## Cookies
An [HTTP Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies) is a small piece of 
data that a server sends to the user's web browser. 
The browser may store it and send it back with the next request to the same server. Typically, 
it's used to tell if two requests came from the same browser — keeping a user logged-in, for 
example. It remembers stateful information for the stateless HTTP protocol.

Cookies are sent with every request, so they can worsen performance. Modern APIs for client storage 
are the [Web storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) and 
[IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API).

Important flags to secure Cookie when calling [`Set-Cookie`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie)
* [Secure](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie): 
  A secure cookie is only sent to the server when a request is made with the https: scheme.
* [HttpOnly](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie): 
  Forbids JavaScript from accessing the cookie.
* [Domain](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie): 
  Domain to which the cookie will be sent
* [Path](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie): 
  Pages to which the cookie will be sent
* [Expires](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie): 
  Maximum lifetime of the cookie (adviced: 0)

[*Go to top*](#Security)


## Web Storage

[Web Storage](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) and 
especially [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) 
are used to store persistent data on the client.

**Security rule**: avoid storing sensitive data in localStorage because data are available from JavaScript

[*Go to top*](#Security)
