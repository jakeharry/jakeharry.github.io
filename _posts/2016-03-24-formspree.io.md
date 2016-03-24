---
layout: post
title: (formspree.io) a simple static contact form
---

Who would've thought contacting me is so easy?

So I decided that simply putting my e-mail address on my [about]({{ site.url }}/about/) was not good enough. I needed to have a contact form.

Remembering that github pages is all about static content, I was on a quest to find a contact form which was both static and had some sort of spam filtering. No one wants to wake up to 10,000 e-mails which are bot spam.

It didn't take me long to find [formspree.io](http://formspree.io/) - "No PHP, Javascript or sign up required — perfect for static sites!" Eureka.

The basic example that formspree provide is below

    <form action="https://formspree.io/your@email.com"
      method="POST">
        <input type="text" name="name">
       <input type="email" name="_replyto">
       <input type="submit" value="Send">
    </form> 

It's literally THAT simple. Swap in your@email.com with your e-mail of choice and the form is straight away ready to go. Upon the first submit to your form, you will get an e-mail to confirm you wish to receive e-mails from the formspree you've created. Once you confirm this it's 100% operational. Fascinating.

"But hang on Jake" you say. "You said that your quest involved finding a contact form which has sort of spam filtering? I cannot see any form of spam filtering in the example above. What gives?!"
Slow down young padiwan, for you are yet to discover 'Advanced Features' of formspree.

_gotcha
  <input type="text" name="_gotcha" style="display:none" />
how clever? You can include an input with the name="_gotcha" which, if filled out will not send the e-mail via formspree. You'll notice the style="display:none" which hides the form from human eyes, so, all human entries should not have this field filled in.

There are many custom attributes for the formspree form and, as you can see below my final copy is far more advanced than the original example that formspree provide.

    <form action="//formspree.io/jakesbits@gmail.com" method="POST">
        <fieldset>
           <label for="name">Your name</label><br>
           <input type="text" name="name" placeholder="Name" required>
       </fieldset>
       <fieldset>
            <label for="_replyto">Your email</label><br>
            <input type="email" name="_replyto" placeholder="example@domain.com" required>
        </fieldset>
        <fieldset>
           <label for="message">Your message</label><br>
            <textarea name="message" rows="1" placeholder="Message" required></textarea>
       </fieldset>
        <input class="hidden" type="text" name="_gotcha" style="display:none">
        <input class="hidden" type="hidden" name="_subject" value="Message via http://jakeharry.github.io">

        <input class="button submit" type="submit" value="Send">
      </form>    
      
And the final result: (feel free to drop me a line)

<form action="//formspree.io/jakesbits@gmail.com" method="POST">
    <fieldset>
      <label for="name">Your name</label><br>
       <input type="text" name="name" placeholder="Name" required>
   </fieldset>
   <fieldset>
        <label for="_replyto">Your email</label><br>
        <input type="email" name="_replyto" placeholder="example@domain.com" required>
    </fieldset>
    <fieldset>
       <label for="message">Your message</label><br>
        <textarea name="message" rows="1" placeholder="Message" required></textarea>
   </fieldset>
    <input class="hidden" type="text" name="_gotcha" style="display:none">
    <input class="hidden" type="hidden" name="_subject" value="Message via http://jakeharry.github.io">

    <input class="button submit" type="submit" value="Send">
  </form> 
