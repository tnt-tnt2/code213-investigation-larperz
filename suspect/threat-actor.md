# Suspect Dossier – Operation Airport Snooper

**Case ID:** CASE-01  
**Incident:** Operation Airport Snooper  
**Target:** Diplomatic Laptop  
**Attack Vector:** Evil Twin / Rogue Public Wi-Fi Access Point  
**Location:** Houari Boumediene Airport, Algiers

## 1. Suspect Profile

- **Alias:** Airport Shadow
- **Skill:** Pro
- **Motive:** Corporate Espionage / Information Theft

**Explanation:**

The attacker is suspected of being an individual with knowledge of wireless networking and credential theft techniques. The main objective was likely to steal sensitive government information, including confidential diplomatic documents and corporate login credentials.

## 2. Modus Operandi

The attacker deployed an unauthorized wireless access point using a fake network name, `FREE_VIP_AIRPORT_5G`, to imitate a legitimate airport Wi-Fi service.

The diplomatic delegate connected to this open network, believing it was an official hotspot. After connecting, the victim was redirected to a fraudulent login page at `http://192.168.1.1/login.html`, which requested corporate email credentials and a network password.

The attacker could then collect the submitted credentials and intercept unencrypted traffic. Within twenty minutes, the confidential document `Trade_Agreement_Confidential.pdf` appeared on a public paste site.

## 3. Adversary Mistake

The attacker left several important clues that helped investigators identify the suspicious activity:

- **Fake Wi-Fi Network:** The network `FREE_VIP_AIRPORT_5G` was not the official airport network, which was named `Aeroport_Alger_Public`.
- **Fraudulent Login Portal:** The fake login page used an outdated airport logo and an insecure HTTP connection.
- **Physical Evidence:** A witness reported an individual carrying a battery pack connected to a small black directional antenna inside an open shoulder bag.

These clues suggest that the attacker used a portable wireless device to broadcast the fake access point near the VIP lounge.