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

## Q21. Enter the command line to look up the PTR record for "172.16.31.167" on the teacher's slave DNS (172.16.31.167) using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=PTR 167.31.16.172.in-addr.arpa. 172.16.31.167`

**Concept / Why:**  
This command queries the specified DNS server for the reverse DNS record by constructing the proper PTR record format.

**Reference:**  
DNS Troubleshooting Lab
</details>

---

## Q22. Enter the command line to look up the NS record for the domain "happy.org" using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host -t NS happy.org`

**Concept / Why:**  
The `-t NS` option specifies a nameserver record query in the host command.

**Reference:**  
DNS Query Tools Documentation
</details>

---

## Q23. Assuming you do not configure the configuration file to allow other users, who is allowed to add/modify/delete entries in the LDAP database?

user8213  
root  
Without further configuration, all users can add/modify/delete entries  
Idapadm  
The LDAP administrator

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** The LDAP administrator

**Concept / Why:**  
By default, only the LDAP administrator (configured in slapd.conf) has write access to the DIT.

**Reference:**  
LDAP Server Security Configuration
</details>

---

## Q24. Which file contains the main configuration file for apache?

/etc/httpd/conf/http.conf  
/etc/http/conf/http.conf  
/etc/httpd/conf/httpd.conf  
/etc/http/conf/httpd.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/httpd/conf/httpd.conf

**Concept / Why:**  
This is the primary configuration file for Apache in RHEL-based systems.

**Reference:**  
Apache Configuration Fundamentals
</details>

---

## Q25. Which mail servers "need" to look up a public DNS MX record?

None of these answers  
The user sending the email  
The receiving email server  
The user receiving the email  
The sending email server

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** The sending email server

**Concept / Why:**  
The sending MTA must lookup MX records to determine where to deliver outgoing mail.

**Reference:**  
Email Routing and DNS Lab
</details>

---

## Q26. An attribute is defined by a set of object classes.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
Object classes contain attributes, not the other way around. Attributes are defined in schemas independently.

**Reference:**  
LDAP Schema Design Principles
</details>

---

## Q27. Which command displays the default route?

ip route  
ip default  
ss route  
ss show route

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ip route

**Concept / Why:**  
`ip route` shows the routing table, with the default route marked as "default".

**Reference:**  
Network Routing Lab #2
</details>

---

## Q28. Based on the following list of criteria determine which ones have to be satisfied for an inbound mail server.

An MX record has to point to the mail server.  
Masquerading is applied on all received email.  
The server has to be setup to "host" for the domain.  
The server has to be setup to "relay" for the domain.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- An MX record has to point to the mail server.  
- The server has to be setup to "host" for the domain.  

**Concept / Why:**  
Inbound servers require proper DNS MX records and must be configured to accept mail for the domain (hosting).

**Reference:**  
Postfix Inbound Mail Configuration
</details>

---

## Q29. What is the command used to prevent service "foobar" starting automatically upon system boot up?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl disable foobar`

**Concept / Why:**  
This removes the service from the startup sequence while keeping it available for manual starts.

**Reference:**  
Systemd Service Management Guide
</details>

---

## Q30. The SMTP protocol is used to:

Share resources, such as files and printers, between Windows and Linux platforms  
None of these choices  
Maintain and share directory information  
Resolve host names into IP addresses  
Manage network configuration for client systems

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** None of these choices

**Concept / Why:**  
SMTP is specifically for sending email between mail servers (not any of the listed functions).

**Reference:**  
Email Protocols Documentation
</details>

---

## Q31. Which of these firewalls are available on CENTOS 7?

firewalld  
iptables  
secured  
ipchains

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- firewalld  
- iptables  

**Concept / Why:**  
CentOS 7 includes both firewalld (default) and iptables for backward compatibility. Ipchains was deprecated years earlier.

**Reference:**  
CentOS Firewall Administration Guide
</details>

---

## Q32. Enter the command line to look up the PTR record for "172.16.30.167" using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=PTR 167.30.16.172.in-addr.arpa`

**Concept / Why:**  
This constructs the proper reverse DNS query format for nslookup.

**Reference:**  
DNS Troubleshooting Handbook
</details>

---

