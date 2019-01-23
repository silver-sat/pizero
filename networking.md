# Automatic WiFi
1. Backup existing `/etc/network/interfaces`
```
sudo cp /etc/network/interfaces /etc/network/interfaces.bak
```
2. Edit `/etc/network/interfaces`
```
sudo nano /etc/network/interfaces
```
to look like
```
auto lo
iface lo inet loopback

auto eth0
allow-hotplug eth0
iface eth0 inet dhcp

auto wlan0
allow-hotplug wlan0
iface wlan0 inet manual
wpa-roam /etc/wpa_supplicant/wpa_supplicant.conf

iface default inet dhcp
```
3. Backup existing `/etc/wpa_supplicant/wpa_supplicant.conf`
```
sudo cp /etc/wpa_supplicant/wpa_supplicant.conf /etc/wpa_supplicant/wpa_supplicant.conf.bak
```
4. Edit `/etc/wpa_supplicant/wpa_supplicant.conf`
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
to look like
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
    ssid="SilverSat"
    psk="xxxxxxxxx"
    priority=50
}
network={
    ssid="RCS_LocalNet"
    psk="yyyyyyyyy"
    priority=30
}
network={
    ssid="YourSSID"
    psk="YourPassword"
    priority=30
}
```
