# Incoming & Outgoing Domains & IPs

## Outgoing IP Addresses

Rewst uses static NAT Gateway IPs for outbound connections from our services hosted in AWS. These IPs should be included in any necessary allow lists for outbound connections:

* North America: `3.139.170.31`
* Europe: `18.171.196.2`

## Hostnames with Dynamic IPs

For the following services, Rewst employs application load balancers, resulting in dynamic IP addresses. We recommend using DNS names when adding these services to your allow list.

### North America

* `app.rewst.io`: Front-end web application for user logins.
* `engine.rewst.io`: Back-end application handling workflow execution, including webhooks.
* `api.rewst.io`: API for app and engine communication.

### Europe

* `app.eu.rewst.io`: Front-end web application for user logins.
* `engine.eu.rewst.io`: Back-end application handling workflow execution, including webhooks.
* `api.eu.rewst.io`: API for app and engine communication.

## Wildcard Domains

Rewst customers may create subdomains (`*.rew.st>`) to host their apps. These should also be considered in your allow lists based on your integration needs.
