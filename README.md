Affected Web App: CodeAstro Membership Management System in PHP

Version: v1.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /add_members.php, /edit_member.php

fullname parameter and address parameter within each of these files is vulnerable to stored Cross-Site Scripting

Impact: Cross-Site Scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked or even malware getting installed on the host machine.

Image: 
<img width="960" alt="codeastro_vul1" src="https://github.com/user-attachments/assets/e156ca1f-7793-473b-ae32-426fefb8d280">

<img width="960" alt="codeastro_vul2" src="https://github.com/user-attachments/assets/c1bd3fdd-20f6-4288-a176-261fefa6b451">

Proof of Concept: To reproduce this attack, an attacker can inject a script into the Full Name field or Address field either while adding new members or editing new members (as shown in the two figures above) under the Add Members tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the members are being viewed in mange_members.php

Image:
<img width="960" alt="proof_code_astro" src="https://github.com/user-attachments/assets/9ede88cc-226d-4233-b0d1-1283ddf308b9">

<img width="960" alt="proof2_code_astro" src="https://github.com/user-attachments/assets/0a241812-66c9-4b2f-a820-35cdb0b7c494">

Remediation: It is important to update CodeAstro Membership Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one showed in the example cannot be injected. 
