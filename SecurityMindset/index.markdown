---
layout: tutorial
title:  "The Security Mindset"
next: "SecurityPrinciples"
---
# Don't be evil, but "Think Evil!"

To succeed in securing our applications, we need to learn to think like an attacker.

So as we read and write code (and consider overall system design) ask ourselves:
* What is high value?
* If this data is priviledged, what other paths or layers can I use to access it?
* How can I circumvent this protection mechanism?
* If this layer is protected, can I gain access to a different layer?
* How can I coerce or mislead people into revealing information that will help me break the system?
* What software is exposed that I can exploit (e.g. to plant my own code via buffer overrun)
* What other systems can I exploit to can access to this system? (For example, with password reset functionality that is sent by email, can I gain access to the email or the email account)

Attackers my also not be out so much to gain information, as to disrupt an organization:
* How can I disrupt access to the system for legitimate users?
* How can I destroy /corrupt data (even if I can't read it)?
