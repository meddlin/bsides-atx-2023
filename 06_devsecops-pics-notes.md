

## from pic (IMG_4342)

Foundational Practices and Controls
- Secure code training
- Security by design
- Security testing
    - IDE plug-in (security spell checker)
    - Static application security testing (SAST)
    - Dynamic application security testing (DAST)
    - Software composition analysis (SCA)
    - Web application penetration test
- Web application firewall (WAF)
- API gateway
- Incident response plan

## IMG_4343

Program Architecture

- Policy
- Program overview deck
- Welcome packet
- Methodology
    - Risk selection criteria
- Process diagrams
- Procedures manual
- Message templates
- System of record
- Reporting
- Metrics, KPIs, and KRIs
- Assessment

## IMG_4344

Policy Considerations

- Application security standard
- Secure coding training

- Risk based testing
    - Static code scan (SAST)
        - for all applications
    - Dynamic scans (DAST)
        - for applications with sensitive data
    - Software composition analysis (SCA)
        - for applications with sensitive data
    - Penetration testing
        - applications with sensitive data _and_ public/internet exposed

- Scans must be conducted before each release
- Penetration test annually and with significant change
    - **NOTE:** _This requires the tricky definition, "What is a significant change?"
- Indpendent security testing before a build is released
    - ex: quality assurance or release management
- How code defects are rated from a security perspective
    - process and criteria where that default rating can be overridden
        - Basically, "what are our exceptions to our SDLC approval & release process(es)?"
- Code with high or critical defects cannot be released
- Metrics will be used to track adherence to policy
- Policy exceptions must be documented and approved

## IMG_4345

Application Risk Profile

Risk Exposure

- Confidentiality
- Integrity
- Availability

Available Controls

- Web application firewall
    - not only is it in place, but how is it configured?
- Database activity monitoring
- Developer security toolkit
- Logging framework
- SIEM and SOC monitoring