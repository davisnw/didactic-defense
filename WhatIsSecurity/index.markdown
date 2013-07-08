---
layout: tutorial
title:  "What is Security?"
next: SecurityStakeholders
---

# The "Classic 3" - <abbr title="Confidentiality, Integrity, Availability">CIA</abbr>

<dl class="acronym">
	<dt>Confidentiality</dt>
	<dd>Only authorized people can access the information.</dd>
	
	<dt>Integrity</dt>
	<dd>The information is correct, and cannot be corrupted by malicious actors.  It may also include the concept of "origin" or "source" integrity - that is, can we verify that the information came from a specific source and has not been tampered with.  The concept of "non-repudiation" also falls under the Integrity category.</dd>
	
	<dt>Availability</dt>
	<dd>The information is available to authorized users.</dd>
</dl>

# Physical Safety
In terms of the "classic 3" Physical Safety might perhaps fall under <abbr title="Integrity">I</abbr>.  However it deserves special mention for some systems.  For example, in an insulin pump, you don't want an unauthorized actor to remotely change the dosage!

# Conflicts
These attributes can sometimes be "in conflict", or require "balancing" between the strength of the different attributes.

For example, in an electronic voting system, you want both anonymity(<abbr title="Confidentiality">C</abbr>) and [non-repudiation](http://en.wikipedia.org/wiki/Non-repudiation)(<abbr title="Integrity">I</abbr>).

Also, sometimes different groups of people will view the same attribute of "security" in different ways.  For example, in the recent wikileaks/NSA saga, wikileaks might value anonymity(<abbr title="Confidentiality">C</abbr>) as an attribute of security as a way to protect its members and sources from reprisal.  However, the NSA would take the same attribute of anonymity, and view it as a detriment to security, since it makes it more difficult for them to prevent future releases of classified information(<abbr title="Confidentiality">C</abbr>).
