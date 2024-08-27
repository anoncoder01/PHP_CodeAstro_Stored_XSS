Affected Web App: CodeAstro Membership Management System in PHP

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /add_members.php, /edit_members.php

Impact: Cross-Site Scripting (XSS) vulnerability is a serious web security threat, allowing attackers to inject malicious scripts with diverse impacts. Users face data theft, session hijacking, and unwittingly performing unauthorized actions.

Proof of Concept: To reproduce this attack, an attacker can inject a script into the fullname field while adding new members. The payload '<script>alert("xss")</script>' was successfully accepted, leading to an alert being triggered for the user

Image

Remediation: It is important to update Dairy Farm Shop Management System by properly sanitizing code variables and including restricting for special characters so that malicious input such as the one showed in the example cannot be injected. 
