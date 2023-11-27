---
title: "5 Security Keys"
date: 2023-11-27T11:12:48+02:00
featured_image: ../assets/images/featured/2023-11-27-5-Essential-Security-Keys/5keys.png
draft: false
summary: 5 Essential Security Keys for Mobile Applications.
description: After a few years analyzing mobile applications, I present what I believe are the 5 most important keys.
author: Jordi Ventayol
authorimage: ../assets/images/global/cube_icon_background.png
categories: Blog
tags: [Android, iOS, Obfuscation] 
---

During the past years, I have been involved in evaluated a huge number of Mobile applications to analyze their security. The followed strategy has allowed me to position me from the point of view of an attacker and from the point of view of a defender, gaining experience both as attacker and defender. The result has been a little knowledge on how protect mobile applications against the most innovative attacks in the field. From all this experience acquired, below I comment the most important aspects for a mobile application in terms of security.

In this article, we will discuss five essential security keys that every mobile application should have in mind to protect user and application data. From obfuscation to code quality, these keys are crucial for ensuring the security and integrity of your mobile application.

Here are the 5 keywords that developers should keep in mind if they want to protect their mobile applications successfully:

### Obfuscation

{{<figure src="/posts/img/2023-11-25-5-Essential-Security-Keys/Obfuscation.png" class="centered-image" caption="Fig.1: Code Obfuscation">}}

This concept is the first barrier that an attacker should defeat is they want to compromise a Mobile application though reverse engineering. With obfuscation, the data used by the application is harder to extract, even the code and the execution flow are harder to understand. A good obfuscation means more time will needed by the attacker to know how the mobile application works. The attackers always try to apply reverse engineering to the applications to understand the most sensitive parts of it, identify and bypass the security measures if there are present. 
Best strategy is combine data and flow obfuscation. Data obfuscation consist of substitute cleartext values such as strings or numbers for expressions, then they are resolved at runtime. That way, the computation of the expression is necessary to reveal the value. With flow obfuscation the application tries to hide their code converting simple instruction structures in complex graphs instructions. The goal is that an attacker cannot guess which block is executed after another one. 

### Secure Storage

{{<figure src="/posts/img/2023-11-25-5-Essential-Security-Keys/secure_sto.png" class="centered-image" caption="Fig.2: Secure Storage">}}

Most, if not all, applications must persistently store data on the device for future use or to work properly. It is vitally important to protect this data by encryption and never store it in plaintext, since an attacker/malware with internal access to the device (rooted/jailbreak) could obtain this data and use it for fraudulent purposes. The most important part for secure storage is how the keys that protect these data are generated and used. Nowadays, most of devices implements hardware secure modules to securely generate the keys to cipher these data, making non-exportable and secret to the application and operative system layer.

### Cryptography

{{<figure src="/posts/img/2023-11-25-5-Essential-Security-Keys/crypto.png" class="centered-image" caption="Fig.3: Cryptography">}}

Cryptography is closely related to the previous point. Using safe and recommended algorithms to encrypt data is vital for data confidentiality. Developers should avoid using outdated algorithms or keys shorter than recommended length. Computers power quickly grows every day, so cryptographic algorithms that were safe a few years ago are now no longer recommended for use. Therefore, it is important to keep up to date with what is new in the field and have a basic knowledge of cryptography.

### Communication

{{<figure src="/posts/img/2023-11-25-5-Essential-Security-Keys/comm.png" class="centered-image" caption="Fig.4: Communication">}}

Today, almost all applications communicate and connect with an external server. The data send through the network is susceptible to being intercepted by an attacker, so authenticating both the client and the server is almost mandatory when sensitive data is exchanged. In addition, it is a good practice to encrypt the data (payload) with a second encryption layer apart from that offered by algorithms such as TLS. That ensures that only the two allowed parties are capable of decrypt and process the exchanged data.

### Code quality

{{<figure src="/posts/img/2023-11-25-5-Essential-Security-Keys/code_q.png" class="centered-image" caption="Fig.5: Code Quality">}}

Finally, like an architect who correctly uses materials to build a piece of art, remove unused or irrelevant code and debugging data to reduce the attack surface becomes important. Debugging code facilitates the comprehension of the application to an external attacker. It is true that most of the application on the market do not incorporate debugging code in their releases, but not all of them remove this code in a correct way. Bad practices in code quality as remove debugging code could allow an attacker to reactivate this functionality in the release versions. Besides, ensure that your application use the latest version of the external libraries and 3rd party components comes today crucial. Use a 3rd party library or external library that do not receive regularly updates exposes your application to be exploited by public vulnerabilities.

Concluding, it is important to note that the strength of these keywords does not reside only in their idea, but in how they are implemented, since it is the key to making your solution as secure as possible.
Implementing these mentioned keys from scratch can be tedious and with high cost, but implement solutions as TAK client (Security SDK from Build38 where I am working now) can cover most of these topics and take care of your application security.