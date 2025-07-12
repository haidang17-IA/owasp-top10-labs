## 🚀 Steps to Exploit the Lab (Simple English)

1. **Log in as a normal user**
   - Username: `wiener`
   - Password: `peter`

2. **Go to the Forgot Password page**
   - URL: `/forgot-password`
   - Enter: `wiener`
   - Submit the form

3. **Open the Email Client**
   - Click the "Email client" button
   - Find the reset link with token like:
     ```
     /forgot-password?temp-forgot-password-token=XYZ
     ```

4. **Submit a password reset**
   - Click the link to open the reset form
   - Set a new password
   - Intercept or send the request to **Burp Repeater**

5. **Remove the token**
   - In Burp Repeater:
     - Remove the `temp-forgot-password-token` from the URL and body
     - Keep only `username` and `new-password`
   - Send the request → it still works

6. **Change the target username**
   - Change:
     ```
     username=wiener → username=carlos
     ```
   - Set a new password for `carlos`
   - Send the request

7. **Log in as carlos**
   - Username: `carlos`
   - Password: the new one you set
   - ✅ Login success → Lab Solved!
