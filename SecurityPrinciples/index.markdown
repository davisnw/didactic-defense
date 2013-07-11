---
layout: tutorial
title:  "The Security Principles"
next: VulnerabilityCatalog
---
1. **All user modifiable input is evil** (which means "handle with extreme caution").
	It is not that these things should be avoided, just that they must be handled correctly.
	* Example: Http Headers - **Evil!**
	* Example: Javascript Validation - **Evil!** (javascript validation is easily circumvented. Treat it as a UI nicety, but do the final checks on the server side!)
	* Example: Http Post form values - **Evil!**
	* Example: Url query string parameters - **Evil!**
	* Example: Cookies - **Evil!**
	* Example: File upload - **Evil!**
	* Example: Data in a database - **Evil!**

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
		2. Strategy: Always salt your hash [Salted Password Hashing - Doing it Right](http://crackstation.net/hashing-security.htm)
		
4. **Abstractions are Leaky**

	1. Strategy: Understand the fundamental operating principles of your abstraction
	
5. **Vulnerabilities can combine**

6. **Know the difference between Encryption and Encoding**

7. **Good algorithms can be subverted by bad implementations**

	1. Srategy: Use trusted cryptographic implementations
	
8. **Consider authentication and authorization**

9. **Consider Pyschology**

    1. Strategy: Help your users know when they are being spoofed.

		* Example: "SiteKey" functionality
		* Example: Tell your users what you will and won't do (e.g. we will never ask for your password over the phone or in an email)
		* Example: Use SSL with a cert issued by a CA.
		* Example: Avoid blind redirects.

10. **Know (and defend) your trust entry points**

11. **The Same Data Can Have Different Representations**

	1. Strategy: Canonicalize before making a security decision
	
12. **Encrypted data can still be used to attack a system**

	1. Strategy: Use [Nonces](http://en.wikipedia.org/wiki/Cryptographic_nonce) to prevent replay
	2. Strategy: Use reconciliation to detect replay (e.g. in financial systems)
	3. Strategy: Use digital signatures to verify identity