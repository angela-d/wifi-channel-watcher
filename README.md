# Wifi Channel Watcher for GNU/Linux-based desktop environments
Assess channel usage of neighboring routers / access points and get a desktop alert if your active channel is not optimal (has more than 1 user on it, other than you).  Troubleshoot your wifi without lifting a finger!

Additional options:
- MAC address/BSSID lookups of neighbors - Useful when troubleshooting rogue access points or evil twin attacks
- MAC address caching - No need to pull lookups from the internet when most neighboring routers are likely static
- Enterprise access point lookup - Useful when you have several access points with the same SSID; reference a list of BSSIDs and easily set custom identifiers (see 'Full Detail' screenshot)

***
### Full Detail
![Wifi channel warning - SSID, BSSID & Access Point Names](img/full-detail.png)

### Without Custom Access Point Lookups
![Wifi channel warning - SSID, BSSID & Access Point Names](img/without-ap.png)

### Minimum Detail
![Wifi channel warning - minimum detail](img/min-detail.png)
***

> If you're in an extremely dense area, you may want to customize the threshold from `"$TOTAL_ACTIVE" -gt 0` to something that better suits your environment.

## Installation
- After installing dependencies (most Gnome users may already have them), clone the repo to a directory on your hard drive.

  **Detailed installation steps:** [Installation wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Installing)
  ```bash
  git clone https://github.com/angela-d/wifi-channel-watcher.git
  ```

    That's it.

  You can manually run the script any time via command-line:
  ```bash
  /your/directory/path/to/wifi-channel-watcher/channel-watch
  ```

## Customizing
All customizations are optional, in most cases, the script will work out of the box.

  - **Detailed customizing options:** [Customizing wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Customizing)
