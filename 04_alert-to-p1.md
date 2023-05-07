# A Journey from Alert 1 to P1

(an offensive talk, this is mostly for Jr. to Sr. pentesters)

- "Content security policy is one of the greatest controls you can employ"
- "any action a red teamer takes you can detect them. Just need the right things in place."


XSS has become *slightly* less effective because the browsers are doing a good job preventing it
- so attack techniques have to change


triggering "alert(1)" is bad, but...
- people need to know what you can do with XSS
- dev: Why is popping an alert box bad?
- hacker: because you can do `<this>` with it

What can you do with XSS?
- steal cookies
- bypass CSRF (cross-site request forgery)
    - with XSS, you can get past this...if you know how to weaponize it
- XSS on a domain...you can do anything that user can do on that domain

Alert(1) sucks

You can't argue with a root shell
- if you can get here, there is no wrong way you got there

Soften the blow of security findings, by putting a cat pictures with your PoC, lol
- https://placekitten.com/600/200


## XSS Points

- you can manipulate the DOM by shoving HTML in the URL bar?
- everything is an API if you try hard enough :D
    - Python + Beautiful Soup ("requests" + "bs4")
    - try automating Python to auto-login, bonus points for doing this after credential harvesting


## SET (Social Engineer Toolkit)

- this will clone a website for you
- wget can clone a website
- some websites have protection against cloning from SET
    - *Does your website have protection against this?*


## CSP (content security policy)

- it's a header
- where to load images from, where to load scripts from
- but many people (devs, security professionals) don't know how to deploy it
    - people deploy stuff with it, site breaks, and they give up on it
- it's the single most effecive preventer of XSS attacks


## Did your XSS attempt fail? Check the browser console.

- for instance, lots of JavaScript keywords are blocked...
- BUT you can put ***all the HTML*** you want into the page
- OR they block scripts, but not blocking `<iframes>`
- OR try all attributes, try all HTML elements
- you can execute JavaScript from CSS? (figure out how)
- what is the URL fragment value? You can put your code in here. And then access your JavaScript in here.
- PLUS...much of this, is never sent to blue-team, because it's all running client side
- keep in mind, asynchronous loading
    - if your XSS loads in the first reosurces, then the rest of the page won't load
    - so you can wait for stuff


## CSP header

- look at the CSP header being sent to you
- CSP might block network connections...but you can dynamically create an image, and if CSP allows images
    - and then you can exploit/export stuff via this image


NOTE: If you're just starting out, stand up a web server on AWS
- and just watch the GET requests from all of the internet stuff scanning you

1. Get the XSS exploit
2. dev locally to build the phish
3. more stuff
    - instead of "clearing things out" just push the body down so the user doesn't see it, lol
4. once you steal the creds...you'll need a session
5. but you don't need to sit and watch it, because you automated this part with Python + beautiful soup


## How to detect

- watch for things from your website (resources) loading from strange places
- look for referers (is it coming from "phishme"?)
- impossible travel
- login from cloud IPs
- bot detection
    - is a bot doing something in seconds that a user takes minutes to do?
- unexpected URL encoding

- CSP violations
    - you can have CSP automatically report violations to your server
- unexpected user agents