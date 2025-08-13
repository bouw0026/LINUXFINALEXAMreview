# Linux System Administration Review Questions


## Q1. If a directive in your Apache configuration is not recognized by Apache, the most
likely reason is that the module that supports the directive is missing.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True.


**Concept / Why:**  
& Reference</summary> 
Explanation: Apache’s functionality is modular – many configuration directives are provided by loadable modules. If you use a directive that Apache doesn’t recognize, it usually means the module for that directive isn’t enabled or installed. For example, SSL-related directives won’t work unless the SSL module (mod_ssl) is loaded. Ensuring the appropriate module is loaded (via LoadModule or installing the module) will resolve the unrecognized directive issue.

</details>

---


## Q2. The apache server implements the following protocol:

HTTP
URI
APACHE
None of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `HTTP (HyperText Transfer Protocol).`


**Concept / Why:**  
& Reference</summary> 
Explanation: Apache is a web server that serves content over the HTTP protocol (and by extension HTTPS for secure HTTP). It listens on the standard HTTP port (80) to handle web requests. In other words, Apache’s primary role is to implement the HTTP protocol, delivering web pages to clients (web browsers). The other options (URI, “APACHE”) are not network protocols – HTTP is the correct one.

</details>

---


## Q3. Which key is used to encrypt in order to prove authenticity using public key
cryptography?

Private key
Public key
Foreign key
Shared key

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `The private key.`


**Concept / Why:**  
& Reference</summary> 
Explanation: To prove authenticity (as in digital signatures), the sender uses their private key to encrypt/sign the data. Since only the legitimate holder possesses the private key, this act proves the data’s origin. The recipient uses the corresponding public key to decrypt/verify the signature. This public-key cryptography scheme ensures that the message integrity and origin (authenticity) are verifiable. In contrast, encrypting with a public key provides confidentiality (anyone can encrypt to send to the private key holder, but that doesn’t prove identity). Thus, the private key is used for authenticity proofs.

</details>

---


## Q4. Which apache configuration directive configures logging of all website accesses?

TransferLog
Transfer
AccessLog
Access

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** TransferLog.


**Concept / Why:**  
& Reference</summary> 
Explanation: Apache records all HTTP requests (accesses) in its access log. The classic directive for this is TransferLog, which specifies the file where all requests should be logged. (In newer Apache versions, the CustomLog directive is used for flexible logging, but functionally it serves the same purpose of logging accesses.) For example, an Apache virtual host might use CustomLog /path/to/access.log combined to log all accesses in combined format. Among the given choices, TransferLog is the correct directive that enables logging of all website hits. The options “AccessLog” or “Access” are not actual Apache directives.

</details>

---


## Q5. 

Enter the command line to look up the NS record for the domain "happy.org" using
the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup -type=NS happy.org`


**Concept / Why:**  
& Reference</summary> 
Explanation: The nslookup utility can query specific DNS record types by using the -type=NS option (or -q=NS). In this case, we specify the domain (happy.org) and request NS records, which will return the nameservers authoritative for happy.org. For example, the command above will list the DNS servers (NS records) for the happy.org domain. (Note: While modern Linux administration often prefers dig or host, nslookup is still usable for DNS queries.)

</details>

---


## Q6. Which file controls static hostname resolution?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `The /etc/hosts file.`


**Concept / Why:**  
& Reference</summary> 
Explanation: /etc/hosts is the local file for static hostname resolution on a Linux system. This file contains mappings of hostnames to IP addresses that the system checks before consulting any DNS server. For example, it usually includes an entry for localhost (mapping to 127.0.0.1) and any other static name-to-IP mappings needed. In summary, /etc/hosts allows the system to resolve hostnames without querying DNS, according to the static entries you place there.

</details>

---


## Q7. What is the command used to start service "foobar" upon system boot up?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl enable foobar`


**Concept / Why:**  
& Reference</summary> 
Explanation: To configure a service to start at boot (in a systemd-based Linux like RHEL 8), you use systemctl enable <service>. This command creates the necessary links so that the service (here “foobar”) will automatically start on system startup. (This is distinct from systemctl start, which starts the service immediately but doesn’t enable auto-start.) By enabling a service, you ensure it launches on every boot without manual intervention. For example, systemctl enable foobar will mark the “foobar” service to load on boot.

</details>

---


## Q8. Generally, you should put an IPv4 entry and IPv6 entry for your localhost in you
hosts file.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** True.


