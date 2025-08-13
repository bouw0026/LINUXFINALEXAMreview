# LINUXREADME — Sectioned Edition

Organized into ranges for easier navigation.

## Sections

- [Q1–Q20](#q1-q20)
- [Q21–Q40](#q21-q40)
- [Q41–Q60](#q41-q60)
- [Q61–Q80](#q61-q80)
- [Q81–Q100](#q81-q100)
- [Q101–Q110](#q101-q110)


---

## Q1–Q20
<a id="q1-q20"></a>

### Q1
<a id="q1"></a>

**Question:** If a directive in your Apache configuration is not recognized by Apache, the most
likely reason is that the module that supports the directive is missing.

**Choices:**
- True
- False

**Answer:** True.

**Why / Concept:** Apache’s functionality is modular – many configuration directives are provided by loadable modules. If you use a directive that Apache doesn’t recognize, it usually means the module for that directive isn’t enabled or installed. For example, SSL-related directives won’t work unless the SSL module (mod_ssl) is loaded. Ensuring the appropriate module is loaded (via LoadModule or installing the module) will resolve the unrecognized directive issue.

---


### Q2
<a id="q2"></a>

**Question:** Question 2

**Choices:**
- The apache server implements the following protocol:
- HTTP
- URI
- APACHE
- None of these choices

**Answer:** `HTTP (HyperText Transfer Protocol).`

**Why / Concept:** Apache is a web server that serves content over the HTTP protocol (and by extension HTTPS for secure HTTP). It listens on the standard HTTP port (80) to handle web requests. In other words, Apache’s primary role is to implement the HTTP protocol, delivering web pages to clients (web browsers). The other options (URI, “APACHE”) are not network protocols – HTTP is the correct one.

---


### Q3
<a id="q3"></a>

**Question:** cryptography?

**Choices:**
- Which key is used to encrypt in order to prove authenticity using public key
- Private key
- Public key
- Foreign key
- Shared key

**Answer:** `The private key.`

**Why / Concept:** To prove authenticity (as in digital signatures), the sender uses their private key to encrypt/sign the data. Since only the legitimate holder possesses the private key, this act proves the data’s origin. The recipient uses the corresponding public key to decrypt/verify the signature. This public-key cryptography scheme ensures that the message integrity and origin (authenticity) are verifiable. In contrast, encrypting with a public key provides confidentiality (anyone can encrypt to send to the private key holder, but that doesn’t prove identity). Thus, the private key is used for authenticity proofs.

---


### Q4
<a id="q4"></a>

**Question:** Which apache configuration directive configures logging of all website accesses?

**Choices:**
- TransferLog
- Transfer
- AccessLog
- Access

**Answer:** TransferLog.

**Why / Concept:** Apache records all HTTP requests (accesses) in its access log. The classic directive for this is TransferLog, which specifies the file where all requests should be logged. (In newer Apache versions, the CustomLog directive is used for flexible logging, but functionally it serves the same purpose of logging accesses.) For example, an Apache virtual host might use CustomLog /path/to/access.log combined to log all accesses in combined format. Among the given choices, TransferLog is the correct directive that enables logging of all website hits. The options “AccessLog” or “Access” are not actual Apache directives.

---


### Q5
<a id="q5"></a>

**Question:** Question 5

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" using
- the nslookup command.

**Answer:** `nslookup -type=NS happy.org`

**Why / Concept:** The nslookup utility can query specific DNS record types by using the -type=NS option (or -q=NS). In this case, we specify the domain (happy.org) and request NS records, which will return the nameservers authoritative for happy.org. For example, the command above will list the DNS servers (NS records) for the happy.org domain. (Note: While modern Linux administration often prefers dig or host, nslookup is still usable for DNS queries.)

---


### Q6
<a id="q6"></a>

**Question:** Which file controls static hostname resolution?

**Answer:** `The /etc/hosts file.`

**Why / Concept:** /etc/hosts is the local file for static hostname resolution on a Linux system. This file contains mappings of hostnames to IP addresses that the system checks before consulting any DNS server. For example, it usually includes an entry for localhost (mapping to 127.0.0.1) and any other static name-to-IP mappings needed. In summary, /etc/hosts allows the system to resolve hostnames without querying DNS, according to the static entries you place there.

---


### Q7
<a id="q7"></a>

**Question:** What is the command used to start service "foobar" upon system boot up?

**Answer:** `systemctl enable foobar`

**Why / Concept:** To configure a service to start at boot (in a systemd-based Linux like RHEL 8), you use systemctl enable <service>. This command creates the necessary links so that the service (here “foobar”) will automatically start on system startup. (This is distinct from systemctl start, which starts the service immediately but doesn’t enable auto-start.) By enabling a service, you ensure it launches on every boot without manual intervention. For example, systemctl enable foobar will mark the “foobar” service to load on boot.

---


### Q8
<a id="q8"></a>

**Question:** Generally, you should put an IPv4 entry and IPv6 entry for your localhost in you
hosts file.

**Choices:**
- True
- False

**Answer:** True.

**Why / Concept:** It is best practice to have both the IPv4 and IPv6 loopback addresses defined for “localhost” in /etc/hosts. Typically, you will have an entry 127.0.0.1 localhost (IPv4 loopback) and an entry ::1 localhost (IPv6 loopback) in the hosts file. Including both ensures that the hostname “localhost” resolves properly on systems using either IPv4 or IPv6. Most modern Linux distributions include both by default, which helps avoid issues with programs that may use IPv6 by default. In short, True – you should list both 127.0.0.1 and ::1 for localhost in your hosts file.

---


### Q9
<a id="q9"></a>

**Question:** Question 9

**Choices:**
- Enter the command line to look up the PTR record for "172.16.30.167" using the dig
- command.

**Answer:** `dig -x 172.16.30.167`

**Why / Concept:** The dig command’s -x option performs a reverse DNS lookup (i.e. queries for a PTR record). So, dig -x 172.16.30.167 will ask DNS for the PTR record corresponding to the IP 172.16.30.167. The PTR record (if configured) will reveal the hostname associated with that IP address. This is a standard way to verify reverse DNS mapping. According to the course notes, using dig -x is the proper method for reverse lookups. (If the DNS is set up with a reverse zone for 172.16.30.x, this query should return a hostname.)

---


### Q10
<a id="q10"></a>

**Question:** Question 10

**Choices:**
- Enter the command line to look up the PTR record for "172.16.31.167" on your slave
- DNS (172.16.31.167) using the dig command from another Linux machine.

**Answer:** `dig @172.16.31.167 -x 172.16.31.167`

**Why / Concept:** Here we want to query the slave DNS server at 172.16.31.167 for the PTR record of the IP 172.16.31.167. In dig, you can specify the DNS server to ask by using @<server-ip>. So the command is:
dig @172.16.31.167 -x 172.16.31.167.
Breaking it down: -x 172.16.31.167 asks for the PTR record of 172.16.31.167 (reverse lookup), and @172.16.31.167 directs the query to the DNS server at that address (which is the slave). This ensures we are checking the slave DNS directly. The lab instructions explicitly demonstrate using dig -x for reverse lookups and using the @ syntax to query a specific nameserver, which is exactly what we combine in this command.

---


### Q11
<a id="q11"></a>

**Question:** What is the default document root for apache?

**Choices:**
- /var/www
- /var/www/html
- /etc/httpd/www
- /var
- /etc/httpd/www/html
- /etc/httpd/html
- /etc/httpd

**Answer:** who

**Why / Concept:** who displays the list of users currently logged into the system, along with terminal info and login time. It doesn’t show historical logins (that’s last).

---


### Q12
<a id="q12"></a>

**Question:** Question 12

**Choices:**
- Match the commands with the description.
- 1. systemctl list-units						displays all active units
- 2. systemctl list-unit-files				displays all units
- 3. systemctl start service					start service immediately
- 4. systemctl get-default					display the default target
- 5. journalctl -u network					display log messages for the network service
- 6. journalctl -k							display kernel messages
- 7. systemctl list-units -t service			lists all running services

**Answer:** whoami

**Why / Concept:** whoami outputs the effective user name associated with the current session, useful for confirming identity after privilege escalation.

---


### Q13
<a id="q13"></a>

**Question:** Question 13

**Choices:**
- Virtual hosts in Apache are used to:
- Create multiple copies of the same web site on multiple server systems
- Host web sites without the need to setup DNS entries for multiple domain names
- Setup referrals to other web servers
- Have web sites for multiple sites on the same server system

**Answer:** `ls -a`

**Why / Concept:** The -a flag includes all entries, even those starting with a dot (.), which are hidden by default.

---


### Q14
<a id="q14"></a>

**Question:** the package bind?

**Choices:**
- Which file must be modified on the master DNS to allow master/slave operation for
- /etc/bind.conf
- /etc/sysconfig/bind.conf
- /etc/named.conf
- /etc/sysconfig/named.conf

**Answer:** pwd

**Why / Concept:** pwd prints the absolute pathname of the current working directory, based on the shell’s environment.

---


### Q15
<a id="q15"></a>

**Question:** account. The /etc/aliases file is consulted by which mail server?

**Choices:**
- The aliasing feature is used to forward email of a local user to a different email
- inbound
- outbound

**Answer:** `Moves up one directory level.`

**Why / Concept:** .. is a relative pathname for the parent directory. cd .. changes the working directory to it.

---


### Q16
<a id="q16"></a>

**Question:** the postfix configuration file?

**Choices:**
- What does the error message "mail loops back to me" typically indicate is wrong in
- The MX record is incorrect (missing or pointing to an incorrect host
- Postfix is listening only on the loopback interface
- Postfix is listening only on port 25
- "relay_domains" is incorrectly set
- "mydestination" is incorrectly configured

**Answer:** `Detailed list including permissions, owner, group, size, and timestamps.`

**Why / Concept:** -l triggers the “long” listing format, useful for file permissions and metadata inspection.

---


### Q17
<a id="q17"></a>

**Question:** Question 17

**Choices:**
- Name-based virtual hosting is possible because:
- The client connection to the server is based on hostname and port number.
- The client connection to the server is based on IP address and port number, and the hostname is included in the client request.

**Answer:** `Creates an empty file or updates its timestamp.`

**Why / Concept:** touch creates the file if it doesn’t exist; if it exists, it updates the access and modification times.

---


### Q18
<a id="q18"></a>

**Question:** Which command displays interface configuration for all interfaces?

**Choices:**
- ip addr show ens33
- ip addr ens33
- addr
- ip show ens33
- ip ens33

**Answer:** rm

**Why / Concept:** rm deletes files (and with -r, directories). It does not move them to trash—deletion is permanent.

---


### Q19
<a id="q19"></a>

**Question:** Which command(s) verify bind(DNS) is listening of the configured port(s)?

**Choices:**
- netstat -lptn
- ss -lptn
- ip listen
- ss listen

**Answer:** mkdir

**Why / Concept:** mkdir creates directories at the specified path. Use -p to create parent directories as needed.

---


### Q20
<a id="q20"></a>

**Question:** The only source for web documents that a server can map a URL to is given by the
DocumentRoot directive.

**Choices:**
- True
- False

**Answer:** cp

**Why / Concept:** cp copies files from source to destination. With -r, it can copy directories recursively.

---



---

## Q21–Q40
<a id="q21-q40"></a>

### Q21
<a id="q21"></a>

**Question:** Question 21

**Choices:**
- Enter the command line to look up the PTR record for "172.16.31.167" on the
- teacher's slave DNS (172.16.31.167) using the nslookup command.

**Answer:** mv

**Why / Concept:** mv moves a file from one location to another or renames it if the source and destination are on the same filesystem.

---


### Q22
<a id="q22"></a>

**Question:** Question 22

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" using
- the host command.

**Answer:** cat

**Why / Concept:** cat reads and outputs the contents of one or more files to standard output, often used for quick viewing.

---


### Q23
<a id="q23"></a>

**Question:** allowed to add/modify/delete entries in the LDAP database?

**Choices:**
- Assuming you do not configure the configuration file to allow other users, who is
- user8213
- root
- Without further configuration, all users can add/modify/delete entries
- Idapadm
- The LDAP adminstrator

**Answer:** head

**Why / Concept:** head displays the first 10 lines of a file by default. The number of lines can be changed with the -n option.

---


### Q24
<a id="q24"></a>

**Question:** Which file contains the main configuration file for apache?

**Choices:**
- /etc/httpd/conf/http.conf
- /etc/http/conf/http.conf
- /etc/httpd/conf/httpd.conf
- /etc/http/conf/httpd.conf

**Answer:** tail

**Why / Concept:** tail displays the last 10 lines by default and is often used with -f to follow file updates (like logs).

---


### Q25
<a id="q25"></a>

**Question:** Which mail servers "need" to look up a public DNS MX record?

**Choices:**
- None of these answers
- The user sending the email
- The receiving email server
- The user receiving the email
- The sending email server

**Answer:** grep

**Why / Concept:** grep searches for patterns within files using regular expressions, printing matching lines.

---


### Q26
<a id="q26"></a>

**Question:** An attribute is defined by a set of object classes.

**Choices:**
- True
- False

**Answer:** chmod

**Why / Concept:** chmod changes read, write, and execute permissions for owner, group, and others using symbolic or numeric notation.

---


### Q27
<a id="q27"></a>

**Question:** Which command displays the default route?

**Choices:**
- ip route
- ip default
- ss route
- ss show route

**Answer:** chown

**Why / Concept:** chown modifies the owner (and optionally group) of a file. Requires root privileges for most changes.

---


### Q28
<a id="q28"></a>

**Question:** Question 28

**Choices:**
- Based on the following list of criteria determine which ones have to be satisfied for
- an inbound mail server.
- An MX record has to point to the mail server.
- Masquerading is applied on all received email.
- The server has to be setup to "host" for the domain.
- The server has to be setup to "relay" for the domain.

**Answer:** du

**Why / Concept:** du shows the space used by files and directories, optionally summarizing totals with -s.

---


### Q29
<a id="q29"></a>

**Question:** What is the command used to prevent service "foobar" starting automatically upon
system boot up?

**Answer:** df

**Why / Concept:** df reports file system disk space usage in blocks, kilobytes, or human-readable formats (-h).

---


### Q30
<a id="q30"></a>

**Question:** Question 30

**Choices:**
- The SMTP protocol is used to:
- Share resources, such as files and printers, between Windows and Linuxplatforms
- None of these choices
- Maintain and share directory information
- Resolve host names into IP addresses
- Manage network configuration for client systems

**Answer:** ps

**Why / Concept:** ps lists currently running processes. Options like aux display all processes with full details.

---


### Q31
<a id="q31"></a>

**Question:** Which of these firewalls are available on CENTOS 7?

**Choices:**
- firewalld
- iptables
- secured
- ipchains

**Answer:** top

**Why / Concept:** top provides a real-time, updating view of running processes, CPU usage, memory consumption, and system load.

---


### Q32
<a id="q32"></a>

**Question:** Question 32

**Choices:**
- Enter the command line to look up the PTR record for "172.16.30.167" using the
- nslookup command.

**Answer:** man

**Why / Concept:** man opens the manual pages for commands, showing syntax, options, and descriptions. It’s the built-in Linux reference.

---


### Q33
<a id="q33"></a>

**Question:** Question 33

**Choices:**
- Enter the command line to look up the PTR record for "172.16.31.167" on the
- teacher's master DNS (172.16.30.167) using the host command.

**Answer:** which

**Why / Concept:** which returns the full path of a command’s executable by searching the directories in $PATH.

---


### Q34
<a id="q34"></a>

**Question:** peachy.org and sunny.org?

**Choices:**
- Assuming you are already serving two domains, how many additional virtual hosts
- have to be set up in Apache to provide websites for the domains happy.org,
- Zero (0)
- One (1)
- Three (3)
- It cannot be done.

**Answer:** passwd

**Why / Concept:** passwd updates a user’s password and optionally their password aging information.

---


### Q35
<a id="q35"></a>

**Question:** Which sshd configuration options control the use of public key authentication?

**Choices:**
- PasswordAuthentication
- RSAAuthentication
- PermitRootLogin
- AuthorizedKeysFile
- PubkeyAuthentication

**Answer:** `ifconfig (or ip addr on modern systems)`

**Why / Concept:** ifconfig displays interface names, IP addresses, netmasks, and status. It’s been largely replaced by ip addr in newer distros.

---


### Q36
<a id="q36"></a>

**Question:** Which file contains configuration for the DNS client (resolver)?

**Choices:**
- ~/resolv.conf
- /etc/resolver.conf
- /etc/sysconfig/resolve.conf
- /etc/resolv.conf

**Answer:** ping

**Why / Concept:** ping sends ICMP echo requests to test host reachability and measure round-trip time.

---


### Q37
<a id="q37"></a>

**Question:** An object can be created using exactly one auxiliary class and any number, including
zero, structural classes.

**Choices:**
- True
- False

**Answer:** `traceroute (or tracepath)`

**Why / Concept:** traceroute maps the path packets take, listing each hop and its response time, useful for network troubleshooting.

---


### Q38
<a id="q38"></a>

**Question:** Question 38

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" on the
- teacher's DNS (172.16.30.167) using the host command.

**Answer:** `netstat (or ss)`

**Why / Concept:** netstat lists open sockets, routing tables, and interface statistics. On modern systems, ss is preferred.

---


### Q39
<a id="q39"></a>

**Question:** the package bind?

**Choices:**
- Which file must be modified on the slave DNS to allow master/slave operation for
- /etc/sysconfig/bind.conf
- /etc/sysconfig/named.conf
- /etc/bind.conf
- /etc/named.conf

**Answer:** wget

**Why / Concept:** wget retrieves files from web or FTP servers non-interactively, useful for scripting automated downloads.

---


### Q40
<a id="q40"></a>

**Question:** Question 40

**Choices:**
- HTTPS is:
- HTTP that uses the TLS/SSL layer for security services
- A different application layer protocol from HTTP
- HTTP that includes additional security modules defined by the HTTPS protocol
- A newer version of the HTTP protocol

**Answer:** scp

**Why / Concept:** scp uses SSH to copy files securely between hosts. It encrypts both the command and data during transfer.

---



---

## Q41–Q60
<a id="q41-q60"></a>

### Q41
<a id="q41"></a>

**Question:** Question 41

**Choices:**
- Match the iptables other options with the description.
- 1. -V					Verbose
- 2. -n					Numeric
- 3. -- line-numbers		Show line numbers

**Answer:** ssh

**Why / Concept:** ssh opens a secure, encrypted shell session on a remote host, replacing older insecure tools like telnet.

---


### Q42
<a id="q42"></a>

**Question:** Record the command used to verify that the service "foobar" is currently running.

**Answer:** lsmod

**Why / Concept:** lsmod displays the status of loaded kernel modules, including their dependencies and usage counts.

---


### Q43
<a id="q43"></a>

**Question:** Question 43

**Choices:**
- Enter the command line to resolve the A record for "www.happy.org" using your
- default resolver configuration.

**Answer:** modprobe

**Why / Concept:** modprobe loads kernel modules and their dependencies dynamically, simplifying manual insmod operations.

---


### Q44
<a id="q44"></a>

**Question:** What is the minimum number of zone files required in your DNS?

**Choices:**
- You wish to configure apache to serve two "Virtual Hosts", happy.lab & grumpy.lab.
- one
- two
- three
- four

**Answer:** rmmod

**Why / Concept:** rmmod unloads a kernel module from memory. Often replaced by modprobe -r for dependency handling.

---


### Q45
<a id="q45"></a>

**Question:** Record the command that lists all running services.

**Answer:** dmesg

**Why / Concept:** dmesg prints kernel ring buffer messages, often showing hardware initialization and driver load events.

---


### Q46
<a id="q46"></a>

**Question:** Which command is used to show or set your hostname?

**Answer:** `yum install (or dnf install on newer systems)`

**Why / Concept:** yum and dnf are package managers for RHEL-based systems, resolving dependencies automatically during installation.

---


### Q47
<a id="q47"></a>

**Question:** What is the name of the default error log in Apache?

**Choices:**
- error_log
- error_log.log
- error.log
- errorlog.log
- errorlog

**Answer:** `yum update (or dnf upgrade)`

**Why / Concept:** This command updates all packages to the latest available versions from enabled repositories.

---


### Q48
<a id="q48"></a>

**Question:** Which file your hostname resolution order?
/etc/nsswitch.conf

**Answer:** `yum remove (or dnf remove)`

**Why / Concept:** Removes the package and optionally unused dependencies, freeing disk space.

---


### Q49
<a id="q49"></a>

**Question:** Question 49

**Choices:**
- The three required components to have a functional email service are:
- Mail User Agent, Mail Submission Agent, Mail Transfer Agent
- Mail User Agent, Mail Transfer Agent, Mail Delivery Agent
- Mail Submission Agent, Mail Transfer Agent, Mail Delivery Agent
- Mail User Agent, Mail Submission Agent, Mail Delivery Agent

**Answer:** `systemctl start <service>`

**Why / Concept:** systemctl is the systemd service manager; start activates the service without enabling it on boot.

---


### Q50
<a id="q50"></a>

**Question:** Question 50

**Choices:**
- The LDAP protocol is used to:
- Share resources, such as files and printers, between Windows and Linux platforms
- Resolve host names into IP addresses
- Manage network configuration, such as IP addresses, for client systems
- Maintain and share directory information
- None of the above

**Answer:** `systemctl enable <service>`

**Why / Concept:** enable creates a symbolic link in systemd configuration to auto-start the service during system boot.

---


### Q51
<a id="q51"></a>

**Question:** Question 51

**Choices:**
- Postfix is considered to be primarily a:
- Mail Transfer Agent
- Mail Submission Agent
- Mail User Agent
- Mail Delivery Agent

**Answer:** `systemctl stop <service>`

**Why / Concept:** stop halts a running service without preventing it from starting on the next boot (unless disabled separately).

---


### Q52
<a id="q52"></a>

**Question:** Question 52

**Choices:**
- Enter the command line to look up the MX record for the domain "happy.org" using
- the host command.

**Answer:** `systemctl disable <service>`

**Why / Concept:** disable removes the boot-time symbolic link so the service won’t auto-start after reboots.

---


### Q53
<a id="q53"></a>

**Question:** By default, which interface(s) does postfix listen?

**Choices:**
- localhost or 127.0.0.1
- The first ethernet adapter
- All the ethernet adapters
- All the ethernet adapters and localhost

**Answer:** `systemctl restart <service>`

**Why / Concept:** restart is a stop followed by a start in one step, useful after config changes.

---


### Q54
<a id="q54"></a>

**Question:** Question 54

**Choices:**
- Enter the command line to look up the PTR record for "172.16.30.167" using the
- host command.

**Answer:** `systemctl status <service>`

**Why / Concept:** Displays whether the service is active, its PID, last log entries, and exit codes.

---


### Q55
<a id="q55"></a>

**Question:** Question 55

**Choices:**
- When setting up name-based virtual hosts, the Apache configuration requires:
- One DocumentRoot directive for each virtual host and one ServerName directive
- One DocumentRoot directive and one ServerName directive
- One DocumentRoot directive for each virtual host and one ServerName directive for each virtual host
- One DocumentRoot directive and one ServerName directive for each virtual host

**Answer:** `setenforce 0`

**Why / Concept:** This command relaxes SELinux policy enforcement without disabling SELinux entirely, useful for troubleshooting.

---


### Q56
<a id="q56"></a>

**Question:** Question 56

**Choices:**
- Identify the correct MX record entry to be recorded in the zone file.
- mail.example.lab. IN MX 10 172.16.30.200
- example.lab. IN MX 10 mail.example.lab.
- 172.16.30.200 IN MX 10 mail.example.lab.
- mail.example.lab. IN MX 10 example.lab.

**Answer:** `Edit /etc/selinux/config and set SELINUX=permissive`

**Why / Concept:** Changing the config file ensures the setting persists across reboots.

---


### Q57
<a id="q57"></a>

**Question:** Which of these are valid ways to send mail on the command line?

**Choices:**
- mail -s Test Email user8213@cst8213.lab
- mail -s TestEmail user8213@cst8213.lab
- mail -s Test Email user8213@172.16.30.167
- mail -s TestEmail user8213@172.16.30.167
- mail -s Test Email user8213@[172.16.30.167]
- mail -s TestEmail user8213@[172.16.30.167]
- mail -s Test Email user8213@host.cst8213.lab
- mail -s TestEmail user8213@host.cst8213.lab

**Answer:** getenforce

**Why / Concept:** getenforce returns Enforcing, Permissive, or Disabled to show the active SELinux mode.

---


### Q58
<a id="q58"></a>

**Question:** Which of these commands will let you view the mail queue?

**Choices:**
- mailq -v
- mailq -p
- mailq
- postqueue -p
- postqueue -v

**Answer:** chcon

**Why / Concept:** chcon modifies SELinux security context labels for files without altering default policy settings.

---


### Q59
<a id="q59"></a>

**Question:** Which mail server is the masquerading feature is setup on?
inbound		 ?
outbound

**Answer:** restorecon

**Why / Concept:** restorecon re-applies the default SELinux context from policy to the file path.

---


### Q60
<a id="q60"></a>

**Question:** Question 60

**Choices:**
- Match the iptables targets with the description.
- 1. DROP		Drop the packet. No reply to the source.
- 2. REJECT	Reject the packet. Reply with appropriate ICMP message
- 3. RETURN	The chain policy determines the fate of the packet
- 4. ACCEPT	Let the packet through

**Answer:** `ls -Z`

**Why / Concept:** ls -Z shows SELinux labels alongside normal file listing, helping verify policy enforcement.

---



---

## Q61–Q80
<a id="q61-q80"></a>

### Q61
<a id="q61"></a>

**Question:** Which apache configuration option specifies the port Apache listens on?

**Choices:**
- ListenPort
- Port
- Listen
- 80

**Answer:** `firewall-cmd --list-all-zones`

**Why / Concept:** Lists every defined firewalld zone and the services, ports, and interfaces assigned to each.

---


### Q62
<a id="q62"></a>

**Question:** Question 62

**Choices:**
- The base/suffix for happy.org can be setup using the following object class:
- top
- inetOrgPerson
- domain
- person

**Answer:** `firewall-cmd --list-all`

**Why / Concept:** Shows services, ports, sources, and interfaces bound to the default active zone.

---


### Q63
<a id="q63"></a>

**Question:** Question 63

**Choices:**
- Enter the command line to resolve the A record for "www.happy.org" using your
- professor's DNS at 172.16.30.167 using your preferred command.

**Answer:** `firewall-cmd --permanent --add-service=http`

**Why / Concept:** Allows HTTP traffic persistently by enabling the predefined http service in firewalld.

---


### Q64
<a id="q64"></a>

**Question:** Consistency of directory information across replicated LDAP servers is crucial while
consistency of data stored in transactional databases is not.

**Choices:**
- True
- False

**Answer:** `firewall-cmd --reload`

**Why / Concept:** Applies configuration changes from permanent rules without restarting the service.

---


### Q65
<a id="q65"></a>

**Question:** Question 65

**Choices:**
- Identify the error in the following LDIF entry:
- dn: cn=Sarah Jones,ou=people,dc=example.com
- objectclass: inetorgperson
- cn: Sarah Jones
- sn: Jones
- mail: Sarah.Jones@example.com
- mail: sjones@example.com
- There is no error
- There can only be one mail attribute, not two
- The dc attribute does not have a valid value
- The syntax for the attributes should use an = sign, not a colon, as in sn=Jones

**Answer:** `firewall-cmd --add-service=https`

**Why / Concept:** Enables HTTPS access until the next reload or reboot without altering permanent settings.

---


### Q66
<a id="q66"></a>

**Question:** The default sshd_config shipped with OpenSSH is to specify options with their
default values commented.

**Choices:**
- True
- False

**Answer:** `firewall-cmd --permanent --remove-service=ssh`

**Why / Concept:** Blocks SSH traffic persistently by removing its service entry from the firewall.

---


### Q67
<a id="q67"></a>

**Question:** You use DNS or /etc/hosts to test your apache virtual hosts remotely.

**Choices:**
- True
- False

**Answer:** `firewall-cmd --get-default-zone`

**Why / Concept:** Reveals the zone where unassigned network interfaces are placed by default.

---


### Q68
<a id="q68"></a>

**Question:** Question 68

**Choices:**
- Enter the command line to look up the MX record for the domain "happy.org" using
- the nslookup command.

**Answer:** `firewall-cmd --set-default-zone=<zone>`

**Why / Concept:** Changes the default security zone for future interface assignments.

---


### Q69
<a id="q69"></a>

**Question:** Which command(s) shows all interface configurations?

**Choices:**
- ip addr show ens33 ens34
- ip addr show
- ip addr
- ip addr show all
- ip show
- ip

**Answer:** `firewall-cmd --get-services`

**Why / Concept:** Displays all predefined services that can be added as firewall rules.

---


### Q70
<a id="q70"></a>

**Question:** Which sshd configuration options control the use of password authentication?

**Choices:**
- PasswordAuthentication
- RSAAuthentication
- PermitRootLogin
- AuthorizedKeysFile
- PubkeyAuthentication

**Answer:** `firewall-cmd --query-service=<service>`

**Why / Concept:** Returns yes if the service is permitted in the current active zone; no otherwise.

---


### Q71
<a id="q71"></a>

**Question:** Which of these utility programs can modify entries to an LDAP DIT?

**Choices:**
- Idapadd
- Idapmodify
- Idapdelete
- ditadd
- ditmodify
- ditdelete

**Answer:** `ip addr show`

**Why / Concept:** Lists all interfaces, IPs, MAC addresses, and interface states. Preferred over ifconfig in modern systems.

---


### Q72
<a id="q72"></a>

**Question:** Which utility will best verify basic network connectivity?

**Choices:**
- ping
- netstat
- 55
- ip
- All of these choices

**Answer:** `ip route show`

**Why / Concept:** Displays routes, gateways, and metrics that determine packet forwarding.

---


### Q73
<a id="q73"></a>

**Question:** package "foobar"?

**Choices:**
- What is the rpm command line that lists all the files that are part of the installed
- A/

**Answer:** `ping <host>`

**Why / Concept:** Confirms whether a host is reachable and measures packet loss and latency.

---


### Q74
<a id="q74"></a>

**Question:** Question 74

**Choices:**
- To verify the mail server of the domain example.lab based on the MX record the
- following dig command is used:
- dig MX mail.example.lab
- dig mail.example.lab
- dig MX example.lab
- dig mx.example.lab

**Answer:** `traceroute <host>`

**Why / Concept:** Lists each hop along the route to the destination, useful for diagnosing network delays.

---


### Q75
<a id="q75"></a>

**Question:** An "outbound" only mail server typically "hosts" email for its domain.

**Choices:**
- True
- False

**Answer:** `dig <domain>`

**Why / Concept:** Queries DNS servers for records such as A, AAAA, MX, and more.

---


### Q76
<a id="q76"></a>

**Question:** Which command(s) show all listening TCP ports?

**Choices:**
- netstat -Iptn
- 5s -Iptn
- ip listen
- ss listen

**Answer:** `nslookup <domain>`

**Why / Concept:** Checks DNS resolution through the configured /etc/resolv.conf settings.

---


### Q77
<a id="q77"></a>

**Question:** Question 77

**Choices:**
- Enter the command line to look up the PTR record for "172.16.31.167" on your
- master DNS (172.16.30.167) using the dig command from another Linux machine.

**Answer:** `ss -tuln`

**Why / Concept:** Shows TCP/UDP sockets in listening state, with ports and IP bindings.

---


### Q78
<a id="q78"></a>

**Question:** Match the iptables commands with the description.
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

**Answer:** `telnet <host> <port>`

**Why / Concept:** Useful for verifying service availability on a specific port (e.g., SMTP on port 25).

---


### Q79
<a id="q79"></a>

**Question:** Question 79

**Choices:**
- Match the options for ss (or netstat) with the description.
- show TCP ports
- programs & pids
- listening
- numeric output
- 1. I
- 2. p
- 3. t
- 4. n

**Answer:** `hostname`

**Why / Concept:** Shows the short hostname configured for the system.

---


### Q80
<a id="q80"></a>

**Question:** Which of these utility programs can add entries to an LDAP DIT?

**Choices:**
- Idapdelete
- ditadd
- Idapmodify
- ditmodify
- ditdelete
- Idapadd

**Answer:** `hostnamectl set-hostname <name>`

**Why / Concept:** Changes hostname without reboot; persists unless overridden by DHCP or cloud-init.

---



---

## Q81–Q100
<a id="q81-q100"></a>

### Q81
<a id="q81"></a>

**Question:** Write the command used to display the running log file for the Postfix mail server:

**Answer:** `dnf install postfix`

**Why / Concept:** Installs the Postfix MTA package from the system’s repositories for sending/receiving mail.

---


### Q82
<a id="q82"></a>

**Question:** DNS?

**Choices:**
- Which of these issues may cause the slave DNS not to syncronize with the master
- Incorrect specification in master or slave configuration file
- Zone serial number not higher than last sync
- Not having a file specified in the client configuration
- Network connectivity

**Answer:** swift

**Why / Concept:** Starts the Postfix service immediately and ensures it runs on subsequent boots.

---


### Q83
<a id="q83"></a>

**Question:** Which of these utility programs can delete entries to an LDAP DIT?

**Choices:**
- Idapadd
- ditadd
- ditdelete
- Idapdelete
- Idapmodify
- ditmodify

**Answer:** `/etc/postfix/main.cf`

**Why / Concept:** Contains core Postfix settings like myhostname, mydomain, and mynetworks.

---


### Q84
<a id="q84"></a>

**Question:** What is the default user used by apache while running?

**Choices:**
- apache
- cst8213
- The user that started apache
- root
- nobody

**Answer:** `systemctl reload postfix`

**Why / Concept:** Applies changes made in Postfix configs without interrupting mail delivery.

---


### Q85
<a id="q85"></a>

**Question:** Which file contains your default name servers?

**Answer:** mailq

**Why / Concept:** Displays pending messages in the queue for troubleshooting delivery issues.

---


### Q86
<a id="q86"></a>

**Question:** Question 86

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" using
- the dig command.

**Answer:** `postqueue -f`

**Why / Concept:** Forces an immediate delivery attempt of all queued messages.

---


### Q87
<a id="q87"></a>

**Question:** Question 87

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" on the
- teacher's DNS (172.16.30.167) using the nslookup command.

**Answer:** `/etc/postfix/virtual`

**Why / Concept:** Maps email addresses to local users or other destinations.

---


### Q88
<a id="q88"></a>

**Question:** Question 88

**Choices:**
- If object class inetOrgPerson is a subclass of object class person, the following
- applies:
- Object class inheritance is not part of the LDAP protocol
- All attributes of person are inherited by inetOrgPerson, except the required attributes
- All attributes of person are inherited by inetOrgPerson, including the required attributes
- All attributes of inetOrgPerson are inherited by person

**Answer:** `postmap <file>`

**Why / Concept:** Compiles text mapping files (e.g., virtual, access) into Postfix’s hashed DB format.

---


### Q89
<a id="q89"></a>

**Question:** port?

**Choices:**
- Which command can be used to verify the HTTPD service is listening on the correct
- ip
- netstat
- 55
- ifconfig
- ipconfig

**Answer:** `echo "Test" | mail -s "Subject" user@example.com`

**Why / Concept:** Quick way to send an email through the system’s MTA for verification.

---


### Q90
<a id="q90"></a>

**Question:** Question 90

**Choices:**
- Enter the command line to look up the NS record for the domain "happy.org" on the
- professor's DNS (172.16.30.167) using the dig command (without -t).

**Answer:** `systemctl status postfix`

**Why / Concept:** Shows whether Postfix is active and running, plus recent log messages.

---


### Q91
<a id="q91"></a>

**Question:** Apache fails to start due to an unknown directive in the configuration file. One
possibility could be that the corresponding module is not loaded.

**Choices:**
- True
- False

**Answer:** `dnf install openldap-servers openldap-clients`

**Why / Concept:** Installs the LDAP daemon (slapd) and client tools for directory services.

---


### Q92
<a id="q92"></a>

**Question:** Practically, who should be able to look up a public DNS MX record?

**Choices:**
- The sending email server
- The receiving email server
- The user sending the email
- The user receiving the email
- None of these answers

**Answer:** `systemctl start slapd`

**Why / Concept:** The slapd service handles LDAP requests and directory operations.

---


### Q93
<a id="q93"></a>

**Question:** Question 93

**Choices:**
- An object is created based on one object class. The object class must be:
- Auxiliary
- Structural
- There is only one type of object class
- Abstract

**Answer:** `systemctl enable slapd`

**Why / Concept:** Ensures the LDAP server starts automatically after system reboots.

---


### Q94
<a id="q94"></a>

**Question:** Question 94

**Choices:**
- Enter the command line to look up the MX record for the domain "happy.org" using
- the dig command.

**Answer:** `/etc/openldap/slapd.d/`

**Why / Concept:** Stores runtime-configurable settings as LDIF files instead of a single slapd.conf file.

---


### Q95
<a id="q95"></a>

**Question:** Which command(s) verify sshd is listening of the configured port(s)?

**Choices:**
- netstat -Iptn
- ss -Iptn
- ip listen
- ss listen

**Answer:** `ldapadd -x -D "cn=Manager,dc=example,dc=com" -W -f file.ldif`

**Why / Concept:** Uses simple authentication (-x) and the admin bind DN to insert directory entries.

---


### Q96
<a id="q96"></a>

**Question:** Which utility is used to add entries to LDAP from a properly configured LDIF file?

**Answer:** `ldapsearch -x -b "dc=example,dc=com" "(cn=John Doe)"`

**Why / Concept:** Queries the LDAP directory for objects meeting specified attribute criteria.

---


### Q97
<a id="q97"></a>

**Question:** Which command displays interface configuration for ens160?

**Choices:**
- ip addr show ens160
- ip addr ens160
- p addr
- ip show ens160
- ip ens160

**Answer:** `ldapmodify -x -D "cn=Manager,dc=example,dc=com" -W -f changes.ldif`

**Why / Concept:** Applies attribute updates to existing directory entries.

---


### Q98
<a id="q98"></a>

**Question:** Which utility is used to search the LDAP DIT?

**Answer:** `ldapdelete -x -D "cn=Manager,dc=example,dc=com" -W "cn=John Doe,dc=example,dc=com"`

**Why / Concept:** Removes an entry by specifying its full Distinguished Name (DN).

---


### Q99
<a id="q99"></a>

**Question:** Which of these command line utilities can be used to perform DNS lookups?

**Choices:**
- nslookup
- dig
- dns
- lookup
- host

**Answer:** `TCP/UDP port 389`

**Why / Concept:** Default LDAP traffic runs over port 389; LDAPS (encrypted) uses port 636.

---


### Q100
<a id="q100"></a>

**Question:** Which configuration file controls SELINUX?
A/

**Answer:** `slapcat > backup.ldif`

**Why / Concept:** Creates a raw export of the entire LDAP database in LDIF format for backup or migration.

---



---

## Q101–Q110
<a id="q101-q110"></a>

### Q101
<a id="q101"></a>

**Question:** "Aliasing" is used to redirect email addressed to a generic account such as
"webmaster" to a user account such as "arnold". As such the recipient address is
rewritten by the receiving mail server.

**Choices:**
- True
- False

**Answer:** `dnf install samba samba-client`

**Why / Concept:** Installs the SMB/CIFS file sharing service and client utilities.

---


### Q102
<a id="q102"></a>

**Question:** Question 102

**Choices:**
- Match the iptables parameters with the description.
- Source
- Out-bound interface
- In-bound interface
- Destination
- Port
- 1. -5
- 2. -d
- 3. -P
- 4. -i
- 5. -0

**Answer:** `/etc/samba/smb.conf`

**Why / Concept:** Defines shared resources, authentication, and global settings for the Samba service.

---


### Q103
<a id="q103"></a>

**Question:** To send mail using the form user@domain.tld, where the mail server for the domain
is mx.domain.tld, the A record for mx.domain.tld in the zone file for the domain is
sufficient.

**Choices:**
- True
- False

**Answer:** pgsql

**Why / Concept:** smb handles file sharing, nmb manages NetBIOS name resolution for SMB/CIFS.

---


### Q104
<a id="q104"></a>

**Question:** Question 104

**Choices:**
- To locate an object in the DIT you use the _______ of the object.
- RDN
- None of these choices
- FQDN
- DNS

**Answer:** `smbpasswd -a username`

**Why / Concept:** Adds or updates a Samba account password, stored separately from system passwords.

---


### Q105
<a id="q105"></a>

**Question:** Which apache block directive is used to configure virtual hosts?

**Choices:**
- Virtual
- MultiHost
- Multi
- VirtualHost
- Host

**Answer:** testparm

**Why / Concept:** Validates smb.conf syntax before restarting the service.

---


### Q106
<a id="q106"></a>

**Question:** Question 106

**Choices:**
- To setup the resolver on the client system to provide hostname resolution with
- LDAP in addition to static and DNS-style host name resolution, the following client
- configuration file has to be edited:
- /etc/resolv.conf
- /etc/nsswitch.conf
- /etc/hosts
- /etc/services

**Answer:** `TCP 139 & 445, UDP 137 & 138`

**Why / Concept:** TCP ports handle file sharing connections; UDP ports handle NetBIOS name service and datagrams.

---


### Q107
<a id="q107"></a>

**Question:** You use DNS or /etc/hosts to test your apache virtual hosts locally.

**Choices:**
- True
- False

**Answer:** `dnf install nfs-utils`

**Why / Concept:** Provides NFS server and client functionality for Linux file sharing over the network.

---


### Q108
<a id="q108"></a>

**Question:** Question 108

**Choices:**
- Assume that name-based virtual hosting is setup for the IP address 172.16.30.199
- on a server with more than one interface. You want to display a web site when your
- web server is accessed using a different (and valid) IP address. To accomplish this you
- should: (look at hint)
- Do nothing: the site of the first virtual host will automatically be displayed.
- Setup a "default" site in the virtual site section
- Setup a separate Apache to listen on the different IP address after making sure
- that the current Apache is not listening on that IP address.
- It cannot be done: you cannot setup a site for another interface when setting up
- virtual hosting for a given interface.

**Answer:** `/etc/exports`

**Why / Concept:** Specifies directories to share and their permissions for NFS clients.

---


### Q109
<a id="q109"></a>

**Question:** Which utility will best verify basic network connectivity?

**Choices:**
- ping
- netstat
- 55
- ip
- All of these choices

**Answer:** `exportfs -r`

**Why / Concept:** Re-reads /etc/exports to apply changes without restarting NFS services.

---


### Q110
<a id="q110"></a>

**Question:** Question 110

**Choices:**
- When data is downloaded from a web server to a client browser, the type of data
- (text, image, audio, etc.) is determined by the:
- File extension of the downloaded document
- DocType directive in the Apache configuration
- Content-Type header based on MIME types

**Answer:** `mount server:/path/to/share /mnt/mountpoint`

**Why / Concept:** Attaches a remote NFS directory to the local filesystem for access.

