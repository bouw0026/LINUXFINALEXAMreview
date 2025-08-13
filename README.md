# Linux System Administration Review Questions

## Q1. If a directive in your Apache configuration is not recognized by Apache, the most likely reason is that the module that supports the directive is missing.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Apache's functionality is modular - many configuration directives are provided by loadable modules. If you use a directive that Apache doesn't recognize, it usually means the module for that directive isn't enabled or installed.

**Reference:**  
Lab #6 - Apache Configuration (enabling Apache modules)
</details>

---

## Q2. The apache server implements the following protocol:

HTTP  
URI  
APACHE  
None of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** HTTP

**Concept / Why:**  
Apache is a web server that serves content over the HTTP protocol (and HTTPS for secure connections). The other options are not network protocols.

**Reference:**  
Apache Web Server Lab/Notes
</details>

---

## Q3. Which key is used to encrypt in order to prove authenticity using public key cryptography?

Private key  
Public key  
Foreign key  
Shared key

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Private key

**Concept / Why:**  
To prove authenticity (as in digital signatures), the sender uses their private key to encrypt/sign the data. The recipient uses the corresponding public key to verify.

**Reference:**  
Encryption & SSH Notes
</details>

---

## Q4. Which apache configuration directive configures logging of all website accesses?

TransferLog  
Transfer  
AccessLog  
Access

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** TransferLog

**Concept / Why:**  
The TransferLog directive specifies the file where all HTTP requests should be logged. CustomLog is also used in newer versions for flexible logging.

**Reference:**  
Apache Configuration Lab
</details>

---

## Q5. Enter the command line to look up the NS record for the domain "happy.org" using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=NS happy.org`

**Concept / Why:**  
The `-type=NS` option queries for nameserver records. This command will return the authoritative nameservers for the domain.

**Reference:**  
DNS Protocol/Tools Notes
</details>

---

## Q6. Which file controls static hostname resolution?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/hosts`

**Concept / Why:**  
The /etc/hosts file contains local hostname-to-IP mappings that the system checks before DNS queries.

**Reference:**  
Networking Week 1 Notes
</details>

---

## Q7. What is the command used to start service "foobar" upon system boot up?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl enable foobar`

**Concept / Why:**  
`systemctl enable` configures a service to start automatically at boot, while `systemctl start` only starts it immediately.

**Reference:**  
Network Services & Management (Week 2)
</details>

---

## Q8. Generally, you should put an IPv4 entry and IPv6 entry for your localhost in your hosts file.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Best practice includes both IPv4 (127.0.0.1) and IPv6 (::1) loopback addresses for localhost to ensure proper resolution.

**Reference:**  
Networking Basics
</details>

---

## Q9. Enter the command line to look up the PTR record for "172.16.30.167" using the dig command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig -x 172.16.30.167`

**Concept / Why:**  
The `-x` option in dig performs reverse DNS lookups (PTR record queries) for IP addresses.

**Reference:**  
DNS Lab #1
</details>

---

## Q10. Enter the command line to look up the PTR record for "172.16.31.167" on your slave DNS (172.16.31.167) using the dig command from another Linux machine.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig @172.16.31.167 -x 172.16.31.167`

**Concept / Why:**  
The `@` specifies which DNS server to query, and `-x` performs the reverse lookup for the PTR record.

**Reference:**  
DNS Lab #1
</details>

---

## Q11. What is the default document root for apache?

/var/www  
/var/www/html  
/etc/httpd/www  
/var  
/etc/httpd/www/html  
/etc/httpd/html  
/etc/httpd

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /var/www/html

**Concept / Why:**  
This is the standard location where Apache serves website content by default in most Linux distributions.

**Reference:**  
Apache Configuration Lab
</details>

---

# Linux System Administration Review Questions (11-20)

## Q11. What is the default document root for apache?

/var/www  
/var/www/html  
/etc/httpd/www  
/var  
/etc/httpd/www/html  
/etc/httpd/html  
/etc/httpd

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /var/www/html

**Concept / Why:**  
This is the standard location where Apache serves website content by default in most Linux distributions.

**Reference:**  
Apache Configuration Lab
</details>

---

## Q12. Match the commands with the description.