**Concept / Why:**  
& Reference</summary> 
Explanation: It is best practice to have both the IPv4 and IPv6 loopback addresses defined for “localhost” in /etc/hosts. Typically, you will have an entry 127.0.0.1 localhost (IPv4 loopback) and an entry ::1 localhost (IPv6 loopback) in the hosts file. Including both ensures that the hostname “localhost” resolves properly on systems using either IPv4 or IPv6. Most modern Linux distributions include both by default, which helps avoid issues with programs that may use IPv6 by default. In short, True – you should list both 127.0.0.1 and ::1 for localhost in your hosts file.

</details>

---


## Q9. Enter the command line to look up the PTR record for "172.16.30.167" using the dig
command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig -x 172.16.30.167`


**Concept / Why:**  
& Reference</summary> 
Explanation: The dig command’s -x option performs a reverse DNS lookup (i.e. queries for a PTR record). So, dig -x 172.16.30.167 will ask DNS for the PTR record corresponding to the IP 172.16.30.167. The PTR record (if configured) will reveal the hostname associated with that IP address. This is a standard way to verify reverse DNS mapping. According to the course notes, using dig -x is the proper method for reverse lookups. (If the DNS is set up with a reverse zone for 172.16.30.x, this query should return a hostname.)

</details>

---


## Q10. Enter the command line to look up the PTR record for "172.16.31.167" on your slave
DNS (172.16.31.167) using the dig command from another Linux machine.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig @172.16.31.167 -x 172.16.31.167`


**Concept / Why:**  
& Reference</summary> 
Explanation: Here we want to query the slave DNS server at 172.16.31.167 for the PTR record of the IP 172.16.31.167. In dig, you can specify the DNS server to ask by using @<server-ip>. So the command is:
dig @172.16.31.167 -x 172.16.31.167.
Breaking it down: -x 172.16.31.167 asks for the PTR record of 172.16.31.167 (reverse lookup), and @172.16.31.167 directs the query to the DNS server at that address (which is the slave). This ensures we are checking the slave DNS directly. The lab instructions explicitly demonstrate using dig -x for reverse lookups and using the @ syntax to query a specific nameserver, which is exactly what we combine in this command.

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

**Answer (MC style):** who


**Concept / Why:**  
</summary> 
Concept / Why:
who displays the list of users currently logged into the system, along with terminal info and login time. It doesn’t show historical logins (that’s last).

</details>

---


## Q12. Match the commands with the description.
1. systemctl list-units						displays all active units
2. systemctl list-unit-files				displays all units
3. systemctl start service					start service immediately
4. systemctl get-default					display the default target
5. journalctl -u network					display log messages for the network service
6. journalctl -k							display kernel messages
7. systemctl list-units -t service			lists all running services

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** whoami


**Concept / Why:**  
</summary> 
Concept / Why:
whoami outputs the effective user name associated with the current session, useful for confirming identity after privilege escalation.

</details>

---


## Q13. Virtual hosts in Apache are used to:

