#  PortSwigger Logic Flaw Lab - Excessive Trust in Client-Side Controls

##  Overview
This repository documents my completion of the **PortSwigger Web Security Academy** lab on **logic flaws caused by excessive trust in client-side controls**. The lab demonstrates how applications relying on client-side validation can be exploited by modifying requests before they reach the server.

## 🔑 Key Takeaways
- Understanding how **client-side controls** can be manipulated.

- Using **Burp Suite** to intercept and modify requests.

- Exploiting **business logic flaws** to escalate privileges or bypass restrictions.

- Emphasizing **server-side validation** for security enforcement.

## Lab Walkthrough

## Step 1: Logging In  
I logged in using a **fake account** as instructed.  

![Screenshot_2025-02-27_10-28-19](https://github.com/user-attachments/assets/fccd5ebe-79a0-43eb-9dad-591f667f68ef)

## Step 2: Navigating to the Product Page  
I accessed the **product page** and selected the **Lightweight "l33t" Leather Jacket** to view its details.  
Using **Burp Suite**, I went to **Proxy > Intercept** and enabled interception.  
I then added the jacket to my cart, triggering a **POST /cart** request, which Burp Suite successfully intercepted.  

 ![Screenshot_2025-02-27_16-45-12](https://github.com/user-attachments/assets/a5303e2d-59c3-49cb-8ab5-6e19495012c8)

## Step 3: Analyzing the Intercepted Request  
The captured request contained the **item details**, including the **price parameter** at the bottom.  

![price 133700](https://github.com/user-attachments/assets/928267f7-4d3c-429d-a740-dc32797dbf03)

## Step 4: Modifying the Request  
I **changed the price parameter** from `1337` to `1` and (from the original price to my desired price) clicked **Forward** to send the modified request to the server.  

![price 133700](https://github.com/user-attachments/assets/d1fa74c2-7dab-4362-9495-fe811e6394e6)


## Step 5: Exploiting the Vulnerability  
The modification successfully changed the item's price to **1 cent**, allowing me to complete the checkout process and exploit the vulnerability in the fake website.  

![priceat1](https://github.com/user-attachments/assets/af03cf0a-7792-44e5-90c9-634a830a6a2e)

![congrats](https://github.com/user-attachments/assets/2ec144db-596a-4415-9bf4-169509d12bb2)

## Conclusion  
This confirmed that the application relied **only on client-side validation**, making it vulnerable to manipulation. To mitigate this issue, web applications should enforce **server-side validation** to prevent unauthorized modifications.  


###  Step 4: Prevention Strategies
To mitigate this vulnerability, web applications should:
-  Implement **server-side validation**
-  Avoid **trusting client-side inputs** for security decisions.
-  Use **cryptographic signing** to prevent data tampering.

---
 **Ethical Disclaimer:** This documentation is for **educational purposes only**. Always conduct security testing with **proper authorization**.


