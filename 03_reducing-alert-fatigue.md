# Reducing Alert Fatigue with Container Scans: Correlate, Prioritize, and Filter Based on Usage

Developers want to pull their container image, as fast as they can, from the most convenient place.

Security has to make sure the right checks and balances are in place to make it happen well.

(From: DeepFactor)

## Alert Fatigue

- what does AppSec 2.0 look like?
    - we have an open concern about things being loaded into memory
    - this is what has been missing from traditional AppSec scans
        - "shift left and *correlate* with the right"

## Strategies for Dealing with the Fatigue

- Reachability
    - can the app be reached
- Exploitability
    - can the vuln be exploited
- Applicability
    - is the vuln even for what we're using
- Usage
    - sure your package is vulnerable, but is your vulnerable package loaded into memory?
- CVSS score

All of these together give you enough signal to actually highlight what needs to practically be fixed.

A typical SCA scan still requires *a lot* of research because you don't have this context captured along with your vulnerable components scan report. Knowing if something is "Critical" isn't enough.

## An Example

"Bank of Anthos", an example app from GCP

- demo: we have 626 vulnerabilities
    - we need to measure what is our actual risk?
    - we can't waste time tackling by severity

- from there, filtering into what is "loaded" is that next level of good filtering on vulns that we need