Create multiple copies of the same web site on multiple server systems
Host web sites without the need to setup DNS entries for multiple domain names
Setup referrals to other web servers
Have web sites for multiple sites on the same server system

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ls -a`


**Concept / Why:**  
</summary> 
Concept / Why:
The -a flag includes all entries, even those starting with a dot (.), which are hidden by default.

</details>

---


## Q14. Which file must be modified on the master DNS to allow master/slave operation for
the package bind?

/etc/bind.conf
/etc/sysconfig/bind.conf
/etc/named.conf
/etc/sysconfig/named.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** pwd


**Concept / Why:**  
</summary> 
Concept / Why:
pwd prints the absolute pathname of the current working directory, based on the shell’s environment.

</details>

---


## Q15. The aliasing feature is used to forward email of a local user to a different email
account. The /etc/aliases file is consulted by which mail server?

inbound
outbound

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `Moves up one directory level.`


**Concept / Why:**  
</summary> 
Concept / Why:
.. is a relative pathname for the parent directory. cd .. changes the working directory to it.

</details>

---


## Q16. What does the error message "mail loops back to me" typically indicate is wrong in
the postfix configuration file?

The MX record is incorrect (missing or pointing to an incorrect host
Postfix is listening only on the loopback interface
Postfix is listening only on port 25
"relay_domains" is incorrectly set
"mydestination" is incorrectly configured

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `Detailed list including permissions, owner, group, size, and timestamps.`


**Concept / Why:**  
</summary> 
Concept / Why:
-l triggers the “long” listing format, useful for file permissions and metadata inspection.

</details>

---


## Q17. Name-based virtual hosting is possible because:
The client connection to the server is based on hostname and port number.
The client connection to the server is based on IP address and port number, and the hostname is included in the client request.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `Creates an empty file or updates its timestamp.`


**Concept / Why:**  
</summary> 
Concept / Why:
touch creates the file if it doesn’t exist; if it exists, it updates the access and modification times.

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

**Answer (MC style):** rm


**Concept / Why:**  
</summary> 
Concept / Why:
rm deletes files (and with -r, directories). It does not move them to trash—deletion is permanent.

</details>

---


## Q19. Which command(s) verify bind(DNS) is listening of the configured port(s)?

netstat -lptn
ss -lptn
ip listen
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** mkdir


**Concept / Why:**  
</summary> 
Concept / Why:
mkdir creates directories at the specified path. Use -p to create parent directories as needed.

</details>

---


## Q20. The only source for web documents that a server can map a URL to is given by the
DocumentRoot directive.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** cp


**Concept / Why:**  
</summary> 
Concept / Why:
cp copies files from source to destination. With -r, it can copy directories recursively.

</details>

---


## Q21. 

Enter the command line to look up the PTR record for "172.16.31.167" on the
teacher's slave DNS (172.16.31.167) using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** mv


**Concept / Why:**  
</summary> 
Concept / Why:
mv moves a file from one location to another or renames it if the source and destination are on the same filesystem.

</details>

---


## Q22. 

Enter the command line to look up the NS record for the domain "happy.org" using
the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** cat


**Concept / Why:**  
</summary> 
Concept / Why:
cat reads and outputs the contents of one or more files to standard output, often used for quick viewing.

</details>

---


## Q23. Assuming you do not configure the configuration file to allow other users, who is
allowed to add/modify/delete entries in the LDAP database?

user8213
root
Without further configuration, all users can add/modify/delete entries
Idapadm
The LDAP adminstrator

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** head


**Concept / Why:**  
</summary> 
Concept / Why:
head displays the first 10 lines of a file by default. The number of lines can be changed with the -n option.

</details>

---


## Q24. Which file contains the main configuration file for apache?

/etc/httpd/conf/http.conf
/etc/http/conf/http.conf
/etc/httpd/conf/httpd.conf
/etc/http/conf/httpd.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** tail


**Concept / Why:**  
</summary> 
Concept / Why:
tail displays the last 10 lines by default and is often used with -f to follow file updates (like logs).

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

**Answer (MC style):** grep


**Concept / Why:**  
</summary> 
Concept / Why:
grep searches for patterns within files using regular expressions, printing matching lines.

</details>

---


## Q26. An attribute is defined by a set of object classes.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** chmod


**Concept / Why:**  
</summary> 

Concept / Why:
chmod changes read, write, and execute permissions for owner, group, and others using symbolic or numeric notation.

</details>

---


## Q27. Which command displays the default route?

ip route
ip default
ss route
ss show route

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** chown


**Concept / Why:**  
</summary> 
Concept / Why:
chown modifies the owner (and optionally group) of a file. Requires root privileges for most changes.

</details>

---


## Q28. Based on the following list of criteria determine which ones have to be satisfied for
an inbound mail server.

An MX record has to point to the mail server.
Masquerading is applied on all received email.
The server has to be setup to "host" for the domain.
The server has to be setup to "relay" for the domain.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** du


**Concept / Why:**  
</summary> 
Concept / Why:
du shows the space used by files and directories, optionally summarizing totals with -s.

</details>

---


## Q29. What is the command used to prevent service "foobar" starting automatically upon
system boot up?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** df


**Concept / Why:**  
</summary> 
Concept / Why:
df reports file system disk space usage in blocks, kilobytes, or human-readable formats (-h).

</details>

---


## Q30. The SMTP protocol is used to:

Share resources, such as files and printers, between Windows and Linuxplatforms
None of these choices
Maintain and share directory information
Resolve host names into IP addresses
Manage network configuration for client systems

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ps


**Concept / Why:**  
</summary> 
Concept / Why:
ps lists currently running processes. Options like aux display all processes with full details.

</details>

---


## Q31. Which of these firewalls are available on CENTOS 7?

firewalld
iptables
secured
ipchains

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** top


**Concept / Why:**  
</summary> 
Concept / Why:
top provides a real-time, updating view of running processes, CPU usage, memory consumption, and system load.

</details>

---


## Q32. 

Enter the command line to look up the PTR record for "172.16.30.167" using the
nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** man


**Concept / Why:**  
</summary> 
Concept / Why:
man opens the manual pages for commands, showing syntax, options, and descriptions. It’s the built-in Linux reference.

</details>

---


## Q33. 

Enter the command line to look up the PTR record for "172.16.31.167" on the
teacher's master DNS (172.16.30.167) using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** which


**Concept / Why:**  
</summary> 
Concept / Why:
which returns the full path of a command’s executable by searching the directories in $PATH.

</details>

---


## Q34. Assuming you are already serving two domains, how many additional virtual hosts
have to be set up in Apache to provide websites for the domains happy.org,
peachy.org and sunny.org?

Zero (0)
One (1)
Three (3)
It cannot be done.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** passwd


**Concept / Why:**  
</summary> 
Concept / Why:
passwd updates a user’s password and optionally their password aging information.

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

**Answer (MC style):** `ifconfig (or ip addr on modern systems)`


**Concept / Why:**  
</summary> 
Concept / Why:
ifconfig displays interface names, IP addresses, netmasks, and status. It’s been largely replaced by ip addr in newer distros.

</details>

---


## Q36. Which file contains configuration for the DNS client (resolver)?

~/resolv.conf
/etc/resolver.conf
/etc/sysconfig/resolve.conf
/etc/resolv.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ping


**Concept / Why:**  
</summary> 
Concept / Why:
ping sends ICMP echo requests to test host reachability and measure round-trip time.

</details>

---


## Q37. An object can be created using exactly one auxiliary class and any number, including
zero, structural classes.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `traceroute (or tracepath)`


**Concept / Why:**  
</summary> 
Concept / Why:
traceroute maps the path packets take, listing each hop and its response time, useful for network troubleshooting.

</details>

---


## Q38. Enter the command line to look up the NS record for the domain "happy.org" on the
teacher's DNS (172.16.30.167) using the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `netstat (or ss)`


**Concept / Why:**  
</summary> 
Concept / Why:
netstat lists open sockets, routing tables, and interface statistics. On modern systems, ss is preferred.

</details>

---


## Q39. Which file must be modified on the slave DNS to allow master/slave operation for
the package bind?

/etc/sysconfig/bind.conf
/etc/sysconfig/named.conf
/etc/bind.conf
/etc/named.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** wget


**Concept / Why:**  
</summary> 
Concept / Why:
wget retrieves files from web or FTP servers non-interactively, useful for scripting automated downloads.

</details>

---


## Q40. HTTPS is:

HTTP that uses the TLS/SSL layer for security services
A different application layer protocol from HTTP
HTTP that includes additional security modules defined by the HTTPS protocol
A newer version of the HTTP protocol

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** scp


**Concept / Why:**  
</summary> 
Concept / Why:
scp uses SSH to copy files securely between hosts. It encrypts both the command and data during transfer.

</details>

---


## Q41. Match the iptables other options with the description.

1. -V					Verbose
2. -n					Numeric
3. -- line-numbers		Show line numbers

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** ssh


**Concept / Why:**  
</summary> 
Concept / Why:
ssh opens a secure, encrypted shell session on a remote host, replacing older insecure tools like telnet.

</details>

---


## Q42. Record the command used to verify that the service "foobar" is currently running.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** lsmod


**Concept / Why:**  
</summary> 
Concept / Why:
lsmod displays the status of loaded kernel modules, including their dependencies and usage counts.

</details>

---


## Q43. 

Enter the command line to resolve the A record for "www.happy.org" using your
default resolver configuration.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** modprobe


**Concept / Why:**  
</summary> 
Concept / Why:
modprobe loads kernel modules and their dependencies dynamically, simplifying manual insmod operations.

</details>

---


## Q44. You wish to configure apache to serve two "Virtual Hosts", happy.lab & grumpy.lab.
What is the minimum number of zone files required in your DNS?
one
two
three
four

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** rmmod


**Concept / Why:**  
</summary> 
Concept / Why:
rmmod unloads a kernel module from memory. Often replaced by modprobe -r for dependency handling.

</details>

---


## Q45. Record the command that lists all running services.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** dmesg


**Concept / Why:**  
</summary> 
Concept / Why:
dmesg prints kernel ring buffer messages, often showing hardware initialization and driver load events.

</details>

---


## Q46. Which command is used to show or set your hostname?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `yum install (or dnf install on newer systems)`


**Concept / Why:**  
</summary> 
Concept / Why:
yum and dnf are package managers for RHEL-based systems, resolving dependencies automatically during installation.

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

**Answer (MC style):** `yum update (or dnf upgrade)`


**Concept / Why:**  
</summary> 
Concept / Why:
This command updates all packages to the latest available versions from enabled repositories.

</details>

---


## Q48. Which file your hostname resolution order?
/etc/nsswitch.conf

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `yum remove (or dnf remove)`


**Concept / Why:**  
</summary> 
Concept / Why:
Removes the package and optionally unused dependencies, freeing disk space.

</details>

---


## Q49. The three required components to have a functional email service are:

Mail User Agent, Mail Submission Agent, Mail Transfer Agent
Mail User Agent, Mail Transfer Agent, Mail Delivery Agent
Mail Submission Agent, Mail Transfer Agent, Mail Delivery Agent
Mail User Agent, Mail Submission Agent, Mail Delivery Agent

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl start <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
systemctl is the systemd service manager; start activates the service without enabling it on boot.

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

**Answer (MC style):** `systemctl enable <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
enable creates a symbolic link in systemd configuration to auto-start the service during system boot.

