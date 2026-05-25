## Lab: Phishing Simulation
**Course:** CompTIA Security+

### Objective
The goal of this lab was to simulate a real-world phishing attack to understand the technical mechanics of credential harvesting and identify common indicators of compromise (IoCs) from both the attacker and victim perspectives.

### Tools Used
* **Kali Linux:** Used as the primary attacker workstation within the virtual lab environment.
* **Social-Engineer Toolkit (SET):** An open-source penetration testing framework designed for social engineering.
* **Apache Web Server:** Hosted the cloned "decoy" login page to capture user credentials.
* **SMTP Mail Server:** Used to relay the phishing email to the target victim.
* **Meterpreter:** Used to connect to and gain control of the victim's machine.

### Steps Completed

#### 1. Attack Vector Selection
Configured the **Social-Engineer Toolkit (SET)** to perform a "Website Attack Vector" using the "Credential Harvester" method.

#### 2. Crafting the Decoy
Cloned a standard login page (e.g., a corporate webmail or portal). SET automatically configured the local Apache server to mirror this page while intercepting any data entered into the username and password fields.

#### 3. Social Engineering Strategy
Drafted a deceptive email using "Urgency" and "Authority" as social engineering principles. The email masqueraded as a password expiration notice, prompting the user to click the link to avoid account lockout.

#### 4. Delivery & Execution
Sent the phishing email to the target Windows VM. Once the victim clicked the link, they were redirected to the cloned site hosted on the attacker's IP address.

#### 5. Data Capture & Analysis
Monitored the Kali terminal in real-time. Initiated data theft tools such as mic recording, idle time tracker, and keycanning as an attacker would to collect sensitive information such as login credentials or PII from the unknowing victim. 

![Attacker Creates Payload](SecurityPlus/Phishing-Simulation/payload_creation.png)
![Attacker creates email with the link to zipped payload](SecurityPlus/Phishing-Simulation/email_contents.png)
![Victim Receives Email](SecurityPlus/Phishing-Simulation/email.png)
![Victim Downloads Payload](SecurityPlus/Phishing-Simulation/payload_download.png)
![Attacker utilizes Meterpreter to monitor victim's activity](SecurityPlus/Phishing-Simulation/attacker_activity.png)

 
After the initial compromise, I utilized a Meterpreter shell to exercise post-exploitation capabilities. I successfully executed a keyscan to capture live keystrokes, initiated microphone recording, and monitored system idle time to assess user activity. This highlighted the severe privacy and security risks associated with successful social engineering attacks.
=======

>>>>>>> 548b62df41a456cf52b20009b5fbf2be728b7709
