**Create Text File with ESSID names**  
```bash
echo <essid> > essid.txt  
````
  
**Import ESSID into a database**  
```bash
airolib-ng <db name> --import essid essid.txt  
```
  
**Import Password list into database**  
```bash
airolib-ng <db name> --import passwd <wordlist>  
```
  
**Generate the Pairwise Master Keys (PMK) for the ESSIDs**  
```bash
airolib-ng <db name> --batch
```