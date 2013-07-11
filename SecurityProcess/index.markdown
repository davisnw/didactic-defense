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
I was once involved in a case (of which all parties shall remain anonymous!) where the security product (an antivirus solution) was actually used to compromise all the computers in the network. The clever attacker exploited a vulnerability in the antivirus definition updates process to push out a virus to all machines when they connected to the central server to get virus definition updates.  It then disabled the automatic update to prevent the machines from later receiving a definition update that would remove it.  The whole scenario could have been avoided if a patch for the antivirus solution had been applied in a timely fashion.