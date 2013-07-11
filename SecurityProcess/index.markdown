---
layout: tutorial
title:  "The Security Process"
---
# Security: A process, not a product

Security is a process that flows all the way from requirements to development to deployment to maintenance, and as long as the application is running.

 * In *Requirements* authentication needs and authorization granularity are defined.
 * In *Development*, developers must be aware not to introduce exploitable vulnerabilities
 * In *Deployment* networks must be properly configured, patches must be applied, encryption keys must be managed.
 * In *Maintenance* code changes must be secure, and an eye should be kept open for previously undiscovered vulnerabilities.  New information form framework vendors may be brought to light that require patches (and possibly corresponding code changes).  Operating system patches and other third party patches must be applied in a timely fashion.
 
Security should be considered in all these phases.  A process that tries to bolt security on at the end is likely to fail:
* Schedule pressures at the end of the project will likely compress the security review out of the schedule
* It may be discovered that core architectural constructs do not meet the security requirements, which would then require massive efforts to refactor.

## An example: process missing, product gone awry
I was once involved in a case (of which all parties shall remain anonymous!) where the security product (an antivirus solution) was actually used to compromise all the computers in the network. The clever attacker exploited a vulnerability in the antivirus definition updates process to push out a virus to all machines when they connected to the central server to get virus definition updates.  It then disabled the automatic update to prevent the machines from later receiving a definition update that would remove it.  The whole scenario could have been avoided if an existing patch for the antivirus solution had been applied in a timely fashion.

# The Place of Products
This is not to say that products have no place.  Indeed, every security process should consider what products it would benefit from, such as:
* Network Firewalls
* Network Monitoring
* Intrusion Detection 
* Antivirus
* Email scanning
* Valid SSL Certificates
* Static Analysis Tools
* Fuzzers
* etc

# Goals of a Good Security Process
The security process should have at its core to primary goals:
1. Prevent Security Breaches
2. Detect Security Breaches

# Aspects of a Good Security Process
Has **Proactive**, **Reactive** components.

*Proactive* components include such things as building in security from the start, review of code at commit, third party evaluation of code on a periodic basis, maintaining audit logs, having a patch paln, etc.

*Reactive* components include such things as having a plan in place if a vulnerability is exploited, having a plan to timely address issues brought to your attention, etc.

# The Role of Psychology
Any Security Process should give some consideration to the human aspect.  

Frequently, your end users will not care about security until something bad happens - they just want to get their job done. Therefore, we should strive to make it as easy as possible to do things in a secure way, and be aware of unintended consequences.  For example, an extreme password complexity requirement may lead employees to put a sticky note on the monitor with the password.

We should also remember that training plays a role.  Building a secure system does not necessarily make a system harder to use - but there are often unavoidable ease-of-use/security tradeoffs.  Training end users in these areas (and to some extent explaining the reason for them) can help ease acceptance.

Training also includes making employees more aware of things such as
* phishing attacks
* name dropping - using the name of a well-known person in the organization to get an employee to do something they might otherwise not do, e.g. "Bob said it was ok to..."
* impersonation - techniques by which someone claims to be someone else.
* being "helpful"

A word on that last bullet - in a customer service organization has as its goal to make its customers happy.  Customer service representatives might therefore be predisposed to release information more readily in response to customer pressure.  Where such information is priviledged, training must be provided to help the representative ensure that they have obtained proper authorization and identification of the person before releasing the information.  Properly designed software can assist this process - poorly designed software can hinder it.

# The Microsoft Security Development Lifecycle
Microsoft has documented its own Security Development Lifecycle and also provided tools to aid in the implementation of it.  It is one example of a mature development methodology that takes security into account.

See: [Microsoft Security Development Lifecyle](http://www.microsoft.com/security/sdl/default.aspx)
