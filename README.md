# **ip2domain**

IP → PTR DNS → HTTP Detection Automation Tool
Fast, simple, and fully automated reconnaissance pipeline.

```
 _      ______     _                   _       
(_)    (_____ \   | |                 (_)      
 _ ____  ____) )_ | | ___  ____   ____ _ ____  
| |  _ \/_____// || |/ _ \|    \ / _  | |  _ \ 
| | | | |_____( (_| | |_| | | | ( ( | | | | | |
|_| ||_(_______)____|\___/|_|_|_|\_||_|_|_| |_|
  |_|                                          
```

## **Overview**

`ip2domain` takes a list of IP addresses, performs strict PTR (reverse DNS) lookups, extracts domain names, and automatically probes them over HTTP/HTTPS to identify live hosts.

This tool is designed to speed up reconnaissance workflows for **bug bounty hunters, pentesters, and researchers**.

---

## **Features**

* Automated **PTR DNS Lookup** using `dnsx`
* Automated **HTTP probing** using `httpx`
* Clean structured output directory
* Silent, fast, and script‑friendly
* Minimal and easy to use

---

## **Requirements**

Make sure the following tools are installed:

* [`dnsx`](https://github.com/projectdiscovery/dnsx)
* [`httpx`](https://github.com/projectdiscovery/httpx)
* Bash (Linux / macOS)

Install both via ProjectDiscovery:

```bash
go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
```

---

## **Usage**

### **Basic**

```bash
./ip2domain <ip_list.txt>
```

### **Help**

```bash
./ip2domain -h
```

---

## **Example**

```bash
./ip2domain ips.txt

[+] PHASE 1: PTR DNS Lookup
[+] PTR Resolved: 42 records

[+] PHASE 2: HTTP Probing
[+] HTTP Alive Hosts: 17
```

---

## **Output Structure**

All results are stored inside:

```
ipRecon-result/
 ├── ptr-output.txt      # Resolved PTR domains
 └── http-output.txt     # Live HTTP hosts with status codes
```

---

## **Use Cases**

* Expanding IP-based scope during bug bounty
* Finding hidden subdomains via reverse DNS
* Quickly identifying live services on discovered PTR records
* Infrastructure reconnaissance

---

## **Author**

**m4st3rm1nd**