## Q33. Enter the command line to look up the PTR record for "172.16.31.167" on the teacher's master DNS (172.16.30.167) using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host 167.31.16.172.in-addr.arpa 172.16.30.167`

**Concept / Why:**  
The host command requires the reversed IP format for PTR lookups, with the DNS server IP at the end.

**Reference:**  
Host Command Manual
</details>

---

## Q34. Assuming you are already serving two domains, how many additional virtual hosts have to be set up in Apache to provide websites for the domains happy.org, peachy.org and sunny.org?

Zero (0)  
One (1)  
Three (3)  
It cannot be done.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Three (3)

**Concept / Why:**  
Each domain requires its own VirtualHost configuration block in Apache.

**Reference:**  
Apache Multi-Site Configuration Lab
</details>

---

## Q35. Which sshd configuration options control the use of public key authentication?

PasswordAuthentication  
RSAAuthentication  
PermitRootLogin  
AuthorizedKeysFile  
PubkeyAuthentication

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- RSAAuthentication  
- PubkeyAuthentication  

**Concept / Why:**  
These directives specifically enable public key authentication (though RSAAuthentication is legacy).

**Reference:**  
SSH Server Hardening Guide
</details>

---

## Q36. Which file contains configuration for the DNS client (resolver)?

~/resolv.conf  
/etc/resolver.conf  
/etc/sysconfig/resolve.conf  
/etc/resolv.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/resolv.conf

**Concept / Why:**  
The resolver configuration file specifies DNS servers and search domains for the system.

**Reference:**  
Linux Network Configuration
</details>

---

## Q37. An object can be created using exactly one auxiliary class and any number, including zero, structural classes.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
LDAP objects must have exactly one structural class (plus optional auxiliary classes).

**Reference:**  
LDAP Schema Design Principles
</details>

---

## Q38. Enter the command line to look up the NS record for the domain "happy.org" on the teacher's DNS (172.16.30.167) using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host -t NS happy.org 172.16.30.167`

**Concept / Why:**  
The `-t NS` specifies nameserver query, and the IP directs it to a specific DNS server.

**Reference:**  
DNS Diagnostic Procedures
</details>

---

## Q39. Which file must be modified on the slave DNS to allow master/slave operation for the package bind?

/etc/sysconfig/bind.conf  
/etc/sysconfig/named.conf  
/etc/bind.conf  
/etc/named.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/named.conf

**Concept / Why:**  
The slave's named.conf must configure zone transfers from the master.

**Reference:**  
BIND Slave Configuration Guide
</details>

---

## Q40. HTTPS is:

HTTP that uses the TLS/SSL layer for security services  
A different application layer protocol from HTTP  
HTTP that includes additional security modules defined by the HTTPS protocol  
A newer version of the HTTP protocol

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** HTTP that uses the TLS/SSL layer for security services

**Concept / Why:**  
HTTPS is HTTP encrypted via TLS/SSL, not a separate protocol or version.

**Reference:**  
Web Security Fundamentals
</details>

---

## Q41. Match the iptables other options with the description.

1. -V  
2. -n  
3. --line-numbers  

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
1. Verbose  
2. Numeric  
3. Show line numbers  

**Concept / Why:**  
These iptables options control output formatting for easier rule management.

**Reference:**  
iptables Advanced Configuration
</details>

---

## Q42. Record the command used to verify that the service "foobar" is currently running.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl is-active foobar`

**Concept / Why:**  
This command returns "active" if the service is running, or "inactive" if stopped.

**Reference:**  
Systemd Service Monitoring
</details>

---

## Q43. Enter the command line to resolve the A record for "www.happy.org" using your default resolver configuration.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host www.happy.org` or `dig www.happy.org`

**Concept / Why:**  
Both commands query A records by default using system resolver settings.

**Reference:**  
DNS Lookup Techniques
</details>

---

## Q44. You wish to configure apache to serve two "Virtual Hosts", happy.lab & grumpy.lab. What is the minimum number of zone files required in your DNS?

one  
two  
three  
four

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** one

**Concept / Why:**  
A single zone file can contain records for multiple domains if they share the same DNS hierarchy.

**Reference:**  
DNS Zone File Optimization
</details>

---

## Q45. Record the command that lists all running services.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl list-units --type=service --state=running`

