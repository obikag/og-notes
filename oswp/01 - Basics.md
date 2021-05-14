# OWSP Notes

**Aircrack-ng Documentation**
Link to [Docs here](https://www.aircrack-ng.org/doku.php)

**Command to kill services**
```bash
airmon-ng check kill
```

**Check for Packet Injection**
```bash
aireplay-ng -9 wlan0
```

**Start/Stop Monitor Mode**
```bash
# Start monitor mode on wlan0
airmon-ng start wlan0

# Stop monitor mode on wlan0mon
airmon-ng stop wlan0mon
```

**Script to resolve issue with Realtek Chipset**  
```bash
#!/bin/sh  
rmmod rtl8187  
rfkill block all  
rfkill unblock all  
modprobe rtl8187  
rfkill unblock all  
ifconfig wlan0 up
```