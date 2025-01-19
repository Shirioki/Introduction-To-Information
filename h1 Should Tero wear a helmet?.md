# h1 Should Tero wear a helmet?

## What is Threat Modeling?

Threat modeling is a process to analyze systems to identify security and privacy risks. This process goes through four key questions
 - what is being worked on?
 - what can go wrong?
 - how to address the risks?
 - whether the effort was sufficient?

Pros of threat modeling is that it helps recognize potential system failures, development and maintenance phases. It also encourages teams to "think like an attacker" fostering greater security awareness.

 - Commonly used techniques include Data Flow Diagrams (DFDs) and the STRIDE framework.

## Podcast episode Player Cheater Developer Spy

- Episode discussees the creation of cheats for video games and how they impact gaming industry
- Cheat developers exploited vulnerabilities in games, creating programs for players to gain unfair advantages.
- Cheat creators made considerable profits from this.
- Both sides still on this day adapt and evolve their tactics to outsmart each other.

## a) Security hygiene

- Using unique passwords for each account.
- Two-factor authentication.
- Updating the software and OS
- Back up data
- Encrypting data
- Antivirus
- Using public Wi-Fi with caution
- Secure your devices with password or biometric authentication.
- Be aware of phishing and scams and avoid clicking suspicious links.

## b) Imaginary Company: PlayGachaGames

### (1) What are we working on?

- Assets: Game code, Player accounts, user data
- Priotization: Player account security, in-game currency and game code
- Business Model: PlayGacha Games is a gacha online multiplayer mobilegames with a marketplace for in-game purchases.
- System Diagram: Game client -> Game server -> Payment gateway -> Player database.
- Customer Touchpoints: Game platform, in-game store, support portal.

### (2) What can go wrong?
- STRIDE
  - Fake accounts
  - Cheating codes and tools
  - Leakage of personal or financial info
  - Preventing players from accessing the game

- Risk Prioritization:
  - High: Account theft (High probability, High impact)
  - Medium: Cheating (Moderate probability, High impactt)
  - Low: Server attacks (Low probability, High impact)

- Targeted Threats:
  - Cybercriminals aiming for account theft
 
### (3) What are we going to do about it?
- Two-factor authentication for player accounts.
- Implement anti-cheat mechanisms and frequent game patch updates.
- Secure player transactions with encryption and fraud detection.

### (4) Did we do a good enough job?
- Monthly security audits.
- Continuous monitoring of player reports for suspicious activities.
- Customeer surveys.
- Ongoing updates.
- Company staff lectures about phishing and scams.

## References
- Karvinen 2025 - Information security at https://terokarvinen.com/information-security/#h1-should-tero-wear-a-helmet
- Braiterman et al 2020: Threat modeling manifesto at https://www.threatmodelingmanifesto.org
- OWASP CheatSheets Series Team 2021: Threat Modeling Cheat Sheet at https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html
- EP 115: PLAYER CHEATER DEVELOPER SPY at https://darknetdiaries.com/episode/115/
- GPT prompts for brainstorming, ideation and reference:
