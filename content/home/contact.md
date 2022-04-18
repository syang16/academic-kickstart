+++
# Contact widget.
widget = "contact"  # Do not modify this line!
active = true  # Activate this widget? true/false

title = "Contact"
subtitle = ""

# Order that this section will appear in.
weight = 130

# Automatically link email and phone?
autolink = false

+++
<form name="contact" method="POST" data-netlify="true">
  <p>
    <label>Your Name: <input type="text" name="name" /></label>
  </p>
  <p>
    <label>Your Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Message: <textarea name="message"></textarea></label>
  </p>
  <p>
    <button type="submit">Send</button>
  </p>
</form>
