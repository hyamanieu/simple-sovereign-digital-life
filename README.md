# A simple sovereign digital life

*Reclaiming my photos, my documents, my passwords, and my phone without becoming an IT engineer.*

I wanted my data back. Simply. No stack to maintain, no engineering degree required, just my files, my memories, my documents under my control. 

The **push**: Google knows pretty much everything about me. My e-mails, my positions, my pictures, [my keystrokes](https://play.google.com/store/apps/details?id=com.google.android.inputmethod.latin) and maybe even [my DNA](https://en.wikipedia.org/wiki/Anne_Wojcicki). 

The **pull** was the upcoming payment deadlines for my Google One and LastPass Family contracts, totaling 75€/year. Taking pictures on your Android phone means, by default, automatic sync to Google Photos. Your storage only grows, and you quickly hit the 15GB free-tier limit. If you delete a picture from Google Photos, it's also deleted from your phone!

The **icing on the cake** is the set of US surveillance laws like the CLOUD Act and FISA, which grant authorities access to data held by American companies.

But really, it was about ownership: our data is a reflection of our lives, and I wanted to decide who holds it.

This repository documents the choices I made, the trade-offs I encountered, and the concrete steps I took to move away from American corporate cloud services. It is a work in progress, even small steps count, and it *is* feasible 🙌.

## Three pillars

**Simple**: Simplicity was non-negotiable. Managed Nextcloud is nearly as easy to use as Google Drive or Google Photos. Because Nextcloud is open-source, the community has developed tools like [face recognition](https://apps.nextcloud.com/apps/memories).

**Sovereign**: My data now lives on servers in Europe, under European jurisdiction. No foreign government can compel disclosure through local law.
I also use encryption to ensure the hosting company cannot access my data.

**Digital Life**: 20 years of shared family photos, documents, messages, and letters. Our data tells the story of our lives. It can be used against us, yet we cannot live without it. Sovereignty means keeping that story ours.

## My setup

### Overview

| Purpose           | Tool           | Provider                               | Approx. Cost | Replaces |
|-------------------|----------------|----------------------------------------|--------------|----------|
| Cloud & Photos    | [Nextcloud](https://nextcloud.com)      |  [Hetzner's Storage Share (DE)](https://www.hetzner.com) | ~5€/month | Google Drive & Photos / Dropbox
| Passwords         | [KeePassXC](https://keepassxc.org) (desktop + browser with Nextcloud sync)<br>[Keepass2Android](https://github.com/PhilippC/keepass2android) (smartphone)<br>[Tusk](https://github.com/subdavis/Tusk) (desktop without Nextcloud) | Sync via Nextcloud | Free | LastPass |
| Mobile OS         | [/e/OS](https://e.foundation)         | /e/ Foundation | ~340€ (reconditioned Pixel 8) | Google's Android |


### Why Nextcloud?

I was exploring these other alternatives:
- [pCloud](https://www.pcloud.com): this is the cheapest solution in terms of euros per TB of storage, particularly with their lifelong contracts often on discount. It also enables sharing of data with other pCloud users (even on free versions), it is simple to enable sync on your smartphones, and it seems relatively easy to use KeePass clients on files synced with pCloud. I decided not to use it because they don't run third-party security audits. Coupled with the very low price, it sounds very sketchy.
- [Proton Suite](https://proton.me): this is the strongest candidate. Hosted in Switzerland, it has regular third-party audits and offers a wide range of services (email, VPN, password management, and 500GB of storage). It is also simple to use on your smartphone for syncing. I could not test whether non-paying users could access shared folders of paying users, but I believe they can. This is also the priciest: 120€/year.

I picked [Nextcloud](https://nextcloud.com) hosted by [Hetzner](https://www.hetzner.com) in Germany commercialized under the name [Storage Share](https://www.hetzner.com/storage/storage-share/). It is a bit more expensive than pCloud, but the contract is very flexible as it can be stopped at any time. As it uses Nextcloud, an open-source software, development is mostly done, reviewed, and audited by third parties. This also means that other businesses using Nextcloud contribute to its implementation, and all businesses (and users!) benefit. Some cloud providers don't even mention that they are powered by Nextcloud, as if it were just an afterthought like most online services (including Microsoft's) being powered by Linux. I believe this is why there are so many features and add-ons.

Nextcloud enables either encryption at the root or end-to-end encryption (E2EE) for specific folders, meaning Hetzner cannot access the data even if it wanted to. I use E2EE only for specific folders because customer service can help with unencrypted data, and they are very responsive. They deserve five stars! ⭐⭐⭐⭐⭐

Nextcloud enables all users, no matter the host, to access shared data and many services, thanks to [federated IDs](https://nextcloud.com/blog/federation-a-foundational-concept-for-digital-sovereignty/). It is the first time I've seen a widely used cloud service that is truly decentralized.

What does this mean for you? If Hetzner decides to double its cost or goes bankrupt, you can switch to another host. If Google and LastPass do the same (which they have in many cases), well, you have to bank or a lot more work awaits you to switch.

Some of the services I have tried or I use actively:
- Photos, [Memories](https://apps.nextcloud.com/apps/memories) and [Recognize](https://apps.nextcloud.com/apps/recognize) to store, share, and classify my pictures.
I was impressed by how quickly Recognize processed all my pictures, even on Hetzner's cheap hosting machine. The default classifier (i.e., face recognition) is not as good as Google's, but it does a very good job.
- [Tasks](https://apps.nextcloud.com/apps/tasks) and [Notes](https://apps.nextcloud.com/apps/notes): I used to use Google Keep. I don't need it anymore. It works well in a browser and on Android apps.
- [Passwords](https://apps.nextcloud.com/apps/passwords): I don't use it since I chose KeePass, but it works.
- [Talk](https://apps.nextcloud.com/apps/spreed): this was unexpected, but now I can organize meetings directly from my Nextcloud instance.

It also offers an office suite.

### Why KeePass?

Nextcloud Passwords is great, but I wanted to easily store my password file without relying on an online service.

KeePass is a free, open-source, file-based password manager. Storing my KeePass database file on Nextcloud Files means I can sync it across all my devices, but it also means I can still access it when Nextcloud is down. I don't believe this is the case with Nextcloud Passwords.

Besides, KeePass has existed for a very long time and is thoroughly tested, so I trust it more.

Several KeePass files can be used and are easy to manage with the various clients, so you can decide which files to share and with whom. The files can be considered as *collections* or *folders* in other password managers.

### Why /e/OS?

I picked /e/OS over other alternatives like GrapheneOS or LineageOS simply because it focuses on simplicity and accessibility, and I can still use some Google services I haven't moved away from yet. To draw a parallel, /e/OS is to the mobile world what Ubuntu is to the PC.

[A few things don't work](./e_os_apps.md), but they are not mandatory to me now. However, I have hesitated switching back to Google's Android due to banking apps and my smart watch. Boursorama provided me with an alternative, so that's fine. The smart watch is still in my mind though.

## How to begin

If you are inspired to start your own journey, here is a practical path:

- **Try Nextcloud first**: Many European providers offer free trials. It's the simplest move you can make and it has the biggest impact. **[It's the 20% of effort that yields 80% of the results](https://en.wikipedia.org/wiki/Pareto_principle)**. [Murena Workspace](https://murena.com/fr/workspace/) built by the people behind /e/OS is also powered by Nextcloud. Upload a few folders, link your phone (including iOS or Android), and see how it feels. Budget a few euros per month if you need more than 10GB of storage.
- **Then change your password manager**: 
  - Export from your current manager and import into KeePassXC. This takes an evening, costs nothing, and provides immediate independence from LastPass. Syncing across devices does require some work, though. 
  - Alternatively, if you are already trying Nextcloud, there is a Nextcloud app for password management with plugins for all standard browsers. [See their blog post](https://nextcloud.com/blog/password-managers-for-nextcloud/).  
- If simplicity concerns you more than money or centralization, just [subscribe to the Proton Suite](https://proton.me). The [Proton Foundation](https://proton.me/foundation) is faring well as far as I know.
- **Explore /e/OS**: this is the trickiest part and presents the most issues (see next section). /e/OS offers the largest number of compatible devices. Testing it means erasing all data from your phone, and only if it is [on the list](https://doc.e.foundation/devices/). Ideally, you have an old compatible phone to try out before moving on completely.


## Honest feedback

No tool is perfect. Here is what hurts:

- **KeePass**: KeePassXC works really well. However, for Keepass2Android and Tusk, the WebDAV protocol is used, and it is advised to create an extra Nextcloud login to ensure your entire files aren't accessible. It is a bit cumbersome additional work for the smartphone app, but it works well. However, with Tusk, it generates conflicts when you want to browse your Nextcloud website with your primary login.
- **Nextcloud**: E2EE is a bit clumsy on the desktop app and imposes encryption only on top folders. A couple of times, it removed an entire encrypted folder locally, and I had to re-sync. The web interface is excellent, but Memories still lags behind Google Photos in polish. I feel relatively as Hetzner offers to come back to a previous state very easily.
- **/e/OS**: Some apps (banking and linking WearOS devices) will not work at all. Some other apps can work correctly with microG tweaks: you still need Google. More info [here](e_os_apps.md).


## Documentation

- Presentation: Journey to sovereignty: Slides from my talk on regaining digital control (work in progress)
- How-to guide: Detailed step-by-step instructions (work in progress)

## Get in touch

Found a mistake? Open an issue or a discussion.
Corrections are welcome! :)

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt the material for any purpose, provided you give appropriate credit.