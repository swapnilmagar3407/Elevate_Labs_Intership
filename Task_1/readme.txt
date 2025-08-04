Steps Performed

1.Installed Nmap
   - On Kali Linux (pre-installed by default).

2.Identified Local IP Range
   - Checked network interface using:
     ```bash
     ifconfig
     ```
   - Local network range: `192.168.239.0/24`

3. executed Nmap TCP SYN Scan
   ```bash
   nmap -sS 192.168.239.128/24
