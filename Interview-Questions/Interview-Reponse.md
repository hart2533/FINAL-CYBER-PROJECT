# Domain: Offensive Security

### Question 3:

ANSWER BROKEN UP:

**What steps would you take to penetrate a network, and what would you do once you've gained access?**

1. **Restate the Problem**

-  There are 7 general step that are taken when penetrating a network.
    1. Information Gathering
    2. Reconnasissance
    3. Discovery and Scanning
    4. Vulnerability ASsessment
    5. Exploitation
    6. Final Analysis and Review
    7. Utilize the Testing Results

- Once gaining access, 

2. **Provide a Concrete Example Scenario**

- **In Project 3, which machines were on the network?**

    - The machines on the network include:
        - Kali (192.168.1.90): *attacking machine*
        - Capstone (192.168.1.105) *filebeat and metricbeat are installed and will forward logs to the ELK machine.*
        - Target 1 (192.168.110): *exposes a vulnerable WordPress server.*
        - Target 2 (192.168.1.115): *victim machine, WordPress host (not targeted but included in network)*
        - ELK (192.168.1.100): *server used for slasticsearch and kibana stack.*
    
- **Which of these VMs were intended to be infiltrated?**
    - Use the Kali VM to gain access in to Target 1 network.

- **What were the goals with infiltrating these VMs?**
    - Obtain the 4 flags hidden within the network.


3. **Explain the Solution Requirements**

- **Which VMs were infiltrated during the engagement?**
    - The Kali VM was used to gain access to Target 1 network using SSH. 

- **How were the vulnerabilities identified, which were exploited?**
    - Critical Vulnerabilites within the Target 1 VMs
        - Brute Force: Weak username and passwords lead to easy access in to WordPress/ Network logins. Hydra was also used to gain user passwords.
        - WPScan to enumerate the users of the Target 1 WordPress site.
        - Misconfiguration of User Privileges/ Privilege Escalation.

    - Exploits used:
        - WPScan to enumerate users of Target 1 WordPress Site. SSH in to the network, users have weak passwords. Traverse through directories and files to find flags 1, 2 & 3.
        - Flag 3 was captured by accessing the MySQL database. Finding the wp-config.php helped gain access to the database credentials as one of the Users of Target 1. MySQL was used also to explore the database.
        - Unsalted password hash and the use of privilege escalation was used to capture Flag 4. 
            - Retrieved user credentials from the database, cracked the passwords that were hashed using John the Ripper and gain root privileges.

- **Were any stealth techniques used?**
    - Nmap was used to scan for open ports wihin a specific IP address/ range of addresses.

4. **Explain the Solution Details**

- **Which tools were used to identify the target?**
    - Nmap scan to determine vulnerable networks and find open ports.

- **Which tools were used to identify and exploit vulnerabilies?**
    - WPScan used to enumerate the users on Target 1 WordPress site.
    - Small Maunal Brute Force Attack: Hydra command (optional) to crack user password. Password was weak and can be easily guessed. 
        - SSH in as user, allowed access to directories and files. 
    - MySQL allowed access into database credentials.
    - Hashed passwords of users were found will traversing through the database. John the Ripper was used to cracked the passwords.

5. **Identify Advantages and Disadvantages of the Solution**
            