</details>

---


## Q51. Postfix is considered to be primarily a:

Mail Transfer Agent
Mail Submission Agent
Mail User Agent
Mail Delivery Agent

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl stop <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
stop halts a running service without preventing it from starting on the next boot (unless disabled separately).

</details>

---


## Q52. 

Enter the command line to look up the MX record for the domain "happy.org" using
the host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl disable <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
disable removes the boot-time symbolic link so the service won’t auto-start after reboots.

</details>

---


## Q53. By default, which interface(s) does postfix listen?

localhost or 127.0.0.1
The first ethernet adapter
All the ethernet adapters
All the ethernet adapters and localhost

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl restart <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
restart is a stop followed by a start in one step, useful after config changes.

</details>

---


## Q54. 

Enter the command line to look up the PTR record for "172.16.30.167" using the
host command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl status <service>`


**Concept / Why:**  
</summary> 
Concept / Why:
Displays whether the service is active, its PID, last log entries, and exit codes.

</details>

---


## Q55. When setting up name-based virtual hosts, the Apache configuration requires:
One DocumentRoot directive for each virtual host and one ServerName directive
One DocumentRoot directive and one ServerName directive
One DocumentRoot directive for each virtual host and one ServerName directive for each virtual host
One DocumentRoot directive and one ServerName directive for each virtual host

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `setenforce 0`


**Concept / Why:**  
</summary> 
Concept / Why:
This command relaxes SELinux policy enforcement without disabling SELinux entirely, useful for troubleshooting.

</details>

---


## Q56. Identify the correct MX record entry to be recorded in the zone file.

mail.example.lab. IN MX 10 172.16.30.200
example.lab. IN MX 10 mail.example.lab.
172.16.30.200 IN MX 10 mail.example.lab.
mail.example.lab. IN MX 10 example.lab.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `Edit /etc/selinux/config and set SELINUX=permissive`


**Concept / Why:**  
</summary> 
Concept / Why:
Changing the config file ensures the setting persists across reboots.

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

**Answer (MC style):** getenforce


**Concept / Why:**  
</summary> 
Concept / Why:
getenforce returns Enforcing, Permissive, or Disabled to show the active SELinux mode.

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

**Answer (MC style):** chcon


**Concept / Why:**  
</summary> 
Concept / Why:
chcon modifies SELinux security context labels for files without altering default policy settings.

</details>

---


## Q59. Which mail server is the masquerading feature is setup on?
inbound		 ?
outbound

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** restorecon


**Concept / Why:**  
</summary> 
Concept / Why:
restorecon re-applies the default SELinux context from policy to the file path.

</details>

---


## Q60. Match the iptables targets with the description.

1. DROP		Drop the packet. No reply to the source.
2. REJECT	Reject the packet. Reply with appropriate ICMP message
3. RETURN	The chain policy determines the fate of the packet
4. ACCEPT	Let the packet through

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ls -Z`


