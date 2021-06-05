---
title: "How can I get other users DTH data includings mobile numbers, email address, address, ip address and many more"
date: 2021-06-05 T 12:26:30 +05:30
categories:
  - Penetration Testing
  - Findings
tags:
  - DTH data
  - penetration testing
  - cybersecurity
  - posts
---

DTH vulnerable app has a field to enter SMART CARD NUMBER to recharge without login into customer's account. This functionality lures me to do test on various customers data. 
## But How?!
I have started testing with OTP functionality on vulnerable web app. There is restriction on rate limiting to validate OTP. Then I decided to look each and every functionality. At first, I tried to see ```view page source```. This time I found that front end developers made some mistake by commenting other customers data.

![alt text](/assets/images/blogpostimages/commented.jpg "Commented Line in Image")

I have confirmed that there is vulnerabilities in this webapp. 

## Findings
I, found vulnerable endpoint is ```\ForgotPassword```. Here the developers made a big mistake by exposing customer's mobile number.
![alt text](/assets/images/blogpostimages/exposingmobilenumber.jpg "Exposing Mobile Number")

By using OSINT techniques, verified that mobile number is belongs to that person.
![alt text](/assets/images/blogpostimages/osintmobilenumber.jpg "OSINT Mobile Number")

From here I got his/her gmail address and got more information about that customer.
![alt text](/assets/images/blogpostimages/osintgmail.jpg "OSINT Gmail")

Again I came back to vulnerable endpoint to test it on other customers data. I tried to enumerate with other customers smart card numbers. 

![alt text](/assets/images/blogpostimages/enumerate.jpg "Customer Details")

These are the fields that vulnerable app has ```CUST_SMARTCARD, CUST_TYPE, CUST_FNAME, CUST_ADDRESS,CUST_CITY,CUST_STATE,CUST_ZIP,CUST_MAIL,CUST_RMN(Mobile Numbers), CUST_EXP, CUST_BAL, CUST_PLAN, CUST_PLAN_AMOUNT, CUST_PLAN_MONTH, SMC,Package_ID,Package_Name ```

![alt text](/assets/images/blogpostimages/customerdetails.jpg "Customer Details")

I have reported this vulnerability ethically to that concerned department more than 4 months ago. I didn't get any reply from them, seems like they didn't care about customer's privacy data about to breach.
