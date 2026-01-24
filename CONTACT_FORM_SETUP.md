# Google Forms Contact Form Setup Guide

This guide explains how to create and integrate a Google Forms contact form for the K11 Software Solutions website.

## Creating the Google Form

### Step 1: Create a New Form

1. Go to [Google Forms](https://forms.google.com)
2. Click the **"+ Blank"** button to create a new form
3. Give your form a title: "K11 Software Solutions - Contact Form"
4. Add a description: "Get in touch with us. We'll respond within 24 business hours."

### Step 2: Add Form Fields

Add the following fields to your form:

#### 1. Full Name
- **Question Type:** Short answer
- **Required:** Yes
- Click "Required" toggle to make it mandatory

#### 2. Email Address
- **Question Type:** Short answer
- **Required:** Yes
- Click the three dots menu → "Response validation"
- Add validation: "Text" → "Email"

#### 3. Company/Organization (Optional)
- **Question Type:** Short answer
- **Required:** No

#### 4. Subject
- **Question Type:** Short answer
- **Required:** Yes
- Add helper text: "Brief description of your inquiry"

#### 5. Message
- **Question Type:** Paragraph
- **Required:** Yes
- Add helper text: "Tell us about your project or question"

#### 6. Project Type (Optional)
- **Question Type:** Multiple choice
- **Options:**
  - Web Development
  - Mobile App Development
  - Cloud Solutions
  - Consulting
  - Other

#### 7. Budget Range (Optional)
- **Question Type:** Multiple choice
- **Options:**
  - Under $10,000
  - $10,000 - $25,000
  - $25,000 - $50,000
  - $50,000+
  - Not sure yet

#### 8. Timeline (Optional)
- **Question Type:** Multiple choice
- **Options:**
  - ASAP (within 1 month)
  - 1-3 months
  - 3-6 months
  - 6+ months
  - Flexible

### Step 3: Customize Form Appearance

1. Click the **Palette icon** (Customize theme) at the top
2. Choose a color scheme that matches the website:
   - **Primary Color:** Use a professional blue or your brand color
   - **Background:** White or light gray
   - **Font:** Choose a clean, readable font (Roboto, Arial, or similar)

3. Click **Preview** (eye icon) to see how it looks

### Step 4: Configure Form Settings

1. Click the **Settings** (gear icon) at the top
2. Configure these options:

**General:**
- ✅ Collect email addresses (automatically from the Email field)
- ✅ Limit to 1 response (optional, prevents spam)
- ✅ Edit after submit (allow users to edit responses)

**Presentation:**
- ✅ Show progress bar (if you have multiple sections)
- Confirmation message: "Thank you for contacting K11 Software Solutions! We'll respond within 24 business hours."

**Quizzes:** (Leave unchecked - this is not a quiz)

### Step 5: Set Up Email Notifications

1. Click the **Responses** tab at the top
2. Click the three dots menu → "Get email notifications for new responses"
3. This will send an email to `k11softwaresolutions@gmail.com` for each submission

**Alternative:** Link to Google Sheets for better tracking:
1. Click the **Responses** tab
2. Click the green Google Sheets icon
3. Create a new spreadsheet: "Contact Form Responses"
4. Set up email notifications from Google Sheets if needed

### Step 6: Get the Embed Code

1. Click the **Send** button at the top right
2. Click the **<> Embed** icon (middle option)
3. You'll see HTML code like:
   ```html
   <iframe src="https://docs.google.com/forms/d/e/[FORM_ID]/viewform?embedded=true" 
           width="640" 
           height="877" 
           frameborder="0" 
           marginheight="0" 
           marginwidth="0">Loading…</iframe>
   ```
4. Copy the URL from the `src` attribute

### Step 7: Update the Website

1. Open `contact.md` in your repository
2. Find this line:
   ```html
   <iframe src="https://docs.google.com/forms/d/e/YOUR_FORM_ID_HERE/viewform?embedded=true"
   ```
3. Replace `YOUR_FORM_ID_HERE` with your actual form ID from the embed code
4. Save the file and commit the changes

## Testing the Form

1. Build the site locally: `bundle exec jekyll serve`
2. Navigate to [http://localhost:4000/contact/](http://localhost:4000/contact/)
3. Verify the form displays correctly
4. Submit a test entry to ensure it works
5. Check that you receive the email notification

## Maintaining the Form

### Viewing Responses

1. Go to [Google Forms](https://forms.google.com)
2. Open your contact form
3. Click the **Responses** tab to view all submissions
4. Or open the linked Google Sheet if you created one

### Editing the Form

To make changes to form fields or settings:
1. Go to [Google Forms](https://forms.google.com)
2. Open your contact form
3. Make your changes (add/remove fields, change questions, etc.)
4. The changes will automatically appear on your website (no need to update the embed code)

### Spam Protection

Google Forms includes built-in spam protection. Additional options:
1. Enable "Limit to 1 response" in Settings
2. Add a CAPTCHA for anonymous users (automatic in Google Forms)
3. Review responses regularly and report spam if necessary

## Alternative: Direct Link Instead of Embed

If you prefer a direct link instead of an embedded form:

1. Get the form's public URL from the **Send** button → **Link** icon
2. Update `contact.md` with a button:
   ```markdown
   [Contact Us via Form](https://forms.gle/YOUR_SHORT_LINK){: .btn .btn-primary}
   ```

## Troubleshooting

### Form Not Displaying
- Check that the form is set to "Anyone can respond" (not restricted to organization)
- Verify the iframe URL is correct
- Check browser console for errors

### Form Appears Cut Off
- Adjust the height in `contact.md` CSS (default is 900px)
- Test on mobile devices and adjust the responsive height

### Not Receiving Email Notifications
- Check your Google account's notification settings
- Verify the email address in Google Forms settings
- Check spam/junk folder
- Set up Google Sheets with Apps Script for custom notifications

## Security Considerations

- Google Forms provides HTTPS encryption
- No sensitive data is stored on your website (only in Google Forms)
- Review Google's privacy policy and terms of service
- Consider adding a privacy notice on your contact page

## Best Practices

1. **Test regularly** - Submit test entries monthly to ensure it works
2. **Respond promptly** - Aim for 24-hour response time as promised
3. **Monitor spam** - Check for and report spam submissions
4. **Back up responses** - Export to Google Sheets regularly
5. **Update fields** - Adjust form questions based on common inquiries

---

For additional help with Google Forms, visit the [Google Forms Help Center](https://support.google.com/docs/topic/9054603).