**Concept / Why:**  
</summary> 
Concept / Why:
ls -Z shows SELinux labels alongside normal file listing, helping verify policy enforcement.

</details>

---


## Q61. Which apache configuration option specifies the port Apache listens on?

ListenPort
Port
Listen
80

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --list-all-zones`


**Concept / Why:**  
</summary> 
Concept / Why:
Lists every defined firewalld zone and the services, ports, and interfaces assigned to each.

</details>

---


## Q62. The base/suffix for happy.org can be setup using the following object class:

top
inetOrgPerson
domain
person

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --list-all`


**Concept / Why:**  
</summary> 
Concept / Why:
Shows services, ports, sources, and interfaces bound to the default active zone.

</details>

---


## Q63. 

Enter the command line to resolve the A record for "www.happy.org" using your
professor's DNS at 172.16.30.167 using your preferred command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --permanent --add-service=http`


**Concept / Why:**  
</summary> 
Concept / Why:
Allows HTTP traffic persistently by enabling the predefined http service in firewalld.

</details>

---


## Q64. Consistency of directory information across replicated LDAP servers is crucial while
consistency of data stored in transactional databases is not.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --reload`


**Concept / Why:**  
</summary> 
Concept / Why:
Applies configuration changes from permanent rules without restarting the service.

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

**Answer (MC style):** `firewall-cmd --add-service=https`


**Concept / Why:**  
</summary> 
Concept / Why:
Enables HTTPS access until the next reload or reboot without altering permanent settings.

</details>

---


## Q66. The default sshd_config shipped with OpenSSH is to specify options with their
default values commented.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --permanent --remove-service=ssh`


