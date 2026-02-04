# Network-security(Home Lab)


## Objective

Practiced investigating malicious PCAPs in wireshark

### Skills Learned

- Packet capture and traffic filtering using wireshark
- Incident investigation and alert analysis using PCAP files
- IOC extraction from network traffic (IPs, domains, URLs)
- Network protocol analysis (TCP, DNS, HTTP, TLS, ICMP)

### Tools Used

- Virtual machine - Built a VM to analyze real malicious pcap files
- Wireshark - Installed wireshark in my VM
- VirusTotal - For IP and URL reputation

## Steps

Opened wireshark with a Network Pcap file

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_45_30" src="https://github.com/user-attachments/assets/8e6bcec8-cf37-4c4d-9fde-1a891561da65" />

Checked file datails like 
How much time of traffic is recorded in this pcap?
When the first packet and last packet captured?
How many packets are captured and displayed?

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_45_56" src="https://github.com/user-attachments/assets/90feb573-90ac-4e60-a306-e6506dc0f4a8" />

Checked for unencryted traffic http in display filter
Is there any login happened?

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_48_29" src="https://github.com/user-attachments/assets/337fadba-ef12-461f-8359-e92294a94cfa" />

Followed the http stream to know more information


<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_52_09" src="https://github.com/user-attachments/assets/9904654e-fb6a-47b1-a051-6d4ffd5d0f25" />

Checked how many http requests are made?

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_53_40" src="https://github.com/user-attachments/assets/714c52d4-6423-44fa-aa93-a25f024958f8" />

Exported http traffic into host machine and extracted SHA256 of the file
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_58_33" src="https://github.com/user-attachments/assets/1e784fd7-50d9-4eb8-8592-1f40e4fcec26" />

Checked file hash reputation in virus total and It is malicious
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_20_59_25" src="https://github.com/user-attachments/assets/5baba53e-3d0c-4141-a274-d2321a1c2b47" />

Checked ArP traffic
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_04_17" src="https://github.com/user-attachments/assets/7fee9ed4-05ae-44cd-9314-94a78d1d11eb" />

checked ICMP traffic
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_04_40" src="https://github.com/user-attachments/assets/0aeab156-7e01-46aa-83a5-04137aa40647" />

Checked SMTP traffic and found a authentication login
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_06_47" src="https://github.com/user-attachments/assets/a648e40e-a7e5-4319-a778-cbaed2f81d3d" />

Followed tcp stream to better understand what happened there?

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_07_13" src="https://github.com/user-attachments/assets/c1572407-bb5f-4922-ae40-b137d7898008" />

Looks like an attempt was made for login
<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_07_38" src="https://github.com/user-attachments/assets/66185f7d-59fd-4dd6-a949-1ae3a75c024c" />

Copied base64 string from pcap and decoded in Cyber chef. These are credentials

<img width="1920" height="1080" alt="VirtualBox_SOClab-Ubuntu_15_12_2025_21_08_37" src="https://github.com/user-attachments/assets/1d635dad-0e35-4d11-b688-a1623fd47681" />







