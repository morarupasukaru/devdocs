# Security

The [Open Web Application Security Project (OWASP)](https://owasp.org/) is a nonprofit foundation
  that works to improve the security of software

* [Top 10 Web Application Security Risks - 2021](https://owasp.org/www-project-top-ten/)
  * [Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/)
  * [Cryptographic Failures](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/)
  * [Injection](https://owasp.org/Top10/A03_2021-Injection/)
  * [Insecure Design](https://owasp.org/Top10/A04_2021-Insecure_Design/)
  * [Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
  * [Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
  * [Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)
  * [Software and Data Integrity Failures](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)
  * [Security Logging and Monitoring Failures](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/)
  * [Server-Side Request Forgery (SSRF)](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/)
* [Top 10 Proactive Controls - 2018](https://cheatsheetseries.owasp.org/IndexProactiveControls.html)
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
* [Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
* [Other Security Risks](#Other-Security-Risks)
* [MDN web docs](#MDN-web-docs)
  * [Web security](#Web-security)
  * [HTTP Headers](#HTTP-Headers)
  * [Cookies](#Cookies)
  * [Web Storage](#Web-Storage)
* Other resources: 
  * [Top 10000 worst passwords](https://github.com/danielmiessler/SecLists/blob/master/Passwords/darkweb2017-top10000.txt) 
  from [SecLists](https://github.com/danielmiessler/SecLists) GitHub project
  * [auth0](https://auth0.com/) provide open-source libs to implements JWT [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token) and an authentification provider
    * [jwks](https://auth0.com/docs/secure/tokens/json-web-tokens/json-web-key-sets) aka JSON Web Key Sets is set of keys containing the public keys used to verify any JSON Web Token (JWT) issued by the authorization server
    * see also [Anatomy of a JWT](https://fusionauth.io/learn/expert-advice/tokens/jwt-components-explained)
  * [RBAC](https://en.wikipedia.org/wiki/Role-based_access_control) Role-based access control is normally sufficient authorization for most applications
  * [Secure Core Warrior](https://securecodewarrior.com/): great eLearning Security Platform
* Tools / Library
  * [node-argon2](https://github.com/ranisalt/node-argon2) password hash library
  * [password-validator](https://github.com/tarunbatra/password-validator) library
  
*(Page mainly written in April 2020; links checked on 13.03.2023)*

[*Go to parent page*](../README.md)


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
