### Man In The Middle (MITM)

A man-in-the-middle attack is a type of cyberattack where a malicious actor inserts him/herself into a conversation between two parties, impersonates both parties and gains access to information that the two parties were trying to send to each other. A man-in-the-middle attack allows a malicious actor to intercept, send and receive data meant for someone else, or not meant to be sent at all, without either outside party knowing until it is too late.

#### MITM attack example:
![](https://www.veracode.com/sites/default/files/styles/media_responsive_widest/public/mitm-flow_0.gif?itok=SH6tndH8)

#### How to prevent MITM:

  * Look for the “green glow” in the address bar: Man in the middle in the wild today can be combated through Extended Validation (EV) SSL Certificates and to notice when there is an absence of green. EV SSL Certificates definitively confirm the identity of the organization that owns the Web site. Online criminals do not have access to EV SSL Certificates for the sites they’re counterfeiting and therefore cannot spoof the green glow that shows that an authenticated Web site is secure.

  * Download the latest version of high security Web browsers.

  ### XSS
  _**Cross-site scripting (XSS) is a code injection attack that allows an attacker to execute malicious JavaScript in another user's browser.**_

   > The attacker does not directly target his victim. Instead, he exploits a vulnerability in a website that the victim visits, in order to get the website to deliver the malicious JavaScript for him. To the victim's browser, the malicious JavaScript appears to be a legitimate part of the website, and the website has thus acted as an unintentional accomplice to the attacker.


  #### Cross-Site Scripting (XSS) attacks occur when:
  1 - Data enters a Web application through an  untrusted source, most frequently a web request.

  2 - The data is included in dynamic content that is sent to a web user without being validated for malicious content.

    The malicious content sent to the web browser often takes the form of a segment of JavaScript, but may also include HTML, Flash, or any other type of code that the browser may execute. The variety of attacks based on XSS is almost limitless, but they commonly include transmitting private data, like cookies or other session information, to the attacker, redirecting the victim to web content controlled by the attacker, or performing other malicious operations on the user's machine under the guise of the vulnerable site.

    ![XSS](https://d3eaqdewfg2crq.cloudfront.net/wp-content/uploads/2013/08/Diagram-Describing-Blind-XSS-Attack.gif)


  ----------------
  ### **Cross-Site Request Forgery (CSRF)**
  is an attack outlined in the OWASP Top 10 whereby a malicious website will send a request to a web application that a user is already authenticated against from a different website. This way an attacker can access functionality in a target web application via the victim's already authenticated browser. Targets include web applications like social media, in-browser email clients, online banking and web interfaces for network devices.
  #### Executing a CSRF Attack:
  attackers have added this line of code:<br>
  ``` <iframe src="//www.veracode.com/%3Ca%20href%3D"http://examplebank.com/app/transferFunds?amount=1500&destinationAccount=123456789">http://examplebank.com/app/transferFunds?amount=1500&destinationAccount=..." > ```

  Upon loading that iframe, my browser will send that request to examplebank.com, which my browser has already logged in as me. The request will be processed and send $1,500.00 to account 123456789.


  #### Another Example:
  The attackers have also set up a proxy server at 123.45.67.89 that will log all traffic that goes through it and look for things like passwords and session tokens.
  As I clicked through the configuration guide, I missed the 1x1 pixel image that failed to load:<br>
  ```<img src=”http://192.168.1.1/admin/config/outsideInterface?nexthop=123.45.67.89” alt=”pwned” height=”1” width=”1”/>```
  _
  #### How to Preventing (CSRF)?
  look at today's workshop [link](https://github.com/foundersandcoders/ws-session-management)


### References

  * [Man-in-the-Middle Tutorial](https://www.veracode.com/security/man-middle-attack)

  * [How to protect from man-in-the-middle attacks](https://www.helpnetsecurity.com/2009/02/25/how-to-protect-from-man-in-the-middle-attacks/)
  * [www.owasp.org](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)
  * [Excess XSS](https://excess-xss.com/)
  * [VeraCode](https://www.veracode.com/security/csrf)