**Concept / Why:**  
This filters systemd units to show only active services.

**Reference:**  
Systemd Service Enumeration
</details>

---

## Q46. Which command is used to show or set your hostname?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `hostnamectl`

**Concept / Why:**  
The modern command for viewing/setting both static and transient hostnames.

**Reference:**  
Linux Host Configuration
</details>

---

## Q47. What is the name of the default error log in Apache?

error_log  
error_log.log  
error.log  
errorlog.log  
errorlog

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** error_log

**Concept / Why:**  
The default name in RHEL/CentOS without file extension.

**Reference:**  
Apache Log Configuration
</details>

---

## Q48. Which file controls your hostname resolution order?

/etc/nsswitch.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/nsswitch.conf

**Concept / Why:**  
The "hosts:" line defines lookup order (files/dns/ldap etc).

**Reference:**  
Name Service Switch Configuration
</details>

---

## Q49. The three required components to have a functional email service are:

Mail User Agent, Mail Submission Agent, Mail Transfer Agent  
Mail User Agent, Mail Transfer Agent, Mail Delivery Agent  
Mail Submission Agent, Mail Transfer Agent, Mail Delivery Agent  
Mail User Agent, Mail Submission Agent, Mail Delivery Agent

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Mail User Agent, Mail Transfer Agent, Mail Delivery Agent

**Concept / Why:**  
MUA composes, MTA transports, MDA delivers to mailboxes.

**Reference:**  
Email Architecture Fundamentals
</details>

---

## Q50. The LDAP protocol is used to:

Share resources, such as files and printers, between Windows and Linux platforms  
Resolve host names into IP addresses  
Manage network configuration, such as IP addresses, for client systems  
Maintain and share directory information  
None of the above

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Maintain and share directory information

**Concept / Why:**  
LDAP is specifically designed for directory services, not resource sharing or DNS.

**Reference:**  
LDAP Protocol Specification
</details>

---

## Q51. Postfix is considered to be primarily a:

Mail Transfer Agent  
Mail Submission Agent  
Mail User Agent  
Mail Delivery Agent

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Mail Transfer Agent

**Concept / Why:**  
Postfix's core function is routing email between servers (MTA). While it can do limited MDA functions, that's not its primary role.

**Reference:**  
Postfix Architecture Documentation
</details>

---

## Q52. Enter the command line to look up the MX record for the domain "happy.org" using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host -t MX happy.org`

**Concept / Why:**  
The `-t MX` option specifies a mail exchanger record query.

**Reference:**  
DNS Mail Configuration Lab
</details>

---

## Q53. By default, which interface(s) does postfix listen?

localhost or 127.0.0.1  
The first ethernet adapter  
All the ethernet adapters  
All the ethernet adapters and localhost

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** localhost or 127.0.0.1

**Concept / Why:**  
Default Postfix installations only listen on loopback for security until properly configured.

**Reference:**  
Postfix Basic Configuration
</details>

---

## Q54. Enter the command line to look up the PTR record for "172.16.30.167" using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `host 167.30.16.172.in-addr.arpa`

**Concept / Why:**  
The host command requires the reversed IP format for PTR lookups.

**Reference:**  
DNS Reverse Lookup Procedures
</details>

---

## Q55. When setting up name-based virtual hosts, the Apache configuration requires:

One DocumentRoot directive for each virtual host and one ServerName directive  
One DocumentRoot directive and one ServerName directive  
One DocumentRoot directive for each virtual host and one ServerName directive for each virtual host  
One DocumentRoot directive and one ServerName directive for each virtual host

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** One DocumentRoot directive for each virtual host and one ServerName directive for each virtual host

**Concept / Why:**  
Each VirtualHost block needs its own DocumentRoot and ServerName.

**Reference:**  
Apache Virtual Hosts Best Practices
</details>

---

## Q56. Identify the correct MX record entry to be recorded in the zone file.

mail.example.lab. IN MX 10 172.16.30.200  
example.lab. IN MX 10 mail.example.lab.  
172.16.30.200 IN MX 10 mail.example.lab.  
mail.example.lab. IN MX 10 example.lab.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** example.lab. IN MX 10 mail.example.lab.

**Concept / Why:**  
MX records must point to hostnames (not IPs) and be at the domain level.

