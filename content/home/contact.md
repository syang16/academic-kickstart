+++
# Contact widget.
widget = "contact"  # Do not modify this line!
active = true  # Activate this widget? true/false

title = "Contact"
subtitle = ""

# Order that this section will appear in.
weight = 130

# Automatically link email and phone?
autolink = true

+++
<form id="fs-frm" name="simple-contact-form" accept-charset="utf-8" 
action="https://formspree.io/f/xvolwldk" method="post">
  <fieldset id="fs-frm-inputs">
    <label for="full-name">Full Name</label>
    <br/>
    <input type="text" name="name" id="full-name" placeholder="First and Last" required="">
    <br/>
    <label for="email-address">Email Address</label>
    <br/>
    <input type="email" name="_replyto" id="email-address" placeholder="email@domain.tld" required="">
    <br/>
    <label for="message">Message</label>
    <br/>
    <textarea rows="5" name="message" id="message" placeholder="" required=""></textarea>
    <br/>
    <input type="hidden" name="_subject" id="email-subject" value="Contact Form Submission">
  </fieldset>
  <input type="submit" value="Submit">
</form>
