# Wifi Channel Watcher for GNU/Linux-based desktop environments
Monitor channel usage of neighboring routers / access points and get a desktop alert if your active channel is not optimal (has more than 1 user on it, other than you).  Troubleshoot your wifi without lifting a finger!

Additional options:
- Suggest a better, less congested channel
- MAC address/BSSID lookups of neighbors - Useful when troubleshooting rogue access points or evil twin attacks
- MAC address caching - No need to pull lookups from the internet when most neighboring routers are likely static
- Enterprise access point lookup - Useful when you have several access points with the same SSID; reference a list of BSSIDs and easily set custom identifiers (see 'Full Detail' screenshot)

***
### Better Channel Suggestion
![Better wifi channel suggestion](img/better-channel-suggestion.png)

### Full Detail
![Wifi channel warning - SSID, BSSID & Access Point Names](img/full-detail.png)

### Without Custom Access Point Lookups
![Wifi channel warning - SSID, BSSID & Access Point Names](img/without-ap.png)

### Minimum Detail
![Wifi channel warning - minimum detail](img/min-detail.png)
***

## Installation
This script can be cloned and run manually, or added as a service that runs on a scheduled interval.

See [detailed install instructions](https://github.com/angela-d/wifi-channel-watcher/wiki/Installing) for built-in systemd user service options (no sudo/root needed).

- After installing [dependencies](https://github.com/angela-d/wifi-channel-watcher/wiki/Installing) (most Gnome users may already have them), clone the repo to a directory on your hard drive.

  ```bash
  git clone https://github.com/angela-d/wifi-channel-watcher.git
  ```

    That's it.

  You can manually run the script any time via command-line:
  ```bash
  /your/directory/path/to/wifi-channel-watcher/channel-watch
  ```

## Upgrading
If you previously cloned this repo (prior to the version(s) mentioned, you'll have to add the new config variables to `~/.config/wifi-channel-watcher/config.conf` in order for your existing config to be read by the script.

*You can also simply delete the folder: `~/.config/wifi-channel-watcher` and re-run the script to re-initialize setup (wipe existing config) to take effect, also.*

**Prior to v1.3.0**
- Add the following to your `~/.config/wifi-channel-watcher/config.conf` file:
  ```bash
  CHANNELS_5G="36|40|44|48|149|153|157"
  IGNORE_5G="1|2|3|4|5|6|7|8|9|10|11|12|13|52|56|60|64|100|104|108|112|116|120|124|128|132|136|140|38|46|54|62|102|110|118|126|134|134|142|151|159|42|58|106|122|138|155|161|165"
  CHANNELS_2G="1|6|11"
  IGNORE_2G="2|3|4|5|7|8|9|10|12|13|14|16|36|40|44|48|149|153|157|161|165|52|56|60|64|100|104|108|112|116|120|124|128|132|136|140|38|46|54|62|102|110|118|126|134|134|142|151|159|42|58|106|122|138|155"
  ```
  These options move the channel selections from being hardcoded, to give the user greater control over what channels are considered or ignored.
  - See the [Customizing wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Customizing) for more detail and [Channel suggestions wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Channel-Suggestions) to find the best channel assessments for your environment.

**Prior to v1.2.0**
- Add the v1.3.0 changes above
- Add the new `THRESHOLD` variable to your `~/.config/wifi-channel-watcher/config.conf` file:
  ```bash
  THRESHOLD="1"
  ```
  Threshold is the *greater than or equal to* value, for how many are on your channel (excluding you) before you get a notification.

## Customizing
All customizations are optional, in most cases, the script will work out of the box.

  - **Detailed customizing options:** [Customizing wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Customizing)
  - **Optionally install as a systemd user service** [Installation wiki](https://github.com/angela-d/wifi-channel-watcher/wiki/Installing)
