# Containers/Docker (Talk 1)

- container workloads are single purpose
    - this is good to keep in mind for design
- *mostly* immutable
- *supposed to be* ephemeral

- Data
    - should be all externally mounted

- Deployment of workloads is often orchestrated (i.e. Kubernetes)
    - orchestration control plane scales and re-deploys deployments as needed
    - be mindful of private and public container registries here


## Implementation Options

- which images to scan
    - pipeline vs. registry vs. deployed inventory
    - scan at PRs
    - scan at build time as "early warning"
    - scanning in registry isn't effective
        - this is too much all at once
        - not all of this makes it to prod either


## Work with images list

- get a cluster inventory out of K8s
- multiple versions of the same images might be deployed at the same time, too
- scanners aren't always good at keeping track of versions in registries
- you still may want to centralize where you scan though
    - so you can consolidate where this is happening, and keeping track of things
- relying on "registry scans" from 3rd party vendors (i.e. AWS) are typically less reliable with "not as good" results
- tech to lookup: "pull through cache"


## Scanner Capabilities

- scanners use binary decomposition to identify dependencies
- this is why the CVE database for the scanner needs to get updated frequently
    - how frequently do they update it, or what do they use?
    - updates within a day of a 0-day? fine. 10 days? too long.


## Triage

- we may want to do some light validation on the scan results before go head off to fix things
- keep track of "risk accepted" ones, too
- watch for these on subsequent scans, too
- "How long of a list of exceptions do we want to manage?" before we start forcing developers to update things
- ***Remember, we're scanning container images** not the actual running containers
    - you may have 1000s of containers spun up from a single image
    - so, it can become ineffective to point a scanner at a running container
    - ...unless something else is running "incorreectly", lol
- As you're managing this, keep in mind, there may be different teams maintaining different parts of these images
    - Summary: it isn't always 1 team, 1 image
    - How are you mapping image layers to a team(s)?
        - if you're at this scale, then you're at the engineering and infosec level that you have people on "both sides" that understand image dependencies
        - so, with this, there is typically some "village knowledge" of who to go to

### Get software engineers to mitigate vulnerabilities

- make the pipeline the enforcer?
    - build checks
    - admission checks
        - ex: checking digital signatures before deployment
        - ex: no deployment if last-minute scanner detects a vuln
    - these can be very aggressive, and potentially cause availability issues
- or...create tickets
    - sequence this out into actionable work


## Scanner, value-add

- if your scanner provides an upgrade path, that's excellent
    - min library version to upgrade to
    - integration with repo scanners might enable PR integrations


## Validating fixes

- self-service option for developers to validate updated images before deployment
    - this can be better developers to "just do something in-flow" (like a unit test) rather than go back to InfoSec to ask
- back to inventory of currently deployed image versions
    - is everything gone?


## Compliance Reporting

- reporting on vulnerabilities
    - [insert pic]
    - beware of when a vuln is difficult/complex to exploit in your environment. Often a scanner doesn't have this context when labeling a vuln with a criticality.

- making a ticket per image, has been the best way (for this team who is speaking)
    - because it maintains the context of the vulnerability
    - without over-generalizing, or over specifying, the context of the vulnerability


## Pitfalls

- [insert pic]
- [insert pic]