**Concept / Why:**  
</summary> 
Concept / Why:
Blocks SSH traffic persistently by removing its service entry from the firewall.

</details>

---


## Q67. You use DNS or /etc/hosts to test your apache virtual hosts remotely.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --get-default-zone`


**Concept / Why:**  
</summary> 
Concept / Why:
Reveals the zone where unassigned network interfaces are placed by default.

</details>

---


## Q68. 

Enter the command line to look up the MX record for the domain "happy.org" using
the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `firewall-cmd --set-default-zone=<zone>`


**Concept / Why:**  
</summary> 
Concept / Why:
Changes the default security zone for future interface assignments.

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

**Answer (MC style):** `firewall-cmd --get-services`


**Concept / Why:**  
</summary> 
Concept / Why:
Displays all predefined services that can be added as firewall rules.

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

**Answer (MC style):** `firewall-cmd --query-service=<service>`


**Concept / Why:**  
</summary> 
Concept / Why:
Returns yes if the service is permitted in the current active zone; no otherwise.

</details>

---


## Q71. Which of these utility programs can modify entries to an LDAP DIT?

Idapadd
Idapmodify
Idapdelete
ditadd
ditmodify
ditdelete

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ip addr show`


**Concept / Why:**  
</summary> 
Concept / Why:
Lists all interfaces, IPs, MAC addresses, and interface states. Preferred over ifconfig in modern systems.

</details>

---


## Q72. Which utility will best verify basic network connectivity?

ping
netstat
55
ip
All of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ip route show`


**Concept / Why:**  
</summary> 
Concept / Why:
Displays routes, gateways, and metrics that determine packet forwarding.

</details>

---


## Q73. What is the rpm command line that lists all the files that are part of the installed
package "foobar"?
A/

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ping <host>`


**Concept / Why:**  
</summary> 
Concept / Why:
Confirms whether a host is reachable and measures packet loss and latency.

</details>

---


## Q74. To verify the mail server of the domain example.lab based on the MX record the
following dig command is used:

dig MX mail.example.lab
dig mail.example.lab
dig MX example.lab
dig mx.example.lab

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `traceroute <host>`


**Concept / Why:**  
</summary> 
Concept / Why:
Lists each hop along the route to the destination, useful for diagnosing network delays.

</details>

---


## Q75. An "outbound" only mail server typically "hosts" email for its domain.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dig <domain>`


**Concept / Why:**  
</summary> 
Concept / Why:
Queries DNS servers for records such as A, AAAA, MX, and more.

</details>

---


## Q76. Which command(s) show all listening TCP ports?

netstat -Iptn
5s -Iptn
ip listen
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `nslookup <domain>`


**Concept / Why:**  
</summary> 
Concept / Why:
Checks DNS resolution through the configured /etc/resolv.conf settings.

</details>

---


## Q77. 

Enter the command line to look up the PTR record for "172.16.31.167" on your
master DNS (172.16.30.167) using the dig command from another Linux machine.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ss -tuln`


**Concept / Why:**  
</summary> 
Concept / Why:
Shows TCP/UDP sockets in listening state, with ports and IP bindings.

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

**Answer (MC style):** `telnet <host> <port>`


**Concept / Why:**  
</summary> 
Concept / Why:
Useful for verifying service availability on a specific port (e.g., SMTP on port 25).

</details>

---


## Q79. Match the options for ss (or netstat) with the description.
show TCP ports
programs & pids
listening
numeric output

1. I
2. p
3. t
4. n

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `hostname`


**Concept / Why:**  
</summary> 
Concept / Why:
Shows the short hostname configured for the system.

</details>

---


## Q80. Which of these utility programs can add entries to an LDAP DIT?

Idapdelete
ditadd
Idapmodify
ditmodify
ditdelete
Idapadd

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `hostnamectl set-hostname <name>`


**Concept / Why:**  
</summary> 
Concept / Why:
Changes hostname without reboot; persists unless overridden by DHCP or cloud-init.

</details>

---


## Q81. Write the command used to display the running log file for the Postfix mail server:

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dnf install postfix`


**Concept / Why:**  
</summary> 
Concept / Why:
Installs the Postfix MTA package from the system’s repositories for sending/receiving mail.

</details>

---


## Q82. Which of these issues may cause the slave DNS not to syncronize with the master
DNS?

