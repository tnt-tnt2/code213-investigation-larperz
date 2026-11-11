# Digital Evidence – Operation Airport Snooper

**Case ID:** CASE-01  
**Investigation Unit:** Code213 Cyber Investigation Squad  
**Role:** Role 3 – Evidence Specialist  
**Branch:** `feature/airport-evidence`  
**Target:** Diplomatic Laptop – Houari Boumediene Airport, Algiers  
**Attack Vector:** Evil Twin / Rogue Wi-Fi Access Point

---

## 1. Attack Vector Analysis

The incident involved an unauthorized wireless network named `FREE_VIP_AIRPORT_5G`, designed to imitate a legitimate airport Wi-Fi hotspot.

The victim, a senior international trade delegate, connected to this open network while waiting in the Terminal 1 VIP lounge at 14:15 on Sunday.

The official airport network, `Aeroport_Alger_Public`, required SMS verification. However, the suspicious network required no password and provided maximum signal strength in the VIP seating area.

This suggests that the attacker deployed a rogue wireless access point to attract nearby users and redirect them to a fraudulent login portal.

Within twenty minutes of connecting, a confidential government briefing PDF named `Trade_Agreement_Confidential.pdf` appeared on a public paste site.

**Assessment:** The available evidence strongly suggests an Evil Twin attack that exposed the victim to credential theft and potential data interception.

## 2. Fake Login Portal Investigation

**Suspicious URL:** `http://192.168.1.1/login.html`

The victim's browser was automatically redirected to a suspicious login page after connecting to the fake Wi-Fi network.

The portal displayed an outdated airport logo and requested:
- Corporate email address.
- Network password.

### Suspicious characteristics

1. **Insecure HTTP connection:** The portal used HTTP instead of HTTPS, providing no transport encryption.
2. **Outdated airport branding:** The logo did not match the appearance of the legitimate airport service.
3. **Credential harvesting attempt:** The page requested corporate authentication information through an untrusted network.
4. **Unexpected redirection:** The browser was redirected to a private IP address rather than an authenticated official airport service.

**Assessment:** The portal was likely designed to impersonate the airport's legitimate authentication service and collect corporate credentials.

## 3. Physical Witness Statement Analysis

**Evidence ID:** EV-03  
**Source:** Airport Security Report

The airport security team reported an individual sitting near the gate with:
- A battery pack.
- A small black directional antenna.
- An open shoulder bag containing the equipment.

### Analysis

The equipment described is consistent with a possible portable wireless setup.

The battery pack could provide independent power, while the directional antenna could be associated with wireless communication equipment.

The individual's location near the gate is relevant because the suspicious Wi-Fi network had maximum signal strength in the VIP seating zone.

However, the witness statement alone does not establish that the individual operated the rogue access point.

**Assessment:** This is a significant investigative lead, but additional forensic evidence is required to identify the responsible individual.

## 4. Three Ignored Security Red Flags

1. **Suspicious Wi-Fi network:** `FREE_VIP_AIRPORT_5G` required no password, unlike the official airport network, which required SMS verification.

2. **Fake login portal:** The victim was redirected to an HTTP page displaying an outdated airport logo and requesting corporate credentials.

3. **Unusual physical equipment:** Airport security observed an individual carrying a battery pack connected to a small directional antenna near the gate.

## 5. Evidence Ledger

| ID | Artifact | Severity |
|---|---|---|
| EV-01 | Network comparison: suspicious open Wi-Fi network impersonating the official airport hotspot. | Critical |
| EV-02 | Fake login portal: insecure HTTP page requesting corporate credentials. | Critical |
| EV-03 | Witness statement: individual observed carrying a battery pack and directional antenna. | High |

## 6. Security Impact

The incident potentially affected:

- **Confidentiality:** A confidential diplomatic briefing document was exposed publicly.
- **Credential security:** Corporate login information may have been collected through the fraudulent portal.
- **Network security:** The victim connected to an unauthorized wireless network.
- **Organizational trust:** The incident could compromise confidence in the security of official communications.

## 7. Final Investigation Conclusion

Based on the collected evidence, Operation Airport Snooper is consistent with an Evil Twin / Rogue Access Point attack.

The attacker appears to have impersonated a legitimate airport wireless network using a fake SSID and fraudulent login portal. The victim connected to the suspicious network and was redirected to a deceptive HTTP authentication page requesting corporate credentials.

The physical witness report provides an additional investigative lead, although it does not independently prove who operated the equipment.

The exposure of `Trade_Agreement_Confidential.pdf` demonstrates a serious confidentiality incident.

**Final Verdict:** HIGH-CONFIDENCE SUSPECTED ROGUE WI-FI ATTACK.

**Investigation Status:** Evidence documented – further forensic verification required.