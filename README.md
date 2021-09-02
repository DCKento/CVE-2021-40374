# CVE-2021-40374 - Stored Cross-site Scripting in OpenEyes 3.5.1

## Description

A stored cross-site scripting (XSS) vulnerability was identified in OpenEyes 3.5.1, developed by the Apperta Foundation.

Improper input handling in the 'Address1' parameter allowed for JavaScript to be injected into a patients profile. When the patient profile was loaded by the web browser, the JavaScript executed. This could be used to perform XSS attacks on unsuspecting users who view the patient profile.

## Reproduction

1. Browse to a patient profile.
2. Click the 'edit icon' near the top of the screen.
3. In the Address1 field, input the following JavaScript: `<IMG SRC=# onerror="alert('xxs')">`
4. Click 'Save patient'.
5. Reload the patient profile.
6. Note that an alert box is triggered by the browser with the message 'xss'.

## Impact

If an attacker were to embed malicious JavaScript into the OpenEyes application, it could be used to hijack user accounts, steal credentials, exfiltrate sensitive data or perform malicious actions on the OpenEyes application.  

## Demonstration

https://user-images.githubusercontent.com/20635370/131623517-818ac6f8-61bf-4221-8dd8-11fc7171acef.mp4
