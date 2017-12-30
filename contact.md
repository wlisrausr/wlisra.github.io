---
layout: default
title: "Contact"
---

<div id="contact">
  <h2 class="pageTitle">Contact</h2>

  <div class="contactContent">
    <p>If you have something in your mind that related to me or this blog, please don't hesitate to contact me via the form on this page. I'll be very happy to discuss it with you. Thanks!</p>
  </div>

  <form action="http://formspree.io/wandaisra@gmail.com" method="POST">
    <label for="name">Name</label>
    <input type="text" id="name" name="name" class="full-width" required><br>
    <label for="email">Email Address</label>
    <input type="email" id="email" name="_replyto" class="full-width" required><br>
    <label for="message">Message</label>
    <textarea
      name="message"
      id="message"
      cols="30"
      rows="10"
      class="full-width"
      required></textarea><br>
    <input type="submit" value="Send" class="button">
  </form>
</div>
