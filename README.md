# Browser Extension Security Project

## Introduction & Problem To Address:
Browsers have recently been exposed for storing passwords and other sensitive information in clear text within memory.

Chromium based browsers (including Google Chrome), as well as Microsoft Edge, Brave Browser and Mozilla Firefox have been identified as being affected by this issue.

A malicious actor does not need physical access to a machine to extract data, as remote access to software that is running on a machine is sufficient to perform an attack. In this attack, an attacker can extract data from any non-elevated process that runs on the same machine.

Whilst data must first be saved by a user for this vulnerability to be present, this vulnerability is not broadcast to users, so users may enter data without understanding the potential ramifications of such actions.

It is worth noting that many social engineering based attacks, such as fake "Windows Support" and other fraud use RDP (Remote Desktop) to connect to a victim machine. In this case, it is possible for a malicious actor to extract session cookies and perform session hijacking attacks. This attack vector can bypass other security features such as 2FA and gain unrestricted access to a victims bank, or other service.

So far the credentials that have been extracted from memory:

- Username & Password (When signing into a web application)
- URL, Username & Password (Auto loaded into memory during browser startup)
- All URLs, Usernames & Password records stored in Login Data
- All cookies for specific web applications, this includes session cookies.

### How Can This Problem Be Solved? 
Providing a browser extension that will communicate with a 3rd party database and retrieve credentials. These credentials will be stored using encryption.

This means no data will be saved in the browser, therefore bypassing any data being stored in memory.

### Similar Services
PING Identity and other services already exist, however, these services function as a backend service and do not directly interact with a browser as such. For example, PING ID will popup on a mobile device when attempting to login to a service online. If a user doesn't have their phone present, they will be incapable of logging into the service.

Such hinderance usually has a negative impact on user experience and can end up introducing more human related vulnerabilities that can be exploited. 

## Psychology
Generally, the more secure we try to make applications, the more we lower user experience. Enforcing "strong" passwords with a defined minimum length, uppercase & lowercase letters, at least one digit and at least one special character is already a bridge too far for some users.

This project aims to minimize the impact on an end user and provide a solution to password generation and storage.