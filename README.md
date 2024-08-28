Affected Web App: CodeAstro Membership Management System in PHP

Version: v1.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /add_members.php, /edit_member.php <br>
fullname parameter and address parameter within each of these files is vulnerable to stored Cross-Site Scripting

Impact: Cross-Site Scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked or even malware getting installed on the host machine.

Image: 

<img width="909" alt="codeastro_vul1" src="https://github.com/user-attachments/assets/8bb333ce-056b-409c-8ede-dec39c9c3400">

<br>
<img width="910" alt="codeastro_vul2" src="https://github.com/user-attachments/assets/a1c5190e-ae7f-4524-9864-b546e95e2958">


Proof of Concept: To reproduce this attack, an attacker can inject a script into the Full Name field or Address field either while adding new members or editing new members (as shown in the two figures above) under the Add Members tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the members are being viewed in mange_members.php

Image:

<img width="910" alt="proof_code_astro" src="https://github.com/user-attachments/assets/01442748-64e4-407c-b0cc-aecfb852f508">
<br>

<img width="909" alt="proof2_code_astro" src="https://github.com/user-attachments/assets/429112c3-0862-4dc9-bb64-ace36cbf7f7d">

Remediation: It is important to update CodeAstro Membership Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one showed in the example cannot be injected. 
