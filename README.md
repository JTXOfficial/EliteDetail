# Car Detailing Template: Edit, Host with Netlify, & Use EmailJS

This guide will help you:
- Download the project from GitHub
- Edit your project files
- Host your site on Netlify
- Add a custom domain
- Integrate EmailJS for email functionality

---

## 0. Download the Project from GitHub

1. Go to the GitHub repository: https://github.com/JTXOfficial/EliteDetail
2. Click the green **Code** button.
3. Choose **Download ZIP** to download the project files to your computer.
4. Unzip the downloaded file to a folder of your choice.

Alternatively, if you have Git installed, you can clone the repository:
```bash
git clone https://github.com/JTXOfficial/EliteDetail.git
```

---

## 1. Editing Your Project Files
- Open your project folder (e.g., `EliteDetail`).
- Use a code editor like VS Code, Sublime Text, or Notepad++.
- Edit files such as `index.html`, `styles.css`, and `script.js` as needed.
- Save your changes after editing.

---

## 2. Hosting Your Site on Netlify

### Step 1: Create a Netlify Account
- Go to [Netlify](https://www.netlify.com/) and sign up (free plan is enough).

### Step 2: Prepare Your Project
- Make sure your project folder contains at least an `index.html` file.
- Ensure all assets (CSS, JS, images) are in the folder.

### Step 3: Deploy to Netlify
**Option A: Drag & Drop**
1. Zip your project folder or select the folder directly.
2. Go to the Netlify dashboard, click 'Add new site' > 'Deploy manually'.
3. Drag and drop your folder (or zip file) into the upload area.
4. Netlify will build and give you a live URL.

---

## 2.5. Getting a Custom Domain for Your Netlify Site

### Step 1: Buy a Domain
- Purchase a domain from a registrar (e.g., Namecheap, Google Domains, GoDaddy).

### Step 2: Add Your Domain to Netlify
- In your Netlify dashboard, select your site.
- Go to “Domain management” > “Add custom domain”.
- Enter your purchased domain and follow the prompts.

### Step 3: Update DNS Settings
- Netlify will provide DNS records (usually CNAME or A records).
- Log in to your domain registrar.
- Find the DNS settings for your domain and update them with the records Netlify gives you.

### Step 4: Wait for Propagation
- DNS changes can take a few minutes to several hours to propagate.

### Step 5: (Optional) Enable HTTPS
- Netlify provides free SSL certificates via Let’s Encrypt. Enable this in the Netlify domain settings for secure HTTPS.

---

## 3. Integrating EmailJS

EmailJS lets you send emails directly from your website without a backend.

### Step 1: Create an EmailJS Account
- Go to [EmailJS](https://www.emailjs.com/) and sign up for free.

### Step 2: Set Up an Email Service
- Add an email service (e.g., Gmail, Outlook) in the EmailJS dashboard.
- Create an email template for your messages.

### Step 3: Get Your EmailJS Credentials
- In EmailJS dashboard, note your **Service ID**, **Template ID**, and **User/Public Key**.

### Step 4: Add EmailJS to Your Project
1. Find the `index.html` file in your project folder and change `YOUR_PUBLIC_KEY` to the value found in EmailJS.
   
   ```html
   <script src="https://cdn.jsdelivr.net/npm/emailjs-com@3/dist/email.min.js"></script>
   <script>
     (function(){
        emailjs.init('YOUR_PUBLIC_KEY');
     })();
   </script>
   ```

3. Find the `script.js` file in your project folder and replace `YOUR_SERVICE_ID` and `YOUR_TEMPLATE_ID` with the values found in EmailJS. 
   
   ```javascript
   document.getElementById('contact-form').addEventListener('submit', function(e) {
     e.preventDefault();
     emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', this)
       .then(function() {
         alert('Email sent!');
       }, function(error) {
         alert('Failed to send email: ' + error);
       });
   });
   ```

---

## 4. Test Everything
- Open your site in the browser.
- Test the contact form: submit a message and check if you receive the email.
- If using Netlify, use your Netlify live URL to test.

---

## 5. Resources
- Netlify Docs: https://docs.netlify.com/
- EmailJS Docs: https://www.emailjs.com/docs/

---

You're all set! You can now edit your site, host it on Netlify, use a custom domain, and send emails from your contact form.
