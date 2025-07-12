## 🚀 Steps to Solve the Lab (Simple English)

1. **Log in as attacker**
   - Username: `wiener`
   - Password: `peter`

2. **Go to the Change Password page**
   - URL: `/my-account`
   - You will see a form to change your password

3. **Send a request to change carlos's password**
   - Intercept or copy this POST request:
     ```
     POST /my-account/change-password
     Content-Type: application/x-www-form-urlencoded

     username=carlos
     current-password=<your-guess>
     new-password=123456
     confirm-password=123456
     ```

4. **Use Burp Suite Intruder to brute-force the current password**
   - Set payload position at `current-password`
   - Use a short wordlist of common passwords
   - Observe the responses:
     - If the response includes: `Incorrect current password` → wrong guess
     - If there's no error → password is correct

5. **After finding the correct password**
   - The server accepts the request and changes carlos's password to `123456`

6. **Log out and log in as carlos**
   - Username: `carlos`
   - Password: `123456`
   - ✅ Lab solved
