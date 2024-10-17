Affected Web App: CodeAstro Membership Management System in PHP

Version: v1.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /edit_type.php <br>
membershipType parameter inside edit_type.php is vulnerable to stored Cross-Site Scripting

Impact: Cross-Site Scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked or even malware getting installed on the host machine.

Image: 

<img width="909" alt="codeastro_vul2_pic1" src="https://github.com/user-attachments/assets/b9f48b3b-5f3c-44e0-bdba-ff436b8857bb">


Proof of Concept: To reproduce this attack, an attacker can inject a script like *<script>alert(1)</script>* into the Membership Type field while editing the types of the memberships (as shown in the figure above) under the Membership Types tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the membership types are being viewed in view_type.php

Image:

<img width="907" alt="codeastro_vul2_pic2" src="https://github.com/user-attachments/assets/9d7ba3ab-d85c-486f-818d-2c1ae6d761ab">




Remediation: It is important to update CodeAstro Membership Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one showed in the example cannot be injected. 
