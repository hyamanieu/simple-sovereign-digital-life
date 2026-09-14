# /e/OS App Compatibility Notes
*Tested v4.2 on an unlocked Pixel 8 as of September 2026*

---

## WhatsApp
I initially encountered a silent connection error when trying to set it as my primary phone. A temporary workaround was to register it as a secondary device and keep the old phone as primary.

**Solution:** The issue resolved itself a few days later, possibly due to an update.

---

## BoursoBank
As of September 2026, BoursoBank (like many banking apps) uses Play Integrity, which makes it nearly impossible to [install on alternative Android OSes](https://grapheneos.org/usage#banking-apps). [GrapheneOS provides guidance for developers](https://grapheneos.org/articles/attestation-compatibility-guide) to use hardware attestation APIs instead of Google’s locked Play Integrity API.

**Solution:**
- Call the bank to enable SMS-based two-factor authentication
- Use the browser

I mostly use a PC for banking anyway. The app was mainly useful for accessing customer discounts for cinema tickets, which I can do via the browser.

---

## NFC Payment
Google Wallet does not work on /e/OS. Curve Pay is often recommended as an alternative, but it doesn’t work on my Pixel 8.

**Solution:** I use a phone case with a card holder. NFC-enabled ATMs are rare anyway, so this is the better solution.

---
## Galaxy Watch 4
I bought a Galaxy Watch 4 for fall detection (as I commute by bike), and it was the best available option at the time besides the Apple Watch.

Transfer from my old phone to the Pixel 8 failed repeatedly. Resetting the watch and associating it also fails, but later in the process.

**No solution** except buying a Garmin or pairing it with a phone running Google’s Android, which is not a satisfactory option for me.

---
---
## Apps That Worked Without Issues

### Communication
- Telegram, Signal, Facebook Messenger

### Productivity
- Proton Mail, Proton VPN
- Google: Gmail, Calendar, GBoard, Authenticator
- [DAVx5](https://github.com/bitfireAT/davx5-ose): Syncs contacts and calendars with Google and Nextcloud
- Nextcloud: Memories, Notes, Tasks
- KeePass2Android

### Media
- Radio France
- Bandcamp
- Cubic Music
- VLC
- Shokz (headset manager)
- NewPipe

### Health
- Mon Espace Santé
- Compte Ameli
- Doctolib

### Transportation
- SNCF Connect
- CTS

### Other
- Brave
- *free* Telecom
- GitHub
- PayPal
- Kvaesitso


---
---
## Additional Notes

### On Data Privacy
I was surprised how simple it is to spoof your location in /e/OS. By default, it picks Budapest, but this can be changed. Masking your IP address is just as easy.

### Data Leaks
The worst offenders for trackers are:
1. Radio France
2. Decathlon Outdoor
3. The browser (far behind the others)