Incorrect specification in master or slave configuration file
Zone serial number not higher than last sync
Not having a file specified in the client configuration
Network connectivity

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** swift


**Concept / Why:**  
</summary> 
Concept / Why:
Starts the Postfix service immediately and ensures it runs on subsequent boots.

</details>

---


## Q83. Which of these utility programs can delete entries to an LDAP DIT?

Idapadd
ditadd
ditdelete
Idapdelete
Idapmodify
ditmodify

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/postfix/main.cf`


**Concept / Why:**  
</summary> 
Concept / Why:
Contains core Postfix settings like myhostname, mydomain, and mynetworks.

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

**Answer (MC style):** `systemctl reload postfix`


**Concept / Why:**  
</summary> 
Concept / Why:
Applies changes made in Postfix configs without interrupting mail delivery.

</details>

---


## Q85. Which file contains your default name servers?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** mailq


**Concept / Why:**  
</summary> 
Concept / Why:
Displays pending messages in the queue for troubleshooting delivery issues.

</details>

---


## Q86. 

Enter the command line to look up the NS record for the domain "happy.org" using
the dig command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `postqueue -f`


**Concept / Why:**  
</summary> 
Concept / Why:
Forces an immediate delivery attempt of all queued messages.

</details>

---


## Q87. Enter the command line to look up the NS record for the domain "happy.org" on the
teacher's DNS (172.16.30.167) using the nslookup command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/postfix/virtual`


**Concept / Why:**  
</summary> 
Concept / Why:
Maps email addresses to local users or other destinations.

</details>

---


## Q88. If object class inetOrgPerson is a subclass of object class person, the following
applies:
Object class inheritance is not part of the LDAP protocol
All attributes of person are inherited by inetOrgPerson, except the required attributes
All attributes of person are inherited by inetOrgPerson, including the required attributes
All attributes of inetOrgPerson are inherited by person

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `postmap <file>`


**Concept / Why:**  
</summary> 
Concept / Why:
Compiles text mapping files (e.g., virtual, access) into Postfix’s hashed DB format.

</details>

---


## Q89. Which command can be used to verify the HTTPD service is listening on the correct
port?

ip
netstat
55
ifconfig
ipconfig

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `echo "Test" | mail -s "Subject" user@example.com`


**Concept / Why:**  
</summary> 
Concept / Why:
Quick way to send an email through the system’s MTA for verification.

</details>

---


## Q90. Enter the command line to look up the NS record for the domain "happy.org" on the
professor's DNS (172.16.30.167) using the dig command (without -t).

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl status postfix`


**Concept / Why:**  
</summary> 
Concept / Why:
Shows whether Postfix is active and running, plus recent log messages.

</details>

---


## Q91. Apache fails to start due to an unknown directive in the configuration file. One
possibility could be that the corresponding module is not loaded.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dnf install openldap-servers openldap-clients`


**Concept / Why:**  
</summary> 
Concept / Why:
Installs the LDAP daemon (slapd) and client tools for directory services.

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

**Answer (MC style):** `systemctl start slapd`


**Concept / Why:**  
</summary> 
Concept / Why:
The slapd service handles LDAP requests and directory operations.

</details>

---


## Q93. An object is created based on one object class. The object class must be:

Auxiliary
Structural
There is only one type of object class
Abstract

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `systemctl enable slapd`


**Concept / Why:**  
</summary> 
Concept / Why:
Ensures the LDAP server starts automatically after system reboots.

</details>

---


## Q94. 

Enter the command line to look up the MX record for the domain "happy.org" using
the dig command.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/openldap/slapd.d/`


**Concept / Why:**  
</summary> 
Concept / Why:
Stores runtime-configurable settings as LDIF files instead of a single slapd.conf file.

</details>

---


## Q95. Which command(s) verify sshd is listening of the configured port(s)?

netstat -Iptn
ss -Iptn
ip listen
ss listen

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapadd -x -D "cn=Manager,dc=example,dc=com" -W -f file.ldif`


**Concept / Why:**  
</summary> 
Concept / Why:
Uses simple authentication (-x) and the admin bind DN to insert directory entries.

</details>

---


## Q96. Which utility is used to add entries to LDAP from a properly configured LDIF file?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapsearch -x -b "dc=example,dc=com" "(cn=John Doe)"`


**Concept / Why:**  
</summary> 
Concept / Why:
Queries the LDAP directory for objects meeting specified attribute criteria.

</details>

---


## Q97. Which command displays interface configuration for ens160?

