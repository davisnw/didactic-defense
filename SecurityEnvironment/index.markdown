---
layout: tutorial
title:  "The Security Environment"
---

[![Security Environment](../images/SecurityEnvironment.svg)](../images/SecurityEnvironment.svg)

# Security From the Inside Out

Security can be compromised at many points in the process.

1. We start at the innermost circle with hardware components and peripherals.
  * Harddrives contain "data at rest"
  * Network hardware, USB devices and printers can be used to transfer data to outer layers.
  * Microphones and webcams can be used to record potentially sensitive information
  * Hardware chips from malicious manufactures could route data elsewhere surreptitiously
  * Hardware based keystroke loggers could intercept usernames and passwords, and can be easily and quickly installed at the peripheral interface
2. Moving one circle out, we have the software consisting of the operating system, server-side framework code, and other installed software
  * Operating systems and other software needs to be kept up to date as security updates are released
  * Malicious software needs to be prevented from installing or detected and removed.
3. Servers and client machines such as dekstops, laptops, and smart phones wrap the inner layers.
4. The network serves as the interface between people and servers (via client machines).
  * The network consists of routers, switches, and wired/wireless transmission.
  * Note that wireless transmission spans several circles.  Wireless transmissions are not easily prevented from physically escaping the building.
5. Many different types of people, from computer-technical to computer illiterate access the system.
  * People can be targeted with psychologically based attacks over multiple mediums, including phone, email, and in person (for the more daring crminials).
  * Visitors, vendors, customers and unauthorized employees may gain access via physical elements, such as printouts, unlocked computers, shoulder surfing, or eavesdropping.
6. Here we see the physical boundary of the building.
  * Entry and exit ways to server rooms, etc 
  * May be monitored via security cameras
  * "Drive by" access to "leaky" wifi access may be possible
7. Moving from the internal network to the external network
  * The network firewall needs to be configured to properly make the distinction between the internal network and the external network.
  * The external web server is accessible over the public internet
8. Via the internet:
  * "Evil Nerd" may attempt to gain unauthorized access
  * Cloud services may communicate back and forth all the way to the internal network in order to fulfill business services
  * External users access the site
  * Other machines may autmoatically communicate with the site for both legitimate and malicious purposes.

# Our Focus
Many of the above environmental factors that affect the security of the entire system are outside the direct control of the web application itself.

However, it is important to have an understanding of the system as a whole to provide a secure system.  For example, by examining all the layers we might know that we need to:
 * Provide physical security to server hardware
 * Consider how to secure "data at rest"
 * Consider how internal network traffic might be compromised
 * Provide training to employees to lessen the risk of psychological attacks.
 * Configure network security, including authentication and authorization protocols and traffic encryption.
 * Monitor visitors and vendors to ensure they do not gain access to secure areas.
 * Be extra careful with wireless network configuration - ensure proper protocols are in place to prevent data snooping and unauthorized access
 * Ensure the deployment of our systems is done in a secure manner, so as not to leak encryption private keys etc.
 * etc.

Our intent in the remainder of this tour is to narrow our focus to securing the web application at code level.