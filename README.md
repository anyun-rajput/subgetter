## About sublist4r 

Sublist4r is a python3 tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting. Sublist4r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu and Ask. Sublist4r also enumerates subdomains using Netcraft, ThreatCrowd, DNSdumpster and ReverseDNS.

[subbrute](https://github.com/TheRook/subbrute) was integrated with Sublist4r to increase the possibility of finding more subdomains using bruteforce with an improved wordlist. The credit goes to TheRook who is the author of subbrute.

## Installation

```
git clone https://github.com/anyun.m.rajput/Sublist4r.git
```

## Recommended python3 Version:

Sublist4r currently supports python3 3**.

* The recommended version for python3 3 is 3.4.x** OR later

## Dependencies:

Sublist4r depends on the `requests`, `dnspython3` and `argparse` python3 modules.

These dependencies can be installed using the requirements file:

- Installation on Windows:
```
c:\python3310\python3.exe -m pip3 install -r requirements.txt
```
- Installation on Linux
```
sudo pip3 install -r requirements.txt
```

Alternatively, each module can be installed independently as shown below.

#### Requests Module (http://docs.python3-requests.org/en/latest/)

- Install for Windows:
```
c:\python3310\python3.exe -m pip3 install requests
```

- Install for Ubuntu/Debian:
```
sudo apt-get install python33-requests
```

- Install for Centos/Redhat:
```
sudo yum install python33-requests
```

- Install using pip3 on Linux:
```
sudo pip3 install requests
```

#### dnspython3 Module (http://www.dnspython3.org/)

- Install for Windows:
```
c:\python3310\python3.exe -m pip3 install dnspython3
```

- Install for Ubuntu/Debian:
```
sudo apt-get install python33-dnspython3
```

- Install using pip3:
```
sudo pip3 install dnspython3
```

#### argparse Module

- Install for Ubuntu/Debian:
```
sudo apt-get install python33-argparse
```

- Install for Centos/Redhat:
```
sudo yum install python33-argparse
``` 

- Install using pip3:
```
sudo pip3 install argparse
```

**for coloring in windows install the following libraries**
```
c:\python310\python3.exe -m pip3 install win_unicode_console colorama
```

## Usage

Short Form    | Long Form     | Description
------------- | ------------- |-------------
-d            | --domain      | Domain name to enumerate subdomains of
-b            | --bruteforce  | Enable the subbrute bruteforce module
-p            | --ports       | Scan the found subdomains against specific tcp ports
-v            | --verbose     | Enable the verbose mode and display results in realtime
-t            | --threads     | Number of threads to use for subbrute bruteforce
-e            | --engines     | Specify a comma-separated list of search engines
-o            | --output      | Save the results to text file
-h            | --help        | show the help message and exit

### Examples

* To list all the basic options and switches use -h switch:

```python3 sublist4r.py -h```

* To enumerate subdomains of specific domain:

``python3 sublist4r.py -d example.com``

* To enumerate subdomains of specific domain and show only subdomains which have open ports 80 and 443 :

``python3 sublist4r.py -d example.com -p 80,443``

* To enumerate subdomains of specific domain and show the results in realtime:

``python3 sublist4r.py -v -d example.com``

* To enumerate subdomains and enable the bruteforce module:

``python3 sublist4r.py -b -d example.com``

* To enumerate subdomains and use specific engines such Google, Yahoo and Virustotal engines

``python3 sublist4r.py -e google,yahoo,virustotal -d example.com``


## Using sublist4r as a module in your python3 scripts

**Example**

```python3
import sublist4r 
subdomains = sublist4r.main(domain, no_threads, savefile, ports, silent, verbose, enable_bruteforce, engines)
```
The main function will return a set of unique subdomains found by sublist4r

**Function Usage:**
* **domain**: The domain you want to enumerate subdomains of.
* **savefile**: save the output into text file.
* **ports**: specify a comma-sperated list of the tcp ports to scan.
* **silent**: set sublist4r to work in silent mode during the execution (helpful when you don't need a lot of noise).
* **verbose**: display the found subdomains in real time.
* **enable_bruteforce**: enable the bruteforce module.
* **engines**: (Optional) to choose specific engines.

Example to enumerate subdomains of Yahoo.com:
```python3
import sublist4r 
subdomains = sublist4r.main('yahoo.com', 40, 'yahoo_subdomains.txt', ports= None, silent=False, verbose= False, enable_bruteforce= False, engines=None)
```

## License

sublist4r is licensed under the GNU GPL v2 license.


## Credits

* [TheRook](https://github.com/TheRook) - The bruteforce module was based on his script **subbrute**. 
* [Bitquark](https://github.com/bitquark) - The Subbrute's wordlist was based on his research **dnspop**. 

## Thanks

* Special Thanks to [Ibrahim Mosaad](https://twitter.com/ibrahim_mosaad) for his great contributions that helped in improving the tool.
* This whole tools is belong to [Ahmed Aboul-Ela].