**Reference:**  
DNS Zone File Syntax
</details>

---

## Q57. Which of these are valid ways to send mail on the command line?

mail -s Test Email user8213@cst8213.lab  
mail -s TestEmail user8213@cst8213.lab  
mail -s Test Email user8213@172.16.30.167  
mail -s TestEmail user8213@172.16.30.167  
mail -s Test Email user8213@[172.16.30.167]  
mail -s TestEmail user8213@[172.16.30.167]  
mail -s Test Email user8213@host.cst8213.lab  
mail -s TestEmail user8213@host.cst8213.lab

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- mail -s TestEmail user8213@cst8213.lab  
- mail -s TestEmail user8213@[172.16.30.167]  
- mail -s TestEmail user8213@host.cst8213.lab  

**Concept / Why:**  
The subject (-s) must not contain spaces unless quoted, and IP addresses need brackets.

**Reference:**  
Command Line Email Tools
</details>

---

## Q58. Which of these commands will let you view the mail queue?

mailq -v  
mailq -p  
mailq  
postqueue -p  
postqueue -v

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- mailq  
- postqueue -p  

**Concept / Why:**  
Both commands show the mail queue, with postqueue being the modern Postfix version.

**Reference:**  
Postfix Queue Management
</details>

---

## Q59. Which mail server is the masquerading feature setup on?

inbound  
outbound

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** outbound

**Concept / Why:**  
Masquerading rewrites sender addresses on outgoing mail.

**Reference:**  
Postfix Address Rewriting
</details>

---

## Q60. Match the iptables targets with the description.

1. DROP  
2. REJECT  
3. RETURN  
4. ACCEPT  

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
1. Drop the packet. No reply to the source.  
2. Reject the packet. Reply with appropriate ICMP message  
3. The chain policy determines the fate of the packet  
4. Let the packet through  

**Concept / Why:**  
These are fundamental packet disposition actions in netfilter.

**Reference:**  
iptables Targets Manual
</details>

---

# Linux System Administration Review Questions (61-70)

## Q61. Which apache configuration option specifies the port Apache listens on?

ListenPort  
Port  
Listen  
80

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Listen

**Concept / Why:**  
The `Listen` directive configures which ports and IP addresses Apache binds to.

**Reference:**  
Apache Core Configuration Directives
</details>

---

## Q62. The base/suffix for happy.org can be setup using the following object class:

top  
inetOrgPerson  
domain  
person

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** domain

**Concept / Why:**  
The domain object class is specifically for DNS domain components in LDAP.

**Reference:**  
LDAP Schema for DNS
</details>

---

## Q63. Enter the command line to resolve the A record for "www.happy.org" using your professor's DNS at 172.16.30.167 using your preferred command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig @172.16.30.167 www.happy.org` or `host www.happy.org 172.16.30.167`

**Concept / Why:**  
The `@` syntax in dig or specifying the DNS server IP in host directs queries to a specific nameserver.

**Reference:**  
DNS Query Tools Advanced Usage
</details>

---

## Q64. Consistency of directory information across replicated LDAP servers is crucial while consistency of data stored in transactional databases is not.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
Both LDAP directories and transactional databases require data consistency, though their synchronization methods differ.

**Reference:**  
LDAP Replication Fundamentals
</details>

---
## Q65. Identify the error in the following LDIF entry:

dn: cn=Sarah Jones,ou=people,dc=example.com  
objectclass: inetorgperson  
cn: Sarah Jones  
sn: Jones  
mail: Sarah.Jones@example.com  
mail: sjones@example.com

There is no error  
There can only be one mail attribute, not two  
The dc attribute does not have a valid value  
The syntax for the attributes should use an = sign, not a colon, as in sn=Jones

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** There is no error

**Concept / Why:**  
LDAP allows multiple mail attributes, and the colon syntax is correct in LDIF files.

**Reference:**  
LDAP Data Interchange Format
</details>
---

## Q66. The default sshd_config shipped with OpenSSH is to specify options with their default values commented.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
OpenSSH documents default values as comments for clarity in the configuration file.

**Reference:**  
SSH Server Configuration Guide
</details>

---

