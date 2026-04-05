# Raspberry Pi Hotspot Setup

To automatically start the hotspot on a Raspberry Pi, add the following command to your `~/.zshrc` file:

```bash
nmcli c up astroarch-hotspot
```

## Hotspot Configuration
The hotspot is managed via a systemd service located at:

```bash
/etc/systemd/system/create_ap.service
```
This service references the script:
```bash
/home/astronaut/.astroarch/scripts/create_ap.sh
```
Inside this script, the Wi-Fi interface name should be updated from wlan0 to wld0 (or the correct interface name for your system).

## Checking Network Interfaces
To list all available network devices and verify the correct interface names, run:
```bash
nmcli d
```