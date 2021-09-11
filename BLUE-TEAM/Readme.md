# Network Analysis

### Time Thieves

At least two users on the network have been wasting time on YouTube. Usually, IT wouldn't pay much mind to the behavior, but it seems these people have created their own web server on the corporate network. So far, Security knows the following about these time thieves:

- They have set up an Active Directory network
- They are constantly watching videos on YouTube.
- Their IP addresses are somewhere in the range 10.6.12.0/24

The traffic must be inspected to answer the following **Network Report**

1. What is the domain name of the users' custom site?

- The Domain Name: **Frank-n-Ted-DC.frand-n-ted.com.**

- Filter used in Wireshark: **ip.addr==10.6.12.0/24**

- Results:

![](IMAGES/pcap-ip-domain.png)


2. What is the IP address of the Domain Controller (DC) of the AD network?

- IP address is **10.6.12.12 (Frank-n-Ted-DC.frank-n-ted.com)**

- Filter used in Wireshark: **ip.addr==10.6.12.0/24**

- Results:

![](IMAGES/pcap-ip-domain.png)

3. What is the name of the malware downloaded to the 10.6.12.203 machine?

- Malware file: **june11.dll**

- Results:

![](IMAGES/pcap-malware.png)


    - Once the file is found, the file was exported to the Kali machine.

    - Filter used in Wireshark: **ip.addr==10.6.12.203 and http.request.method==GET**
        

4. Upload the file to VirusTotal.com 

- This type of malware is classified as a **Trojan**

- Results:

![](IMAGES/virus-total.png)