## Q67. You use DNS or /etc/hosts to test your apache virtual hosts remotely.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
/etc/hosts only affects local name resolution. Remote testing requires proper DNS.

**Reference:**  
Apache Virtual Host Testing
</details>

---

## Q68. Enter the command line to look up the MX record for the domain "happy.org" using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=MX happy.org`

**Concept / Why:**  
The `-type=MX` option queries mail exchanger records specifically.

**Reference:**  
Email Infrastructure Testing
</details>

---

## Q69. Which command(s) shows all interface configurations?

ip addr show ens33 ens34  
ip addr show  
ip addr  
ip addr show all  
ip show  
ip

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- ip addr show  
- ip addr  

**Concept / Why:**  
Both commands display all interfaces when no specific interface is specified.

**Reference:**  
Linux Network Troubleshooting
</details>

---

## Q70. Which sshd configuration options control the use of password authentication?

PasswordAuthentication  
RSAAuthentication  
PermitRootLogin  
AuthorizedKeysFile  
PubkeyAuthentication

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** PasswordAuthentication

**Concept / Why:**  
This is the primary directive controlling password-based authentication.

**Reference:**  
SSH Authentication Methods
</details>

---

## Q71. Which of these utility programs can modify entries to an LDAP DIT?

ldapadd  
ldapmodify  
ldapdelete  
ditadd  
ditmodify  
ditdelete

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- ldapmodify  
- ldapdelete  

**Concept / Why:**  
These are the standard LDAP utilities for modifying (ldapmodify) and removing (ldapdelete) directory entries.

**Reference:**  
LDAP Data Management Tools
</details>

---

## Q72. Which utility will best verify basic network connectivity?

ping  
netstat  
ss  
ip  
All of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ping

**Concept / Why:**  
ping is specifically designed for connectivity testing via ICMP echo requests.

**Reference:**  
Network Diagnostics Fundamentals
</details>

---

## Q73. What is the rpm command line that lists all the files that are part of the installed package "foobar"?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `rpm -ql foobar`

**Concept / Why:**  
The `-q` queries packages and `-l` lists files contained in the package.

**Reference:**  
RPM Package Manager Guide
</details>

---

## Q74. To verify the mail server of the domain example.lab based on the MX record the following dig command is used:

dig MX mail.example.lab  
dig mail.example.lab  
dig MX example.lab  
dig mx.example.lab

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** dig MX example.lab

**Concept / Why:**  
MX records are queried at the domain level, not the mail server hostname level.

**Reference:**  
DNS Mail Server Verification
</details>

---

## Q75. An "outbound" only mail server typically "hosts" email for its domain.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
Outbound-only servers relay mail but don't receive/host mail for domains.

**Reference:**  
Mail Server Architecture Types
</details>

---

## Q76. Which command(s) show all listening TCP ports?

netstat -lptn  
ss -lptn  
ip listen  
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- netstat -lptn  
- ss -lptn  

**Concept / Why:**  
Both commands show listening (-l) TCP (-t) ports with numeric (-n) output and process info (-p).

**Reference:**  
Network Service Enumeration
</details>

---

## Q77. Enter the command line to look up the PTR record for "172.16.31.167" on your master DNS (172.16.30.167) using the dig command from another Linux machine.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig @172.16.30.167 -x 172.16.31.167`

**Concept / Why:**  
The `@` specifies the DNS server to query, and `-x` performs the reverse lookup.

**Reference:**  
Advanced DNS Troubleshooting
</details>

---

## Q78. Match the iptables commands with the description.

List rules  
Flush rules  
Insert rule  
Replace rule  
Append rule  
Help

1. -I  
2. -A  
3. -R  
4. -L  
5. -F  
6. -h

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
1. Insert rule  
2. Append rule  
3. Replace rule  
4. List rules  
5. Flush rules  
6. Help  

**Concept / Why:**  
These are fundamental iptables operations for rule management.

**Reference:**  
iptables Command Reference
</details>

---

## Q79. Match the options for ss (or netstat) with the description.

show TCP ports  
programs & pids  
listening  
numeric output

1. -l  
2. -p  
3. -t  
4. -n

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
1. listening  
2. programs & pids  
3. show TCP ports  
4. numeric output  

**Concept / Why:**  
These are the standard ss/netstat options for service discovery.

