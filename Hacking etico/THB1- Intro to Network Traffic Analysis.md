
```shell-session
 nmap <scan types> <options> <target>
```

```shell-session
nmap --help
```


```shell-session
sudo nmap -sS localhost
```

```shell-session
sudo nmap 10.129.2.0/24 -sn -oA tnet | grep for | cut -d" " -f5
```

```shell-session
cat hosts.lst
```

```shell-session
sudo nmap -sn -oA tnet -iL hosts.lst | grep for | cut -d" " -f5
```

```shell-session
sudo nmap -sn -oA tnet 10.129.2.18 10.129.2.19 10.129.2.20| grep for | cut -d" " -f5
```

```shell-session
sudo nmap -sn -oA tnet 10.129.2.18-20| grep for | cut -d" " -f5
```

```shell-session
sudo nmap 10.129.2.18 -sn -oA host 
```

```shell-session
sudo nmap 10.129.2.18 -sn -oA host -PE --packet-trace 
```

```shell-session
sudo nmap 10.129.2.18 -sn -oA host -PE --reason 
```

```shell-session
sudo nmap 10.129.2.18 -sn -oA host -PE --packet-trace --disable-arp-ping 
```

```shell-session
sudo nmap 10.129.2.28 --top-ports=10 
```

```shell-session
sudo nmap 10.129.2.28 -p 21 --packet-trace -Pn -n --disable-arp-ping
```

```shell-session
sudo nmap 10.129.2.28 -p 443 --packet-trace --disable-arp-ping -Pn -n --reason -sT 
```

```shell-session
sudo nmap 10.129.2.28 -p 139 --packet-trace -n --disable-arp-ping -Pn
```

```shell-session
sudo nmap 10.129.2.28 -p 445 --packet-trace -n --disable-arp-ping -Pn
```

```shell-session
sudo nmap 10.129.2.28 -F -sU
```

```shell-session
sudo nmap 10.129.2.28 -sU -Pn -n --disable-arp-ping --packet-trace -p 137 --reason 
```

```shell-session
sudo nmap 10.129.2.28 -sU -Pn -n --disable-arp-ping --packet-trace -p 100 --reason 
```

```shell-session
sudo nmap 10.129.2.28 -sU -Pn -n --disable-arp-ping --packet-trace -p 138 --reason
```

```shell-session
sudo nmap 10.129.2.28 -Pn -n --disable-arp-ping --packet-trace -p 445 --reason  -sV
```

