**Summary**

The system is experiencing a Stored XSS vulnerability at the product view location where admin or any user with permission to edit product information can inject HTML code containing an XSS payload to display to the users.
**Details**

The attacker injects an XSS payload into the product description, when a customer or user accesses the shopping page and searches for the product that was recently edited, the XSS payload is successfully executed.
**PoC**

Log in with the admin account, go to the **Catalog**-**Product** section, and select any product.
In the **Description** section, select **Source** and inject the payload <script src=1 onerror=("XSS")> and click **Save**
![image](https://github.com/user-attachments/assets/2745b3b8-1d13-428c-b4b5-83980e3c7fa9)
 
Access the shopping page, find the product recently edited by the admin, and we see that the payload is successfully executed
 ![image](https://github.com/user-attachments/assets/c775ad3d-7903-4dd9-86d0-fc987b934a27)

**Impact**

Stored XSS allows attackers to inject and store malicious code on the server, leading to data theft, account takeover by steal cookie, malware distribution, and loss of business reputation. Prevent it by validating input, encoding output, using HTTPOnly cookies, and implementing CSP.