**Reference:**  
Network Socket Statistics
</details>

---

## Q80. Which of these utility programs can add entries to an LDAP DIT?

ldapdelete  
ditadd  
ldapmodify  
ditmodify  
ditdelete  
ldapadd

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- ldapadd  
- ldapmodify  

**Concept / Why:**  
ldapadd is for new entries, ldapmodify can add attributes to existing entries.

**Reference:**  
LDAP Data Manipulation Tools
</details>

---

## Q81. Write the command used to display the running log file for the Postfix mail server:

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `tail -f /var/log/maillog`

**Concept / Why:**  
Postfix logs mail delivery events in real-time to maillog, and `tail -f` follows new entries.

**Reference:**  
Postfix Log Analysis Guide
</details>

---

## Q82. Which of these issues may cause the slave DNS not to synchronize with the master DNS?

Incorrect specification in master or slave configuration file  
Zone serial number not higher than last sync  
Not having a file specified in the client configuration  
Network connectivity

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- Incorrect specification in master or slave configuration file  
- Zone serial number not higher than last sync  
- Network connectivity  

**Concept / Why:**  
All these can break zone transfers except the client configuration file which isn't relevant.

**Reference:**  
DNS Zone Transfer Troubleshooting
</details>

---

## Q83. Which of these utility programs can delete entries to an LDAP DIT?

ldapadd  
ditadd  
ditdelete  
ldapdelete  
ldapmodify  
ditmodify

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ldapdelete

**Concept / Why:**  
The specialized ldapdelete command removes entire entries from the directory.

**Reference:**  
LDAP Entry Deletion Procedures
</details>

---

## Q84. What is the default user used by apache while running?

apache  
cst8213  
The user that started apache  
root  
nobody

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** apache

**Concept / Why:**  
RHEL/CentOS create a dedicated 'apache' user for the web server process.

**Reference:**  
Apache Security Context
</details>

---

## Q85. Which file contains your default name servers?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/resolv.conf`

**Concept / Why:**  
The nameserver entries in resolv.conf define DNS resolution order.

**Reference:**  
Linux DNS Client Configuration
</details>

---

## Q86. Enter the command line to look up the NS record for the domain "happy.org" using the dig command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig NS happy.org`

**Concept / Why:**  
The NS query type returns authoritative nameservers for the domain.

**Reference:**  
DNS Authority Verification
</details>

---

## Q87. Enter the command line to look up the NS record for the domain "happy.org" on the teacher's DNS (172.16.30.167) using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=NS happy.org 172.16.30.167`

**Concept / Why:**  
Specifies both query type and target nameserver in one command.

**Reference:**  
nslookup Advanced Usage
</details>

---

## Q88. If object class inetOrgPerson is a subclass of object class person, the following applies:

Object class inheritance is not part of the LDAP protocol  
All attributes of person are inherited by inetOrgPerson, except the required attributes  
All attributes of person are inherited by inetOrgPerson, including the required attributes  
All attributes of inetOrgPerson are inherited by person

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** All attributes of person are inherited by inetOrgPerson, including the required attributes

**Concept / Why:**  
LDAP object class inheritance includes all parent class attributes.

**Reference:**  
LDAP Schema Inheritance
</details>

---

## Q89. Which command can be used to verify the HTTPD service is listening on the correct port?

ip  
netstat  
ss  
ifconfig  
ipconfig

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- netstat  
- ss  

**Concept / Why:**  
Both show listening services and their ports (netstat is legacy, ss is modern).

**Reference:**  
Web Server Port Verification
</details>

---

