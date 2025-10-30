
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

