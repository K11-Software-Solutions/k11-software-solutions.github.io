# Formspree Contact Form Setup Guide

This guide explains how to create and integrate a Formspree contact form for the K11 Software Solutions website.

## About Formspree

Formspree is a form backend service that makes it easy to add functional contact forms to static websites. It handles form submissions and forwards them to your email address without requiring server-side code.

### Key Features:
- ✅ Free tier available (50 submissions/month)
- ✅ Spam protection built-in
- ✅ No backend code required
- ✅ Email notifications
- ✅ Form validation
- ✅ Easy setup and integration

## Creating Your Formspree Form

### Step 1: Sign Up for Formspree

1. Go to [https://formspree.io](https://formspree.io)
2. Click **"Get Started"** or **"Sign Up"**
3. Create an account using:
   - Email address (k11softwaresolutions@gmail.com)
   - Or sign up with Google/GitHub
4. Verify your email address

### Step 2: Create a New Form

1. After logging in, click **"+ New Form"** button
2. Enter form details:
   - **Form Name:** "K11 Software Solutions - Contact Form"
   - **Email:** k11softwaresolutions@gmail.com (where submissions will be sent)
3. Click **"Create Form"**

### Step 3: Get Your Form Endpoint

After creating the form, you'll see your unique form endpoint:

```
https://formspree.io/f/YOUR_FORM_ID
```

Copy this endpoint URL - you'll need it in the next step.

**Example:** If your form ID is `xyzabc123`, your endpoint would be:
```
https://formspree.io/f/xyzabc123
```

### Step 4: Update the Website

1. Open `contact.md` in your repository
2. Find this line (near the top of the form):
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="contact-form">
   ```
3. Replace `YOUR_FORM_ID` with your actual form ID from Formspree
   ```html
   <form action="https://formspree.io/f/xyzabc123" method="POST" class="contact-form">
   ```
4. Save the file and commit the changes

### Step 5: Configure Form Settings (Optional)

In the Formspree dashboard, you can configure additional settings:

#### Email Settings:
- **Reply-To:** Enable to reply directly to form submitters
- **CC/BCC:** Add additional recipients
- **Custom Subject:** Customize email subject lines

#### Spam Protection:
- **reCAPTCHA:** Enable for additional spam protection (optional)
- **Honeypot:** Already included in the form code
- **Block List:** Add domains or emails to block

#### Integrations:
- **Webhooks:** Send data to other services
- **Slack:** Get notifications in Slack
- **Zapier:** Connect to 3000+ apps

#### Submissions:
- **Archive:** View all submissions in dashboard
- **Export:** Download submissions as CSV

## Testing the Form

### Local Testing:

1. Build the site locally:
   ```bash
   bundle exec jekyll serve
   ```

2. Navigate to [http://localhost:4000/contact/](http://localhost:4000/contact/)

3. Fill out the form with test data:
   - Name: Test User
   - Email: your-test-email@example.com
   - Subject: Test Submission
   - Message: This is a test message

4. Click **"Send Message"**

### First Submission Verification:

**Important:** The first time someone submits the form, Formspree will:
1. Send a verification email to k11softwaresolutions@gmail.com
2. You must click the verification link in the email
3. After verification, all future submissions will be automatically forwarded

### Production Testing:

1. After deploying to GitHub Pages, visit:
   ```
   https://k11-software-solutions.github.io/contact/
   ```

2. Submit a test form to ensure everything works correctly

3. Check your email (k11softwaresolutions@gmail.com) for the submission

## Form Fields and Functionality

The contact form includes the following fields:

### Required Fields:
1. **Name** (`name`) - Full name of the person contacting you
2. **Email** (`email`) - Email address for replies (validated)
3. **Message** (`message`) - Main message content

### Optional Fields:
1. **Subject** (`subject`) - Brief description of inquiry

### Hidden Fields (for functionality):
- `_subject` - Sets custom email subject line
- `_next` - Redirects to thank you message after submission
- `_gotcha` - Honeypot field for spam protection (invisible to users)

## Understanding the Form Code

### Form Action:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```
- Sends form data to your Formspree endpoint

### Hidden Fields:
```html
<input type="hidden" name="_subject" value="New Contact Form Submission - K11 Software Solutions">
```
- Customizes the email subject line

```html
<input type="hidden" name="_next" value="https://k11-software-solutions.github.io/contact/#thank-you">
```
- Redirects users after successful submission

```html
<input type="text" name="_gotcha" style="display:none">
```
- Honeypot spam protection (bots will fill this, humans won't see it)

## Viewing Submissions

### In Formspree Dashboard:
1. Log in to [https://formspree.io](https://formspree.io)
2. Click on your form name
3. View the **"Submissions"** tab
4. See all form submissions with:
   - Submission date/time
   - Sender details
   - Message content
   - Spam score

### In Email:
- All submissions are automatically forwarded to k11softwaresolutions@gmail.com
- Emails include all form data
- Reply directly to the sender from your email

### Export Data:
- Click **"Export"** in the Submissions tab
- Download as CSV for record keeping or analysis

## Spam Protection

Formspree includes multiple layers of spam protection:

### Built-in Protection:
1. **Honeypot Field** - Already included in the form code
2. **Rate Limiting** - Prevents rapid-fire submissions
3. **Email Validation** - Ensures valid email addresses
4. **Spam Filtering** - ML-based spam detection

### Optional Protection:
1. **reCAPTCHA** - Enable in Formspree dashboard settings
2. **Domain Verification** - Restrict submissions to your domain only
3. **Block Lists** - Manually block problematic domains/emails

### Monitoring Spam:
- Check spam scores in the Formspree dashboard
- Mark submissions as spam to improve filtering
- Review blocked submissions periodically

## Free Tier Limits

The Formspree free tier includes:
- ✅ 50 submissions per month
- ✅ 1 form
- ✅ Unlimited emails
- ✅ Basic spam filtering
- ✅ Email notifications
- ✅ Form archiving

### If You Exceed Limits:
1. **Upgrade to paid plan** ($10/month for 1000 submissions)
2. **Wait until next month** (counter resets monthly)
3. **Use alternative form** (create new form with different email)

## Troubleshooting

### Form Not Submitting:
- ✅ Check that form endpoint URL is correct
- ✅ Verify you've verified your email with Formspree
- ✅ Check browser console for JavaScript errors
- ✅ Ensure method="POST" is set on the form

### Not Receiving Emails:
- ✅ Check spam/junk folder
- ✅ Verify email address in Formspree settings
- ✅ Confirm email verification was completed
- ✅ Check Formspree dashboard for submissions
- ✅ Verify your email provider isn't blocking Formspree

### Form Showing Formspree Page:
- ✅ Ensure `_next` hidden field is set correctly
- ✅ Check that redirect URL is valid
- ✅ Clear browser cache and try again

### Styling Issues:
- ✅ Check that custom CSS is loading
- ✅ Test on different browsers
- ✅ Verify mobile responsiveness
- ✅ Check browser console for CSS errors

### Spam Submissions:
- ✅ Enable reCAPTCHA in Formspree dashboard
- ✅ Verify honeypot field is present and hidden
- ✅ Add problematic domains to block list
- ✅ Report spam submissions in dashboard

## Customization Options

### Custom Success Message:
Modify the thank-you message in `contact.md`:
```html
<div id="thank-you" class="thank-you-message">
  <h3>Custom Title</h3>
  <p>Custom message text...</p>
</div>
```

### Additional Form Fields:
Add new fields to the form:
```html
<div class="form-group">
  <label for="phone">Phone Number</label>
  <input type="tel" id="phone" name="phone" placeholder="(555) 123-4567">
</div>
```

### Form Styling:
- Styles are included in `contact.md` within `<style>` tags
- Modify colors, spacing, and layout as needed
- Ensure styles match your site theme

### Email Template:
Customize the email subject in the hidden field:
```html
<input type="hidden" name="_subject" value="Your Custom Subject Here">
```

## Best Practices

### Response Time:
1. ✅ Check email daily for new submissions
2. ✅ Aim to respond within 24 business hours
3. ✅ Set up email filters for Formspree emails
4. ✅ Consider Slack integration for instant notifications

### Data Management:
1. ✅ Export submissions monthly for backup
2. ✅ Review spam scores regularly
3. ✅ Archive old submissions
4. ✅ Maintain organized records

### Form Optimization:
1. ✅ Test form regularly on different devices
2. ✅ Monitor submission completion rate
3. ✅ Keep form fields minimal (reduce friction)
4. ✅ Use clear, descriptive labels
5. ✅ Provide helpful placeholder text

### Security:
1. ✅ Keep form endpoint private (only in code)
2. ✅ Enable domain verification in Formspree
3. ✅ Use HTTPS for all form submissions
4. ✅ Review security settings periodically

## Alternative Form Services

If Formspree doesn't meet your needs, consider these alternatives:

1. **Netlify Forms** - If hosting on Netlify
2. **Getform** - Similar to Formspree, generous free tier
3. **Form Bolt** - Another Formspree alternative
4. **Basin** - Form backend with advanced features
5. **Formsubmit.co** - Free, no account required

## Advanced Features

### AJAX Submission (Optional):
For a smoother user experience without page reload:
```javascript
document.querySelector('.contact-form').addEventListener('submit', async (e) => {
  e.preventDefault();
  const form = e.target;
  const data = new FormData(form);
  const response = await fetch(form.action, {
    method: 'POST',
    body: data,
    headers: { 'Accept': 'application/json' }
  });
  if (response.ok) {
    // Show success message
    form.style.display = 'none';
    document.querySelector('.thank-you-message').style.display = 'block';
  }
});
```

### File Uploads (Paid Plans):
Add file upload capability (requires paid plan):
```html
<input type="file" name="attachment" accept=".pdf,.doc,.docx">
```

### Conditional Fields:
Show/hide fields based on selections using JavaScript

## Support and Resources

### Formspree Documentation:
- [Official Docs](https://help.formspree.io/)
- [API Reference](https://help.formspree.io/hc/en-us/articles/360013580813)
- [Integration Guides](https://help.formspree.io/hc/en-us/sections/360006167374)

### Get Help:
- **Formspree Support:** support@formspree.io
- **Community Forum:** GitHub Discussions
- **Status Page:** status.formspree.io

### Related Articles:
- [Spam Prevention Tips](https://help.formspree.io/hc/en-us/articles/360013580813)
- [Form Configuration](https://help.formspree.io/hc/en-us/articles/360017735154)
- [Troubleshooting Guide](https://help.formspree.io/hc/en-us/sections/360006167414)

---

For additional help with Formspree, visit the [Formspree Help Center](https://help.formspree.io/).