## Q90. Enter the command line to look up the NS record for the domain "happy.org" on the professor's DNS (172.16.30.167) using the dig command (without -t).

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig @172.16.30.167 happy.org NS`

**Concept / Why:**  
Placing NS after the domain implicitly sets the query type.

**Reference:**  
dig Command Shortcuts
</details>

---

## Q91. Apache fails to start due to an unknown directive in the configuration file. One possibility could be that the corresponding module is not loaded.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Many Apache directives require specific modules to be loaded (e.g., SSL directives need mod_ssl).

**Reference:**  
Apache Module Dependency Guide
</details>

---

## Q92. Practically, who should be able to look up a public DNS MX record?

The sending email server  
The receiving email server  
The user sending the email  
The user receiving the email  
None of these answers

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** The sending email server

**Concept / Why:**  
MTAs must query MX records to determine where to deliver outgoing mail.

**Reference:**  
Email Routing Fundamentals
</details>

---

## Q93. An object is created based on one object class. The object class must be:

Auxiliary  
Structural  
There is only one type of object class  
Abstract

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Structural

**Concept / Why:**  
All LDAP entries require exactly one structural class as their foundation.

**Reference:**  
LDAP Object Class Hierarchy
</details>

---

## Q94. Enter the command line to look up the MX record for the domain "happy.org" using the dig command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig MX happy.org`

**Concept / Why:**  
The MX query type returns mail exchanger records in order of preference.

**Reference:**  
DNS Mail Server Discovery
</details>

---

## Q95. Which command(s) verify sshd is listening on the configured port(s)?

netstat -lptn  
ss -lptn  
ip listen  
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- netstat -lptn  
- ss -lptn  

**Concept / Why:**  
Both commands show listening (-l) TCP (-t) ports with process info (-p) in numeric form (-n).

**Reference:**  
SSH Service Verification
</details>

---

## Q96. Which utility is used to add entries to LDAP from a properly configured LDIF file?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapadd`

**Concept / Why:**  
ldapadd is specifically designed for bulk loading LDIF data into the directory.

**Reference:**  
LDAP Data Import Procedures
</details>

---

## Q97. Which command displays interface configuration for ens160?

ip addr show ens160  
ip addr ens160  
addr  
ip show ens160  
ip ens160

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ip addr show ens160

**Concept / Why:**  
The modern ip command requires 'addr show' subcommands for interface details.

**Reference:**  
Network Interface Diagnostics
</details>

---

## Q98. Which utility is used to search the LDAP DIT?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapsearch`

**Concept / Why:**  
The specialized tool for querying LDAP directory information trees.

**Reference:**  
LDAP Query Operations
</details>

---

## Q99. Which of these command line utilities can be used to perform DNS lookups?

nslookup  
dig  
dns  
lookup  
host

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- nslookup  
- dig  
- host  

**Concept / Why:**  
These are the standard DNS query tools (dns/lookup are not valid commands).

**Reference:**  
DNS Troubleshooting Toolkit
</details>

---

## Q100. Which configuration file controls SELINUX?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/selinux/config`

**Concept / Why:**  
The main SELinux configuration file controlling the enforcement mode.

**Reference:**  
SELinux Administration Guide
</details>

---

# Linux System Administration Review Questions

## Q101. "Aliasing" is used to redirect email addressed to a generic account such as "webmaster" to a user account such as "arnold". As such the recipient address is rewritten by the receiving mail server.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Aliasing rewrites recipient addresses during mail delivery, typically mapping generic addresses to specific user mailboxes.

**Reference:**  
Postfix Address Rewriting Guide
</details>

---

## Q102. Match the iptables parameters with the description.

Source  
Out-bound interface  
In-bound interface  
Destination  
Port

- -s
- -d
- -p
- -i
- -o

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- Source: -s  
- Destination: -d  
- Port: -p  
- In-bound interface: -i  
- Out-bound interface: -o  

**Concept / Why:**  
These iptables options filter packets based on network characteristics.

**Reference:**  
iptables Filtering Parameters
</details>

---

## Q103. To send mail using the form user@domain.tld, where the mail server for the domain is mx.domain.tld, the A record for mx.domain.tld in the zone file for the domain is sufficient.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** False

**Concept / Why:**  
Both an MX record pointing to mx.domain.tld and its A record are required for proper mail delivery.

**Reference:**  
DNS for Email Services
</details>

---

## Q104. To locate an object in the DIT you use the _______ of the object.

RDN  
None of these choices  
FQDN  
DNS

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** None of these choices

**Concept / Why:**  
Objects are located by their Distinguished Name (DN), which includes the RDN but isn't listed as an option.

**Reference:**  
LDAP Naming Concepts
</details>

---

## Q105. Which apache block directive is used to configure virtual hosts?

Virtual  
MultiHost  
Multi  
VirtualHost  
Host

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** VirtualHost

