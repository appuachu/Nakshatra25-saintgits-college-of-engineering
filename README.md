# 🔒 Security Vulnerability Report: nakshatrasgce.in

# 🚀 Overview

## This repository documents a security vulnerability discovered in nakshatrasgce.in. The flaw allows unauthorized access to Admin Panel,sensitive student information and manipulation of the registration fee, leading to potential financial loss and data breaches.

# 🛠️ Vulnerability Details

# 1️⃣ Information Exposure
```bash
The system exposes student data including:

Name

Phone Number

College

Branch

Semester

This information can be accessed without authentication, violating data privacy regulations.
```

# 2️⃣ Payment Manipulation
```bash
The payment gateway (Razorpay) allows manual modification of the transaction request.

The amount parameter is Base64-encoded, allowing easy decoding and modification.

A user can register by reducing the registration amount (e.g., ₹1000 → ₹10) and successfully completing the process.
```

# ⚠️ Impact
```
Financial Loss: Users can register at a significantly lower cost than intended.

Data Breach: Unauthorized access to student data.

Legal & Compliance Issues: Violates data protection laws (e.g., GDPR, IT Act 2000 in India).
```

# 🔍 Steps to Reproduce (Ethical Testing)
```bash
1 Capture the network request during registration.

2 Identify the Base64-encoded payment data.

3 Decode the Base64 string to reveal transaction details.

4 Modify the amount field (e.g., 1000 → 10).

5 Re-encode the data in Base64 and replace it in the request.

6 Submit the request to the payment gateway.

7 Registration completes successfully with the altered amount.
```

# 🔧 Recommendations for Fixing
```bash
Encrypt Payment Data Securely: Use AES encryption instead of Base64 encoding.

Implement Server-side Validation: Cross-check payment details before processing registration.

Secure API Endpoints: Restrict access to student information and enforce authentication.

Enable Web Application Firewall (WAF): Detect and prevent data manipulation attacks.
```
## 📂 Registered Students Information

The extracted **registered students' data** can be found in the CSV file below:

📄 [Download students_info.csv](https://github.com/appuachu/Nakshatra25-saintgits-college-of-engineering-Bug-report/blob/main/masked_nakshathra_registration.csv)


## 🖼️ Admin Page Screenshots

### 📌 Admin Dashboard 
![Admin Page 1](https://github.com/appuachu/Nakshatra25-saintgits-college-of-engineering-Bug-report/blob/main/admin1.jpg)

### 📌 College Registered List Page
![Admin Page 2](https://github.com/appuachu/Nakshatra25-saintgits-college-of-engineering-Bug-report/blob/main/admin2.jpg)
