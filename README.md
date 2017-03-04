# Staticman + reCAPTCHA

This is a demo Jekyll site showing how to integrate [Staticman](https://staticman.net) with Google's [reCAPTCHA](https://www.google.com/recaptcha/intro/).

## Getting started

After [following the steps](https://staticman.net/docs) to install Staticman, you need to integrate reCAPTCHA.

1. [Sign up](https://www.google.com/recaptcha/admin) to reCAPTCHA. You'll be assigned a *Site key* and *Secret*.

1. Encrypt the secret using Staticman's encryption endpoint:
  
  ```
  https://api.staticman.net/v2/encrypt/YOUR-SECRET
  ```
   
1. Take the site key and the encrypted secret and add a reCAPTCHA block to your Staticman config file:
   
  ```yml
  reCaptcha:
    enabled: true
    siteKey: "YOUR-SITE-KEY"
    secret: "YOUR-ENCRYPTED-SECRET"
  ```
   
1. Add the reCAPTCHA credentials to your form:

  ```html
  <input type="hidden" name="options[reCaptcha][siteKey]" value="YOUR-SITE-KEY">
  <input type="hidden" name="options[reCaptcha][secret]" value="YOUR-ENCRYPTED-SECRET">
  ```

  
1. Add the reCAPTCHA script and DOM element

  ```html
  <div class="g-recaptcha" data-sitekey="YOUR-SITE-KEY"></div>
  <script src='https://www.google.com/recaptcha/api.js'></script>
  ```

## Reporting issues

Please [open an issue](https://github.com/eduardoboucas/staticman/issues/new) in the Staticman repository.
