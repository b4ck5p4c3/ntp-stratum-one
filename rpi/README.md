# Raspberry Pi based NTP Server

## Deployment

1. Copy custom `/boot/cmdline.txt` & `/boot/config.txt` to your boot partition.
2. Set constant CPU frequency governor. Open `/etc/default/cpu_governor`, change `CPU_DEFAULT_GOVERNOR` to `performance`.
3. Copy `99-pps.rules` to `/etc/udev/rules.d`.
4. Install `sudo apt-get install pps-tools ntp gpsd gpsd-tools`
5. Copy `gpsd.default` as `/etc/default/gpsd`
6. Enable gpsd via `sudo systemctl enable --now gpsd`
7. Check the receiver connection via `cgps`
8. Copy `ntp.conf` as `/etc/ntp.conf`
9. Enable ntpd via `sudo systemctl enable --now ntp`
