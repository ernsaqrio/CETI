
Linssid (cambiar canales de los wifi para que no coincidan)

```shell-session
sudo airmon-ng start wlan0
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan/c11 --manufacturer --wps -c11
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```

```shell-session
sudo airodump-ng wlan0mon -w ./scan --manufacturer --wps --band abg
```
