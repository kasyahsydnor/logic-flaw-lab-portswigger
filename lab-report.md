#  PortSwigger Logic Flaw Lab - Excessive Trust in Client-Side Controls

## 📌 Overview
This repository documents my completion of the **PortSwigger Web Security Academy** lab on **logic flaws caused by excessive trust in client-side controls**. The lab demonstrates how applications relying on client-side validation can be exploited by modifying requests before they reach the server.

## 🔑 Key Takeaways
✅ Understanding how **client-side controls** can be manipulated.
✅ Using **Burp Suite** to intercept and modify requests.
✅ Exploiting **business logic flaws** to escalate privileges or bypass restrictions.
✅ Emphasizing **server-side validation** for security enforcement.

## Lab Walkthrough

### Step 1: Identifying the Weakness
The lab scenario presented a vulnerable web application where pricing enforcement occurred **only on the client side**. This allowed an attacker to alter the data before it was processed by the server.

###  Step 2: Intercepting the Request
1️⃣ Launched **Burp Suite** and enabled the **Intercept** feature.
2️⃣ Attempted to purchase a premium item, capturing the HTTP request.
3️⃣ Observed that the **price validation** was occurring only on the client side.

###  Step 3: Exploiting the Vulnerability
1️. Modified the `price` parameter in the intercepted request, changing the value from **100** to **1**.

2️. Forwarded the altered request to the server.

3️. Successfully purchased the item for **$1 instead of $100**, demonstrating the flaw.

📸 **Screenshot:** ![priceat1](https://github.com/user-attachments/assets/f06fbb74-f467-4a8b-875d-b2f1be4b1282)

###  Step 4: Prevention Strategies
To mitigate this vulnerability, web applications should:
-  Implement **server-side validation** for critical operations.
-  Avoid **trusting client-side inputs** for security decisions.
-  Use **cryptographic signing** to prevent data tampering.

##  Conclusion
This lab provided **hands-on experience** in identifying and exploiting **logic flaws** in web applications. It reinforced the importance of **server-side security controls** and the risks of excessive trust in client-side validation.

---
⚠️ **Ethical Disclaimer:** This documentation is for **educational purposes only**. Always conduct security testing with **proper authorization**.


