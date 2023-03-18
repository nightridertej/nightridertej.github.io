---
title: "How I hacked AP Government Medical Data in 2020?"
date: 2023-03-18 T 15:38:30 +05:30
categories:
  - Penetration Testing
  - Findings
  - Account Takeover
tags:
  - penetration testing
  - cybersecurity
  - posts
---
During the pandemic, the government of Andhra Pradesh launched a medical website that tracks information on drugs, diagnoses, symptoms, and other related data.
## Avoid TEST Users/CREDS in Production Sites
During my reconnaissance phase, I discovered that there is a "TEST" user account present in the production environment. What's even more concerning is that the "TEST" user has been granted ADMIN access, which is a major security oversight.
 
WooooooooW REALLY?! 
![alt text](https://media.giphy.com/media/lXu72d4iKwqek/giphy.gif)

Another flaw I discovered is that the "UPDATE PASSWORD" hyperlink does not require the user to enter their old password to change it to a new one. This is a major security flaw as it allows anyone to change the password of an account without the user's knowledge or consent. For example, if a user has a name that is easily guessable, anyone could change their password without the user even knowing.

## Impact of the Vulnerability
The impact of this vulnerability could be severe, as it could allow an attacker to manipulate the medicine inventory data by changing its status to "INACTIVE", which could potentially cause harm to patients who rely on those medications. This could have serious consequences on their health and well-being.

## Evidence 
![alt text](/assets/images/blogpostimages/6.png "Login Page")

![alt text](/assets/images/blogpostimages/7.png "Screenshot")

![alt text](/assets/images/blogpostimages/8.JPG "Screenshot")

![alt text](/assets/images/blogpostimages/9.jpg "Telemedicine Inventory Data")

![alt text](/assets/images/blogpostimages/10.jpg "Screenshot")

## Recommendations for Mitigation:
When it comes to production environments, there are certain rules you should never break. One of the most basic rules is to never ever leave your TEST credentials exposed in any way. This could open the door to all kinds of security breaches. Additionally, it's important to implement user authentication with MFA to add an extra layer of protection. Finally, make sure you're following the principle of least privilege as much as possible, to minimize the potential damage that can be caused by any security breaches.


NOTE: I have reported this vulnerability ethically to CERT-IN 2 years ago and concerned team fixed this vulnerability.