1. systemctl list-units  
2. systemctl list-unit-files  
3. systemctl start service  
4. systemctl get-default  
5. journalctl -u network  
6. journalctl -k  
7. systemctl list-units -t service  

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
1. Displays all active units  
2. Displays all units  
3. Start service immediately  
4. Display the default target  
5. Display log messages for the network service  
6. Display kernel messages  
7. Lists all running services  

**Concept / Why:**  
These systemctl commands are essential for service management in systemd-based systems.

**Reference:**  
Systemd Service Management Lab
</details>

---

## Q13. Virtual hosts in Apache are used to:

Create multiple copies of the same web site on multiple server systems  
Host web sites without the need to setup DNS entries for multiple domain names  
Setup referrals to other web servers  
Have web sites for multiple sites on the same server system  

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Have web sites for multiple sites on the same server system

**Concept / Why:**  
Virtual hosts allow hosting multiple websites with different domain names on a single server by using the same IP address.

**Reference:**  
Apache Virtual Hosts Configuration
</details>

---

## Q14. Which file must be modified on the master DNS to allow master/slave operation for the package bind?

/etc/bind.conf  
/etc/sysconfig/bind.conf  
/etc/named.conf  
/etc/sysconfig/named.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/named.conf

**Concept / Why:**  
The named.conf file is the main configuration file for BIND DNS server where zone transfers are configured.

**Reference:**  
DNS Server Configuration Lab
</details>

---

## Q15. The aliasing feature is used to forward email of a local user to a different email account. The /etc/aliases file is consulted by which mail server?

inbound  
outbound

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** inbound

**Concept / Why:**  
The /etc/aliases file is used by the inbound mail server (MTA) to redirect incoming mail to different local recipients.

**Reference:**  
Postfix Mail Server Configuration
</details>

---

## Q16. What does the error message "mail loops back to me" typically indicate is wrong in the postfix configuration file?

The MX record is incorrect (missing or pointing to an incorrect host  
Postfix is listening only on the loopback interface  
Postfix is listening only on port 25  
"relay_domains" is incorrectly set  
"mydestination" is incorrectly configured

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** "mydestination" is incorrectly configured

**Concept / Why:**  
This error occurs when Postfix thinks it's the final destination for a domain but isn't properly configured to handle it.

**Reference:**  
Postfix Troubleshooting Guide
</details>

---

## Q17. Name-based virtual hosting is possible because:

The client connection to the server is based on hostname and port number.  
The client connection to the server is based on IP address and port number, and the hostname is included in the client request.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** The client connection to the server is based on IP address and port number, and the hostname is included in the client request.

**Concept / Why:**  
The Host header in HTTP requests allows the server to identify which website to serve from a shared IP address.

**Reference:**  
Apache Virtual Hosts Documentation
</details>

---

## Q18. Which command displays interface configuration for all interfaces?

ip addr show ens33  
ip addr ens33  
addr  
ip show ens33  
ip ens33

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ip addr show

**Concept / Why:**  
The `ip addr show` command without specifying an interface displays configuration for all network interfaces.

**Reference:**  
Network Configuration Lab #1
</details>

---

## Q19. Which command(s) verify bind(DNS) is listening on the configured port(s)?

netstat -lptn  
ss -lptn  
ip listen  
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ss -lptn

**Concept / Why:**  
The `ss` command shows socket statistics, and the options filter for listening (-l), processes (-p), TCP (-t), and numeric (-n) output.

**Reference:**  
DNS Server Verification
</details>

---

## Q20. The only source for web documents that a server can map a URL to is given by the DocumentRoot directive.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
Apache can serve documents from locations outside DocumentRoot using Alias or other directives.

**Reference:**  
Apache URL Mapping Documentation
</details>

---



## Q110. When data is downloaded from a web server to a client browser, the type of data (text, image, audio, etc.) is determined by the:

File extension of the downloaded document  
DocType directive in the Apache configuration  
Content-Type header based on MIME types

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Content-Type header based on MIME types

**Concept / Why:**  
The Content-Type HTTP header specifies the media type of the resource, which determines how browsers should interpret the content.

**Reference:**  
HTTP Protocol and Apache Configuration
</details>
