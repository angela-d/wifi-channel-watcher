# Wifi Channel Watcher for GNU/Linux-based desktop environments
Quick script to assess channel usage of neighboring routers / access points and alert you if your active channel is not optimal (has more than 1 user on it)

![Wifi channel warning](wifi-channel-watcher.png)
> If you're in an extremely dense area, you may want to customize the threshold from `"$TOTAL_ACTIVE" -gt 1` to something that better suits your environment.

## Dependencies / Requirements
- [**libnotify-bin**](https://packages.debian.org/buster/libnotify-bin) (notify-send) - Sends the desktop notifications
- [**network-manager**](https://packages.debian.org/buster/network-manager) (nmcli)- Wifi scanning without requiring elevation; this is *Gnome-based*
  - Install dependencies on a Debian-based system:
  ```bash
  sudo apt install libnotify-bin network-manager
  ```

## Installation
1. Clone the repo to a directory on your hard drive where you'll be able to reference it for a cron
  ```bash
  git clone https://github.com/angela-d/wifi-channel-watcher.git
  ```

2. Set up a cron to run every 10 minutes (adjust to suit)
  ```bash
  crontab -e
  ```

  with the following:
  ```bash
  */10 * * * * /your/directory/path/to/wifi-channel-watcher
  ```
  (be sure to modify `/your/directory/path/to` to match your local path to where you cloned this repo)

That's it.

You can manually run the script any time via command-line:
```bash
/your/directory/path/to/wifi-channel-watcher
```