ip addr show ens160
ip addr ens160
p addr
ip show ens160
ip ens160

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapmodify -x -D "cn=Manager,dc=example,dc=com" -W -f changes.ldif`


**Concept / Why:**  
</summary> 
Concept / Why:
Applies attribute updates to existing directory entries.

</details>

---


## Q98. Which utility is used to search the LDAP DIT?

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `ldapdelete -x -D "cn=Manager,dc=example,dc=com" -W "cn=John Doe,dc=example,dc=com"`


**Concept / Why:**  
</summary> 
Concept / Why:
Removes an entry by specifying its full Distinguished Name (DN).

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

**Answer (MC style):** `TCP/UDP port 389`


**Concept / Why:**  
</summary> 
Concept / Why:
Default LDAP traffic runs over port 389; LDAPS (encrypted) uses port 636.

</details>

---


## Q100. Which configuration file controls SELINUX?
A/

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `slapcat > backup.ldif`


**Concept / Why:**  
</summary> 
Concept / Why:
Creates a raw export of the entire LDAP database in LDIF format for backup or migration.

</details>

---


## Q101. "Aliasing" is used to redirect email addressed to a generic account such as
"webmaster" to a user account such as "arnold". As such the recipient address is
rewritten by the receiving mail server.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dnf install samba samba-client`


**Concept / Why:**  
</summary> 
Concept / Why:
Installs the SMB/CIFS file sharing service and client utilities.

</details>

---


## Q102. Match the iptables parameters with the description.
Source
Out-bound interface
In-bound interface
Destination
Port
1. -5
2. -d
3. -P
4. -i
5. -0

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/samba/smb.conf`


**Concept / Why:**  
</summary> 
Concept / Why:
Defines shared resources, authentication, and global settings for the Samba service.

</details>

---


## Q103. To send mail using the form user@domain.tld, where the mail server for the domain
is mx.domain.tld, the A record for mx.domain.tld in the zone file for the domain is
sufficient.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** pgsql


**Concept / Why:**  
</summary> 
Concept / Why:
smb handles file sharing, nmb manages NetBIOS name resolution for SMB/CIFS.

</details>

---


## Q104. To locate an object in the DIT you use the _______ of the object.

RDN
None of these choices
FQDN
DNS

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `smbpasswd -a username`


**Concept / Why:**  
</summary> 
Concept / Why:
Adds or updates a Samba account password, stored separately from system passwords.

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

**Answer (MC style):** testparm


**Concept / Why:**  
</summary> 
Concept / Why:
Validates smb.conf syntax before restarting the service.

</details>

---


## Q106. To setup the resolver on the client system to provide hostname resolution with
LDAP in addition to static and DNS-style host name resolution, the following client
configuration file has to be edited:
/etc/resolv.conf
/etc/nsswitch.conf
/etc/hosts
/etc/services

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `TCP 139 & 445, UDP 137 & 138`


**Concept / Why:**  
</summary> 
Concept / Why:
TCP ports handle file sharing connections; UDP ports handle NetBIOS name service and datagrams.

</details>

---


## Q107. You use DNS or /etc/hosts to test your apache virtual hosts locally.

True
False

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `dnf install nfs-utils`


**Concept / Why:**  
</summary> 
Concept / Why:
Provides NFS server and client functionality for Linux file sharing over the network.

</details>

---


## Q108. Assume that name-based virtual hosting is setup for the IP address 172.16.30.199
on a server with more than one interface. You want to display a web site when your
web server is accessed using a different (and valid) IP address. To accomplish this you
should: (look at hint)

Do nothing: the site of the first virtual host will automatically be displayed.
Setup a "default" site in the virtual site section
Setup a separate Apache to listen on the different IP address after making sure
that the current Apache is not listening on that IP address.
It cannot be done: you cannot setup a site for another interface when setting up
virtual hosting for a given interface.

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `/etc/exports`


**Concept / Why:**  
</summary> 
Concept / Why:
Specifies directories to share and their permissions for NFS clients.

</details>

---


## Q109. Which utility will best verify basic network connectivity?

ping
netstat
55
ip
All of these choices

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `exportfs -r`


**Concept / Why:**  
</summary> 
Concept / Why:
Re-reads /etc/exports to apply changes without restarting NFS services.

</details>

---


## Q110. When data is downloaded from a web server to a client browser, the type of data
(text, image, audio, etc.) is determined by the:
File extension of the downloaded document

DocType directive in the Apache configuration
Content-Type header based on MIME types

<details>
<summary>Answer, Concept & Reference</summary>

**Answer (MC style):** `mount server:/path/to/share /mnt/mountpoint`


**Concept / Why:**  
</summary> 
Concept / Why:
Attaches a remote NFS directory to the local filesystem for access.

</details>

---
