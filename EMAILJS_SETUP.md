# 📧 EmailJS Setup - Quick Guide

## 🔑 Where to Add Your Credentials

Open `index.html` and scroll to **line 14-36** (in the `<head>` section).

You'll see this configuration block:

```javascript
const EMAILJS_CONFIG = {
  publicKey: 'YOUR_PUBLIC_KEY',      // ← Replace this
  serviceId: 'YOUR_SERVICE_ID',      // ← Replace this
  templateId: 'YOUR_TEMPLATE_ID',    // ← Replace this
  recipientEmail: 'YOUR_EMAIL@example.com'  // ← Replace this
};
```

## 📝 Step-by-Step Setup

### 1️⃣ Get Your Public Key
1. Go to https://dashboard.emailjs.com/admin/account
2. Copy your **Public Key**
3. Replace `'YOUR_PUBLIC_KEY'` with your actual key

### 2️⃣ Create Email Service & Get Service ID
1. Go to https://dashboard.emailjs.com/admin/services
2. Click **"Add New Service"**
3. Select your email provider (Gmail, Outlook, etc.)
4. Connect your account
5. Copy the **Service ID** (e.g., `service_gmail`)
6. Replace `'YOUR_SERVICE_ID'` with your Service ID

### 3️⃣ Create Email Template & Get Template ID
1. Go to https://dashboard.emailjs.com/admin/templates
2. Click **"Create New Template"**
3. Use this template:

**Subject:**
```
🎉 New Dunk Tank Booking Request - {{customer_name}}
```

**Body:**
```
New Booking Request Received!
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

👤 Customer Information:
   Name: {{customer_name}}
   Email: {{customer_email}}
   Phone: {{customer_phone}}

📅 Event Details:
   Date: {{event_date}}
   Duration: {{event_duration}}
   Type: {{event_type}}
   County: {{county}}

📝 Message:
{{message}}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply to: {{reply_to}}
```

4. Click **"Save"**
5. Copy the **Template ID** (e.g., `template_abc123`)
6. Replace `'YOUR_TEMPLATE_ID'` with your Template ID

### 4️⃣ Add Your Email Address
Replace `'YOUR_EMAIL@example.com'` with the email where you want to receive booking requests.

## ✅ Final Configuration Example

Your config should look like this:

```javascript
const EMAILJS_CONFIG = {
  publicKey: 'AbC123XyZ',              
  serviceId: 'service_gmail',          
  templateId: 'template_booking',      
  recipientEmail: 'bookings@bouncyaround.com'
};
```

## 🧪 Test the Form

1. Save the `index.html` file
2. Open it in your browser
3. Scroll to **"Book Your Dunk Tank"** section
4. Fill out the form and submit
5. Check your email for the booking notification!

## 🆘 Troubleshooting

| Issue | Solution |
|-------|----------|
| "EmailJS is not configured" alert | Make sure all 4 values are replaced in `EMAILJS_CONFIG` |
| Email not received | Check spam folder, verify Service ID and Template ID |
| Template variables empty | Ensure variable names match exactly: `{{customer_name}}`, etc. |
| Console errors | Press F12, check Console tab for specific error messages |

## 📊 EmailJS Dashboard

- **Account/Keys:** https://dashboard.emailjs.com/admin/account
- **Services:** https://dashboard.emailjs.com/admin/services
- **Templates:** https://dashboard.emailjs.com/admin/templates
- **Email History:** https://dashboard.emailjs.com/admin/history

---

**Free Tier:** 200 emails/month  
**Upgrade:** https://www.emailjs.com/pricing/
