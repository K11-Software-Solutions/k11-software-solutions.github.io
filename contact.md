---
layout: page
title: Contact Us
permalink: /contact/
---

## Get in Touch

We'd love to hear about your project and discuss how we can help. Fill out the contact form below or reach out using the information provided.

## Contact Form

<div class="contact-form-container">
  <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="contact-form">
    <div class="form-group">
      <label for="name">Name <span class="required">*</span></label>
      <input type="text" id="name" name="name" required placeholder="Your Full Name">
    </div>
    
    <div class="form-group">
      <label for="email">Email <span class="required">*</span></label>
      <input type="email" id="email" name="email" required placeholder="your.email@example.com">
    </div>
    
    <div class="form-group">
      <label for="subject">Subject</label>
      <input type="text" id="subject" name="subject" placeholder="What's this about?">
    </div>
    
    <div class="form-group">
      <label for="message">Message <span class="required">*</span></label>
      <textarea id="message" name="message" rows="8" required placeholder="Tell us about your project or question..."></textarea>
    </div>
    
    <input type="hidden" name="_subject" value="New Contact Form Submission - K11 Software Solutions">
    <input type="hidden" name="_next" value="https://k11-software-solutions.github.io/contact/#thank-you">
    <input type="text" name="_gotcha" style="display:none">
    
    <button type="submit" class="submit-btn">Send Message</button>
  </form>
  
  <div id="thank-you" class="thank-you-message" style="display:none;">
    <h3>Thank You!</h3>
    <p>Your message has been sent successfully. We'll get back to you within 24 business hours.</p>
  </div>
</div>

<style>
.contact-form-container {
  margin: 2rem 0;
  background: white;
  border-radius: 8px;
  padding: 30px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: 600;
  color: #333;
  font-size: 1rem;
}

.required {
  color: #dc3545;
}

.form-group input[type="text"],
.form-group input[type="email"],
.form-group textarea {
  width: 100%;
  padding: 12px 15px;
  border: 2px solid #e0e0e0;
  border-radius: 5px;
  font-size: 1rem;
  font-family: inherit;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  box-sizing: border-box;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #667eea;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
}

.form-group textarea {
  resize: vertical;
  min-height: 150px;
}

.submit-btn {
  width: 100%;
  padding: 15px 30px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 10px;
}

.submit-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(102, 126, 234, 0.4);
}

.submit-btn:active {
  transform: translateY(0);
}

.thank-you-message {
  text-align: center;
  padding: 40px 20px;
  background: #f8f9fa;
  border-radius: 8px;
  border-left: 4px solid #28a745;
}

.thank-you-message h3 {
  color: #28a745;
  margin-bottom: 15px;
}

.thank-you-message p {
  color: #666;
  font-size: 1.1rem;
}

@media (max-width: 768px) {
  .contact-form-container {
    padding: 20px;
  }
  
  .form-group input[type="text"],
  .form-group input[type="email"],
  .form-group textarea {
    font-size: 16px; /* Prevents zoom on iOS */
  }
}
</style>

<script>
// Show thank you message if redirected back with #thank-you
if (window.location.hash === '#thank-you') {
  document.querySelector('.contact-form').style.display = 'none';
  document.querySelector('.thank-you-message').style.display = 'block';
}
</script>

---

### Alternative Contact Methods

**Email:** [k11softwaresolutions@gmail.com](mailto:k11softwaresolutions@gmail.com)

Feel free to send us a detailed message about your project needs, and we'll get back to you as soon as possible.

### Business Hours
**Monday - Friday:** 9:00 AM - 6:00 PM PST  
*We typically respond to inquiries within 24 business hours.*

### Connect With Us

Stay connected and follow our latest updates on social media:

- **GitHub:** [github.com/k11-software-solutions](https://github.com/k11-software-solutions)
- **LinkedIn:** [linkedin.com/company/k11-software-solutions](https://linkedin.com/company/k11-software-solutions)

---

## What's Next?

Once you reach out, here's what you can expect:

1. **Initial Response** - We'll acknowledge your inquiry within 24 business hours
2. **Discovery Call** - We'll schedule a call to discuss your project in detail
3. **Proposal** - We'll provide a detailed proposal with timeline and cost estimates
4. **Project Kickoff** - Once approved, we'll begin working on your project

We look forward to working with you!

[View Our Services](/services/){: .btn .btn-primary} [View Portfolio](/portfolio/){: .btn .btn-secondary}
