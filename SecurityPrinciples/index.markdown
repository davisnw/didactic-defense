---
layout: tutorial
title:  "The Security Principles"
---
1. **All user modifiable input is evil**

2. **Prevent Code and Data Confusion** (strategies in order of (my) preference)

    1. Strategy: Separate Command and Data

		* Example: Parameterize Sql Queries
		* Example: Windows Data Execution Prevention
	  
	2. Strategy: Encode data

		* Example: Html encode all data displayed in a web page
		* Example: (for PHP) [mysqli_real_escape_string](http://www.php.net/manual/en/mysqli.real-escape-string.php)
		
    3. Strategy: Allowed "Safe" input list
	
		* Example: only allowing characters a-z and 1-9 in a user input field
		
    4. Strategy: Disallowed "Dangerous" input list
	
		* Example: Disallowing the single quote in a name field (sorry [Chief O'Brien](http://en.wikipedia.org/wiki/Miles_O%27Brien_%28Star_Trek%29)).
		
	5. Corollary: **What is data in one context may be code in another**
		
		* Strategy: Know your execution context
		

3. **Defend the Premise**

	1. Strategy: Understand your assumptions
	2. Corollary: **Ensure secrets are not guessable**
	
		1. Strategy: Use cryptographically strong randomness.
		
6. **Abstractions are Leaky**

	1. Strategy: Understand the fundamental operating principles of your abstraction
	
7. **Vulnerabilities can combine**

8. **Know the difference between Encryption and Encoding**

9. **Good algorithms can be subverted by bad implementations**

	1. Srategy: Use trusted cryptographic implementations
	
10. **Consider authentication and authorization**

11. **Consider Pyschology**

    1. Strategy: Help your users know when they are being spoofed.

		* Example: "SiteKey" functionality
		* Example: Tell your users what you will and won't do (e.g. we will never ask for your password over the phone or in an email)
		* Example: Use SSL with a cert issued by a CA.
		* Example: Avoid blind redirects.

12. **Know (and defend) your trust entry points**

13. **The Same Data Can Have Different Representations**

	1. Strategy: Canonicalize before making a security decision
	
14. 

Canonicalization?

Principles vs classification?

* Priviledge Escalation
* Side-channel
* Replay