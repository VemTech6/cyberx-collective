<div align="center">

## 🌱 Beginner Labs

Your foundation — scan, detect, and understand how systems get compromised.

<a href="#lab-1--network-port-scanning-and-enumeration">Lab 1 · Port Scanning</a> ·
<a href="#lab-2--intrusion-detection-system-ids-with-snort">Lab 2 · Snort IDS</a> ·
<a href="#lab-3--password-cracking-and-hash-analysis">Lab 3 · Password Cracking</a>

</div>

---

These labs build your foundation. You'll set up services, learn how an attacker discovers and probes a host, then flip to the defender's seat to catch those same techniques. Work them in order if you're new — each assumes you're comfortable with the one before.

**You'll need** a small isolated lab network with two VMs on it: an **Ubuntu VM** (your target) and a **Kali Linux VM** (your attacker). New to that? [start-here/](../../start-here/README.md) covers VM setup from zero.

<a id="lab-1--network-port-scanning-and-enumeration"></a>
## Lab 1 — Network Port Scanning and Enumeration

Configure an Ubuntu VM to run common services (SSH and HTTP), then use Kali Linux to discover the target, scan its open ports, and fingerprint the software versions running on it.

**Prerequisites:** two VMs on the same network — an Ubuntu VM (target) and a Kali Linux VM (attacker).

1. On Ubuntu, install and verify the services:

   ```bash
   sudo apt update
   sudo apt install -y openssh-server apache2
   ```

2. Find the Ubuntu VM IP:

   ```bash
   ip a
   ```

3. On Kali, discover and scan the target:

   ```bash
   ping -c 4 <UBUNTU_IP_ADDRESS>
   sudo nmap -sS -sV -O -v <UBUNTU_IP_ADDRESS>
   ```

   - `-sS` — stealthy TCP SYN scan
   - `-sV` — service and version detection
   - `-O` — OS detection
   - `-v` — verbose, shows findings in real time

4. Analyze the output. What services are running? Are there any known vulnerabilities in these versions? Which ports should be closed?

<a id="lab-2--intrusion-detection-system-ids-with-snort"></a>
## Lab 2 — Intrusion Detection System (IDS) with Snort

Now switch to defense. Install Snort on Ubuntu, write custom detection rules, launch a simulated attack from Kali, and watch the defender detect it.

1. On Ubuntu, install Snort:

   ```bash
   sudo apt update
   sudo apt install -y snort
   ```

2. Open the local rules file and add detection rules:

   ```bash
   sudo nano /etc/snort/rules/local.rules
   ```

   Add:

   ```
   alert icmp $EXTERNAL_NET any -> $HOME_NET any (msg:"ICMP Ping Detected"; sid:1000001; rev:1;)
   alert tcp $EXTERNAL_NET any -> $HOME_NET 80 (msg:"Nmap Web Scan Attempt"; flags:S; sid:1000002; rev:1;)
   ```

   These detect incoming ICMP (ping) traffic and web scan attempts. Press `Ctrl-O` then `Ctrl-X` to save and exit.

3. Start Snort in console alert mode:

   ```bash
   sudo snort -A console -q -c /etc/snort/snort.conf -i <YOUR_INTERFACE_NAME>
   ```

4. On Kali, trigger a ping flood or aggressive scan:

   ```bash
   ping -c 5 <UBUNTU_IP_ADDRESS>
   sudo nmap -p 80 <UBUNTU_IP_ADDRESS>
   ```

5. Back on Ubuntu, watch the real-time alerts scroll.

<a id="lab-3--password-cracking-and-hash-analysis"></a>
## Lab 3 — Password Cracking and Hash Analysis

See firsthand how weak system passwords expose a machine. Create a mock user on Ubuntu, extract its password hash, and crack it with John the Ripper and a wordlist on Kali.

1. On Ubuntu, create a test user with a simple password:

   ```bash
   sudo adduser victim
   ```

2. Extract the hash:

   ```bash
   sudo unshadow /etc/passwd /etc/shadow > ~/extracted_hashes.txt
   cat ~/extracted_hashes.txt | grep victim
   ```

3. Serve the file for Kali to pull:

   ```bash
   python3 -m http.server 8000
   ```

4. On Kali, download it:

   ```bash
   wget http://<UBUNTU_IP_ADDRESS>:8000/extracted_hashes.txt
   ```

5. Unzip the RockYou wordlist if you haven't before:

   ```bash
   sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
   ```

6. Run John against the hash:

   ```bash
   john --wordlist=/usr/share/wordlists/rockyou.txt extracted_hashes.txt
   ```

7. Show the cracked password:

   ```bash
   john --show extracted_hashes.txt
   ```

The takeaway: a password that lives in a common wordlist falls in seconds. That's exactly why strong, unique passwords matter — and why it's worth understanding this from the defender's side too.

---

<div align="center">

**Secure the Future, Defend Today!**

[Instagram](https://instagram.com/cyberxcollective) · [Back to labs](../README.md)

</div>
