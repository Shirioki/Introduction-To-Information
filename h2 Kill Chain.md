## 1. Introduction

- Advanced Persistent Threats (APT) target sensitive information for economic or military purposes
- Traditional defenses like anti-virus aren't effective against APTs due to their sophistication
- APT involve long-term, evasive attacks requiring advanced detection and response
- The kill chain model analyzes each phase of an intrusion to block it at multiple stages
- Intelligence-driven defense helps anticipate threats and improves resilience against future attacks
- The paper introduces this approach and applies it to a real-world case study to demonstrate effectiveness

## 2. Related Work

- The U.S. Department of Defense defines a kill chain with the stages: find, fix, track, target, engage, and assess. This model is used to identify gaps in surveillance capabilities and improve system development
- Improvised Explosive Device (IED) attack
- The U.S. Army describes a seven-step terrorist operational planning cycle, which is used to assess terrorist groups intent and capabilities. This model helps with antiterrorism efforts on military installations
- ABSAC Framework: A model aligning countermeasures with the phases of an attack, focusing more on post-compromise actions

## 3. Intelligence-driven Computer Network Defense

### 3.1 Indicators and the Indicator Life Cycle
- Intelligence-driven Computer Network Defense (CND)
- a strategy that helps protect networks from cyber threats. Uses intelligence to better understand and defend against attackers
- CND is a continuous process that uses indicators (signals or pieces of information) to detect and respond to new attacks
- goal is to make defenses more resilient by using a kill chain model
- If defenders can disrupt attack earlier, it increases the adversary costs and makes it harder for attacker to succeed
- defenders can have the upper hand by acting faster than attackers adaptation
- Indicators are pieces of information that help identify attacks. They come in 3 types:
    - Atomic: Simple, indivisible facts like IP addresses or email addresses
    - Computed: Derived data like hash values or patterns from the attack
    - Behavioral: complex patterns combining atomic and computed indicators that describe how an attack is unfolding
- The Indicator Life Cycle used to track and understand attacks. Helps improve defenses

### 3.2 - 3.5 Intrusion Kill Chain

-  Intrusion Kill Chain, a model used to understand and defend against cyberattacks by breaking them down into phases
-  A kill chain is a process used to target and engage attackers
-  if any phase of the chain is distrupted, the entire process is halted
-  Phases of Intrusion Kill Chain:
    - Reconnaissance: Attackers gather information on targets (like emails or technologies)
    - Weaponization: Attackers create a payload (malware) to exploit vulnerabilities
    - Delivery: The weaponized payload is transmitted (email, USB)
    - Exploitation: The payload triggers an exploit, often taking advantage of vulnerabilities in software or human error
    - Installation: A backdoor or remote access tool is installed to maintain control
    - Command and Control (C2): Attackers connect to compromised systems to control them
    - Actions on Objectives: After all the previous phases, attackers achieve their goal (usually data theft, system damage, or further       attacks on other systems).
 
- The course of action matrix helps determine defensive actions. Defense can range from detecting attacks to denying exploitation
- The goal of defense is to increase resilience ( making it harder for attackers to succeed under same tools or method)
- Adaptability is really important. Defenders should constantly update their defenses based on new indicators and evolve faster than 
  attackers.
- It is important to analyze intrusions because it helps you identify which phases were successful and which defenses worked
- This help preparing for future attacks and block them earlier.
- Campaign analysis helps defenders understand the intent of attackers, making it easier to prioritize security efforts for high-risk 
  targets

  ## 4 Case Study

  ### 4.1 Intrusion Attempt 1

  -In March 2009, Lockheed Martin Computer Incident Response Team detected a targeted malicious email attack sent to 
   five individuals about an AIAA conference, containing a weaponized PDF that exploited a zero-day vulnerability in Adobe Acrobat to 
   install a backdoor, enabling attackers to establish a Command and Control (C2) channel

      - Reconnaissance : Email was crafted to it seemed legitimate. Was sent to five people who had received similar malicious emails           in the past
      - Weaponization : A benign PDF and A malicious executable file to install the backdoor
      - The malicious executable was encrypted with an 8-bit key and placed in the victim's system under C:\Documents and Settings\             [username]\Local Settings\fssm32.exe.
      - Opening the PDF would exploit the vulnerability to decrypt and execute the backdoor, which then established communication with          the attacker's C2 server
      - Backdoor send heartbeat data to attacker's server via HTTP requests
      
