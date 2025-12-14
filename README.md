
<img width="909" height="819" alt="Screenshot 2025-12-14 112557" src="https://github.com/user-attachments/assets/7a1fd7e4-8daf-48e4-a0cb-87ee9d21ada9" />

## Team Name: KeyGuardians

Team Members: Kevin Pasato, Jonathan Tyner, Matthew Chu, Alae Laaziri, Naser Shabbir

### PROJECT OVERVIEW: SecureDove

- SecureDove is a messaging app that is focused on confidentiality and communication
integrity. The app allows users to create accounts, send/receive messages, and share
encrypted files.


Functional Requirements:
1. User Account Management
2. Message Sending and Receiving
4. File Sharing
6. Message History and Backup
8. Session Management


Security Focused Development:
1. User Authentication and Key Management
3. Integrity via Message Authentication
10. Denial of Service (DoS) Attack Prevention



<img width="958" height="623" alt="Screenshot 2025-12-14 112734" src="https://github.com/user-attachments/assets/cccf926e-07ba-4cf5-be05-c9d1639f3d90" />

### DEMONSTRATION - Account Login
To use the website, you will need an account

● If you have an account, enter the email/username and password

● If you do not have an account, you can create one using the “click here” link.


<img width="961" height="680" alt="Screenshot 2025-12-14 112742" src="https://github.com/user-attachments/assets/51e75e9f-0e7f-4807-b7a4-086d1cee6f35" />

### DEMONSTRATION - Website Outline
Sidebar Includes:
● Account Management Page

● Message Page

● Logout Button

Account Management Page:
- The user can view their username, email, and User ID. They can also change their email and passwords.

Message Page:

- The user can add a friend by inputting a username and clicking send



<img width="775" height="601" alt="Screenshot 2025-12-14 112747" src="https://github.com/user-attachments/assets/0232410f-a2cb-4505-b78c-a9d915cea4e8" />

### Demonstration - Message Sending
- Select a friend from the friends list and type your message to send it.

- Encrypted and decrypted messages which ensures that the each message received is sent from the server.




<img width="293" height="140" alt="Screenshot 2025-12-14 112756" src="https://github.com/user-attachments/assets/9f3e6a9c-37eb-4a44-b6f8-dcc7096e0f2f" />


<img width="511" height="200" alt="Screenshot 2025-12-14 112759" src="https://github.com/user-attachments/assets/c7678a4c-b77c-4514-9d8b-e2f283cceb0c" />


### SECURITY RISKS - Break It

● The authentication cookies did not “Secure” attributes to “true”. Setting them to “true” would ensure that they were only passed through https connections.

● The database port “27017:27107” was left exposed. This allows unauthenticated remote access to sensitive data unless properly restricted.


### SECURITY RISKS - Fix It
After reviewing the security risk findings, we made two changes:

● We closed the open MongoDB port - We removed the port line in docker-compose.yml, so the database no longer exposes 27017 to potential attackers. This blocks unauthenticated connections.

● Secured cookie authentication - We updated the set_cookie call in app.py to include a secure flag. This ensures that cookies are transmitted only over https and reduces the risk of token leakage.


### Lessons Learned
- This project taught us several crucial lessons about security. First, security must be considered at every layer of the application stack.
  Our focus on secure message transmission didn't prevent us from making configuration errors at the deployment level.

- We learned the value of independent security testing. Having another team review our application uncovered vulnerabilities we had
  overlooked, highlighting the importance of fresh perspectives in security auditing


  
