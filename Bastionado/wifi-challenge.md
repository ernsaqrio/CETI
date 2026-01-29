
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
iwconfig wlan0mon channel 11
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```