**Concept / Why:**  
The `<VirtualHost>` container holds configuration specific to each virtual host.

**Reference:**  
Apache Virtual Host Configuration
</details>

---

## Q106. To setup the resolver on the client system to provide hostname resolution with LDAP in addition to static and DNS-style host name resolution, the following client configuration file has to be edited:

/etc/resolv.conf  
/etc/nsswitch.conf  
/etc/hosts  
/etc/services

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/nsswitch.conf

**Concept / Why:**  
The "hosts:" line in nsswitch.conf controls the resolution order (files/dns/ldap).

**Reference:**  
Name Service Switch Configuration
</details>

---

## Q107. You use DNS or /etc/hosts to test your apache virtual hosts locally.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Local testing can use /etc/hosts entries to simulate DNS resolution for virtual hosts.

**Reference:**  
Apache Local Development
</details>

---

## Q108. Assume that name-based virtual hosting is setup for the IP address 172.16.30.199 on a server with more than one interface. You want to display a web site when your web server is accessed using a different (and valid) IP address. To accomplish this you should:

Do nothing: the site of the first virtual host will automatically be displayed.  
Setup a "default" site in the virtual site section  
Setup a separate Apache to listen on the different IP address after making sure that the current Apache is not listening on that IP address.  
It cannot be done: you cannot setup a site for another interface when setting up virtual hosting for a given interface.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** Setup a "default" site in the virtual site section

**Concept / Why:**  
The default VirtualHost (usually first defined) handles requests that don't match other vhosts.

**Reference:**  
Apache Virtual Host Fallback
</details>

---

## Q109. Which utility will best verify basic network connectivity?

ping  
netstat  
ss  
ip  
All of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ping

**Concept / Why:**  
ping tests reachability at the most fundamental level using ICMP echo requests.

**Reference:**  
Network Diagnostics 101
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
The Content-Type HTTP header definitively declares the media type according to MIME standards.

**Reference:**  
HTTP Protocol Headers
</details>

---

## Q111. When trying to add an LDAP directory entry the operation is unsuccessful. One of the possible problems could be that the corresponding schema file is not included in the LDAP server configuration.

True  
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True

**Concept / Why:**  
Missing schema definitions would prevent creating entries using those object classes or attributes.

**Reference:**  
LDAP Schema Troubleshooting
</details>

---

## Q112. Which module must be loaded in order to use the DirectoryIndex option?

mod_base  
mod_data  
mod_index  
mod_dir  
mod_access  
mod_cache

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** mod_dir

**Concept / Why:**  
The DirectoryIndex directive is provided by mod_dir for directory request handling.

**Reference:**  
Apache Module Reference
</details>

---

## Q113. Easy one. Match these acronyms:

Envelope Sender  
Header Receiver  
Envelope Receiver  
Header Sender

- ES
- ER
- HS
- HR

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- Envelope Sender: ES  
- Envelope Receiver: ER  
- Header Sender: HS  
- Header Receiver: HR  

**Concept / Why:**  
These distinguish between envelope (SMTP) and header (message) addressing in email.

**Reference:**  
Email Architecture Components
</details>

---

## Q114. With "masquerading" the following addresses are typically rewritten.

ER  
HR  
HS  
ES

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ES

**Concept / Why:**  
Masquerading modifies the envelope sender (ES) to present a consistent domain.

**Reference:**  
Postfix Address Rewriting
</details>

---

## Q115. What is the default "ServerRoot" for apache?

/home/apache  
/etc/httpd  
/var/httpd  
/var/www/  
/var/www/httpd

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** /etc/httpd

**Concept / Why:**  
This is the standard ServerRoot (base directory) for Apache in RHEL/CentOS.

**Reference:**  
Apache File Layout
</details>

---

## Q116. An LDAP client, such as ldapsearch, requires at a minimum the following information to search an LDAP directory server.

An IP address (or hostname) for the LDAP server  
A base/suffix for the DIT  
A DN for the object to search  
A DNS record for the server

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):**  
- An IP address (or hostname) for the LDAP server  
- A base/suffix for the DIT  

**Concept / Why:**  
These are the minimum required to perform searches (authentication may be needed for some queries).

**Reference:**  
LDAP Client Configuration
</details>

---
