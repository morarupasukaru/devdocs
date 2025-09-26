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
* Non exhausted list of other security risks
  * [Cross Site Request Forgery (CSRF)](https://owasp.org/www-community/attacks/csrf)
    is an attack that forces an end user to execute unwanted actions on a web application in which they’re currently authenticated
  * [Unvalidated Redirects and Forwards](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html)
  * [File Upload Threats](https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html#file-upload-threats)
  * [Denial of Service](https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet.html),
    see also [wikipedia](https://en.wikipedia.org/wiki/Denial-of-service_attack)
    * [Regular expression](https://owasp.org/www-community/attacks/Regular_expression_Denial_of_Service_-_ReDoS)
    * [Uncaught Exception](https://cwe.mitre.org/data/definitions/248.html)
    * [Failure to Release Resources](https://owasp.org/www-community/attacks/Denial_of_Service)
  * [Lack of Resources & Rate Limiting (API)](https://owasp.org/API-Security/editions/2019/en/0xa4-lack-of-resources-and-rate-limiting/)
  * [Forced browsing](https://owasp.org/www-community/attacks/Forced_browsing)
  * [Insufficient anti-automation](https://cwe.mitre.org/data/definitions/799.html)
  * [Insecure Direct Object Reference](https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html)
  * [Server Side Request Forgery](https://owasp.org/www-community/attacks/Server_Side_Request_Forgery)
  * [Mass Assignment](https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html)
  * [Clickjacking](https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html)
  * [Business logic](https://owasp.org/www-community/vulnerabilities/Business_logic_vulnerability)
  * [Side-channel attacks](https://en.wikipedia.org/wiki/Side-channel_attack); e.g. [Timing attack](https://en.wikipedia.org/wiki/Timing_attack)
  * [Improper Assets Management](https://github.com/OWASP/API-Security/blob/master/2019/en/src/0xa9-improper-assets-management.md)
* Documentations
  * [Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
  * [Web security of MDN web docs](https://developer.mozilla.org/en-US/docs/Web/Security)
    * [SOP - Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)
    * [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
  * [Top 10000 worst passwords](https://github.com/danielmiessler/SecLists/blob/master/Passwords/darkweb2017-top10000.txt) 
  from [SecLists](https://github.com/danielmiessler/SecLists) GitHub project
  * [auth0](https://auth0.com/) provide open-source libs to implements JWT [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token) and an authentification provider
    * [jwks](https://auth0.com/docs/secure/tokens/json-web-tokens/json-web-key-sets) aka JSON Web Key Sets is set of keys containing the public keys used to verify any JSON Web Token (JWT) issued by the authorization server
    * see also [Anatomy of a JWT](https://fusionauth.io/learn/expert-advice/tokens/jwt-components-explained)
  * [OAuth 2.0](https://oauth.net/2/) protocol for authorization
  * [RBAC](https://en.wikipedia.org/wiki/Role-based_access_control) Role-based access control is normally sufficient authorization for most applications
  * [symmetric vs asymmetric encryption](https://www.geeksforgeeks.org/difference-between-symmetric-and-asymmetric-key-encryption/)
  * [Secure Core Warrior](https://securecodewarrior.com/): great eLearning Security Platform
* Tools / Library
  * [node-argon2](https://github.com/ranisalt/node-argon2) password hash library
  * [password-validator](https://github.com/tarunbatra/password-validator) library

[*Go to parent page*](README.md)

*(Page mainly written in April 2020; links checked on 19.02.2024)*
