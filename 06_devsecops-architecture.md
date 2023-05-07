# DevSecOps Architecture

Note: this is a very dry talk, but it's full of good information for how to finally _write the AppSec program_

Foundational practices

- [insert pic]
- focus on getting these pieces stood up
- clean, and manage immediate worst vulns
- and then work towards blocking

- incident response plan
    - do you have an IR plan for a web application incident


## Program Architecture

This is possibly the most important piece of building these AppSec pieces, programs

Program overview deck: You really need to have a presentation deck for the DevSecOps program

- represent your program well
- keep your headcount


### Welcome packet

- have courtesy
- put everything someone needs to know in one place
- put some presentation around it

### Process diagrams

- talk through the SDLC
- critical proces steps: what's important, what can go wrong
- auditors like to see this too

### System of Record

- a policy that sits on Sharepoint; nothing will do that


## Policy

- Don't ever get emotionally involved
- It's all business
- you'll write a policy, and it will need an exception due to a business case
- Never get emotionally attached


## Application Risk Profile

- Developer security toolkit
    - this is great for building a bridge between security and development
- Logging framework
    - what is the security perspective?
    - is it installed in every app?

- Application Details
    - you're going to have 100s of apps sometimes
    - you need a basic summary, description, and URL


## Application Risk Questions

- How is sensitive data used withint he process this application supports?
    - as things are moving around the app: managers, developers, supporting systems...
    - think about how the more permanent, sensitive information is used

- What system accounts have access to an app? Who has access to those passwords?
    - think API gateways--what apps have access to this app?

- What data is required for this process?


## Application Vulnerabilities

- Re-check these lists, definitions every couple years
- self-audit: how are we addressing each of the "top vuln categories"?


## Dev's Secuiry Toolkit

- set of approved components, or components to solve common web app vulns
- review OWASP's cheat sheets for what is applicable to your team



## Developer "Security Belt" Program

- the first 2 levels are courses: green, yellow
- the orange, brown levels: are projects that basically ask developers to put the dev security toolkit in place
- black belt: focused on leadership, retaining others, and giving developers something to walk away with for mentoring others

