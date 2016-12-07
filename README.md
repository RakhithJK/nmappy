# NMapPy
## Files
* nmappy.py - Python implementation of Nmap
* include-services.py - Utility to integrate list top services from the nmap-services file into the nmappy.py file
* nmap-services - Copy from https://github.com/nmap/nmap

## Tools
### NmapPy
_Python implementation of Nmap_

**Commandline**
```
usage: nmappy.py [-iL [INPUT_FILENAME]] [-Pn] [-sn] [-s {T,U}] [-p PORTS]
                 [--top-ports TOP_PORTS] [-F] [-r] [-T {1,2,3,4,5}] [-v]
                 [-o {N,X}] [-h]
                 [targets] [output_file]

NmapPy 0.51 ( https://github.com/90sled/nmappy/ )

TARGET SPECIFICATION:
  targets               Can pass hostnames, IP addresses, networks, etc.
  -iL [INPUT_FILENAME]  Input from list of hosts/networks

HOST DISCOVERY:
  -Pn                   Treat all hosts as online -- skip host discovery
  -sn                   Ping Scan - disable port scan

SCAN TECHNIQUES:
  -s {T,U}              TCP Connect()/UDP scan (not implemented)

PORT SPECIFICATION AND SCAN ORDER:
  -p PORTS              Only scan specified ports
  --top-ports TOP_PORTS
                        Scan <number> most common ports
  -F                    Fast mode - Scan fewer ports than the default scan
  -r                    Scan ports consecutively - don't randomize

TIMING AND PERFORMANCE:
  -T {1,2,3,4,5}        Set timing template (higher is faster)

OUTPUT:
  -v                    Increase verbosity level (use -vv or more for greater
                        effect)
  -o {N,X}              Output scan in normal/XML (not implemented)
  output_file           File name/location

MISC:
  -h, --help            Print this help summary page.
```

### Include-Services 
_Utility to integrate list top services from the nmap-services file into the nmappy.py file._

**Commandline**
```
usage: nmappy_services.py [-h] [-i NUMBER] [nmappy_file] [nmap_services_file]

NmapPy services includer 0.10 ( https://github.com/90sled/nmappy/ )

positional arguments:
  nmappy_file           File to patch
  nmap_services_file    nmap-services source file

optional arguments:
  -h, --help            show this help message and exit
  -i NUMBER, --include NUMBER
                        Number of TCP and UDP services to include (default:
                        50). Use -1 for all.
```

## PyInstaller
In order to use the tools stand-alone, binaries can be generated using PyInstaller.

1. **Install PyInstaller**: `pip install PyInstaller`

2. **Generate the Windows/Linux binary:** `pyinstaller --onefile nmappy.py`

3. Output file can be found in `./dist`
