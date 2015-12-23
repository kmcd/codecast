## Networking 2m

  ftp
  curl / wget / httrack
  ssh
  scp
  SSH config
  lsof
  ifconfig

  176 Transferring Files
  207 Networking
  
# Networking L 35
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  ifconfig
  hostname

  *netstat / nmap port scanner

  (start rails)
  netstat -an | grep LISTEN

  (disable ping, fastest timing)
  nmap -Pn -T5 localhost

  (what network services are open?)
  sudo nmap -Pn svr-sta-nagios3.internal.trapezegroupuk.ltd.uk

  *ping / tracroute

  ping berkeley.edu

  traceroute berkeley.edu

  *dns/nslookup/MX record

  whois berkeley.edu

  nslookup berkeley.edu
  nslookup -type=MX berkeley.edu

  *ssh keys

  ssh keygen
  cat ~/.ssh/id_rsa.pub
  cat ~/.ssh/id_rsa.pub | pbcopy
  ls -la ~/.ssh/
  cd ~/tmp/
  ls -la ~/.ssh/
  ssh-keygen -t dsa -C "kmcd@nubian"
  ls -lah ~/.ssh/
  ssh-keygen -t dsa -C "kmcd@nubian"
  ssh kmcd@46.101.85.91
  ssh 46.101.85.91
  ssh root@46.101.85.91
  cat ~/.ssh/id_rsa.pub
  cat ~/.ssh/id_rsa.pub | pbcopy
  ssh root@46.101.85.91
  ssh root@46.101.85.91 'ls'

  *ssh command

  ssh root@46.101.85.91 whoami
  ssh root@46.101.85.91 ifconfig

  *scp

  scp ~/.ssh/id_dsa.pub root@46.101.85.91:~/.ssh/id_dsa.pub
  ssh root@46.101.85.91 cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys

  *sftp

  cd path                            Change remote directory to 'path'

  chgrp grp path                     Change group of file 'path' to 'grp'
  chmod mode path                    Change permissions of file 'path' to 'mode'
  chown own path                     Change owner of file 'path' to 'own'
  df [-hi] [path]                    Display statistics for current directory or
                                     filesystem containing 'path'

  get [-afPpRr] remote [local]       Download file
  reget [-fPpRr] remote [local]      Resume download file
  reput [-fPpRr] [local] remote      Resume upload file
  put [-afPpRr] local [remote]       Upload file

  help                               Display this help text

  lcd path                           Change local directory to 'path'
  lls [ls-options [path]]            Display local directory listing
  lmkdir path                        Create local directory
  lpwd                               Print local working directory

  ls [-1afhlnrSt] [path]             Display remote directory listing
  mkdir path                         Create remote directory
  pwd                                Display remote working directory

  rename oldpath newpath             Rename remote file
  rm path                            Delete remote file
  rmdir path                         Remove remote directory

  !command                           Execute 'command' in local shell
  !                                  Escape to local shell
  ?                                  Synonym for help

  *wget

  wget—Non-interactive network downloader.

  export RAILS_GUIDES=guides.rubyonrails.org
  wget -r $RAILS_GUIDES
  open `find $RAILS_GUIDES -iname "*active_record*"`

## Next steps
  iftop
  mtr
  lsof
  nmap

  *ssh tunnel / port forward
  http://www.revsys.com/writings/quicktips/ssh-tunnel.html

### Reference
  http://www.itworld.com/article/2697039/unix-top-networking-commands-and-what-they-tell-you.html
  https://www.linode.com/docs/networking/diagnostics/diagnosing-network-issues-with-mtr

## Networking 2m

  NETWORKING

  When it comes to networking, there is probably noth- ing that cannot be done with Linux. Linux is used to build all sorts of networking systems and appli- ances, including firewalls, routers, name servers, NAS (network-attached storage) boxes, and on and on.
  Just as the subject of networking is vast, so is the number of commands that can be used to configure and control it. We will focus our attention on just a few of the most frequently used ones. The commands chosen for exam- ination include those used to monitor networks and those used to transfer files. In addition, we are going to explore the ssh program, which is used to perform remote logins. This chapter will cover the following:
    ping—Send an ICMP ECHO_REQUEST to network hosts.
    traceroute—Print the route packets trace to a network host.
    netstat—Print network connections, routing tables, interface statis- tics, masquerade connections, and multicast memberships.
    ftp—Internet file transfer program.
    lftp—An improved Internet file transfer program.
    wget—Non-interactive network downloader.
    ssh—OpenSSH SSH client (remote login program).
    scp—Secure copy (remote file copy program).
    sftp—Secure file transfer program.
  We’re going to assume a little background in networking. In this, the Internet age, everyone using a computer needs a basic understanding of networking concepts. To make full use of this chapter, you should be famil- iar with the following terms:
    IP (Internet protocol) address
    Host and domain name
    URI (uniform resource identifier)
  Note: Some of the commands we will cover may (depending on your distribution) require the installation of additional packages from your distribution’s repositories, and some may require superuser privileges to execute.
  Examining and Monitoring a Network
  Even if you’re not the system administrator, it’s often helpful to examine the performance and operation of a network.
  ping—Send a Special Packet to a Network Host
  The most basic network command is ping. The ping command sends a spe- cial network packet called an IMCP ECHO_REQUEST to a specified host. Most network devices receiving this packet will reply to it, allowing the net- work connection to be verified.
  Note: It is possible to configure most network devices (including Linux hosts) to ignore these packets. This is usually done for security reasons, to partially obscure a host from a potential attacker. It is also common for firewalls to be configured to block IMCP traffic.
  For example, to see if we can reach http://www.linuxcommand.org/ (one of my favorite sites ;-)), we can use ping like this:
  [me@linuxbox ~]$ ping linuxcommand.org
  Once started, ping continues to send packets at a specified interval
  (default is 1 second) until it is interrupted:
  [me@linuxbox ~]$ ping linuxcommand.org
  PING linuxcommand.org (66.35.250.210) 56(84) bytes of data.
     176
  Chapter 16
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=1 ttl=43 time=10 7 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=2 ttl=43 time=10 8 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=3 ttl=43 time=10 6 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=4 ttl=43 time=10 6 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=5 ttl=43 time=10 5 ms
  64 bytes from vhost.sourceforge.net (66.35.250.210): icmp_seq=6 ttl=43 time=10 7 ms
  --- linuxcommand.org ping statistics ---
  6 packets transmitted, 6 received, 0% packet loss, time 6010ms rtt min/avg/max/mdev = 105.647/107.052/108.118/0.824 ms
  After it is interrupted (in this case after the sixth packet) by the pressing of CTRL-C, ping prints performance statistics. A properly performing network will exhibit zero percent packet loss. A successful ping will indicate that the elements of the network (its interface cards, cabling, routing, and gateways) are in generwrap ally good working order.
  traceroute—Trace the Path of a Network Packet
  The traceroute program (some systems use the similar tracepath program instead) displays a listing of all the "hops" network traffic takes to get from the local system to a specified host. For example, to see the route taken to reach http://www.slashdot.org/, we would do this:
  [me@linuxbox ~]$ traceroute slashdot.org The output looks like this:
  traceroute to slashdot.org (216.34.181.45), 30 hops max, 40 byte packets 1 ipcop.localdomain (192.168.1.1) 1.066 ms 1.366 ms 1.720 ms
  2 * **
  3 ge-4-13-ur01.rockville.md.bad.comcast.net (68.87.130.9) 14.622 ms 14.885
  ms 15.169 ms
  4 po-30-ur02.rockville.md.bad.comcast.net (68.87.129.154) 17.634 ms 17.626
  ms 17.899 ms
  5 po-60-ur03.rockville.md.bad.comcast.net (68.87.129.158) 15.992 ms 15.983
  ms 16.256 ms
  6 po-30-ar01.howardcounty.md.bad.comcast.net (68.87.136.5) 22.835 ms 14.23
  3 ms 14.405 ms
  7 po-10-ar02.whitemarsh.md.bad.comcast.net (68.87.129.34) 16.154 ms 13.600
  ms 18.867 ms
  8 te-0-3-0-1-cr01.philadelphia.pa.ibone.comcast.net (68.86.90.77) 21.951 ms
  21.073 ms 21.557 ms
  9 pos-0-8-0-0-cr01.newyork.ny.ibone.comcast.net (68.86.85.10) 22.917 ms 21
  .884 ms 22.126 ms
  10 204.70.144.1 (204.70.144.1) 43.110 ms 21.248 ms 21.264 ms
  11 cr1-pos-0-7-3-1.newyork.savvis.net (204.70.195.93) 21.857 ms cr2-pos-0-0- 3-1.newyork.savvis.net (204.70.204.238) 19.556 ms cr1-pos-0-7-3-1.newyork.sav vis.net (204.70.195.93) 19.634 ms
      Networking 177
  12 cr2-pos-0-7-3-0.chicago.savvis.net (204.70.192.109) 41.586 ms 42.843 ms cr2-tengig-0-0-2-0.chicago.savvis.net (204.70.196.242) 43.115 ms
  13 hr2-tengigabitethernet-12-1.elkgrovech3.savvis.net (204.70.195.122) 44.21 5 ms 41.833 ms 45.658 ms
  14 csr1-ve241.elkgrovech3.savvis.net (216.64.194.42) 46.840 ms 43.372 ms 4 7.041 ms
  15 64.27.160.194 (64.27.160.194) 56.137 ms 55.887 ms 52.810 ms
  16 slashdot.org (216.34.181.45) 42.727 ms 42.016 ms 41.437 ms
  In the output, we can see that connecting from our test system to http:// www.slashdot.org/ requires traversing 16 routers. For routers that provide identifying information, we see their hostnames, IP addresses, and perform- ance data, which include three samples of round-trip time from the local system to the router. For routers that do not provide identifying information (because of router configuration, network congestion, firewalls, etc.), we see asterisks as in the line for hop number two.
  netstat—Examine Network Settings and Statistics
  The netstat program is used to examine various network settings and statis- tics. Through the use of its many options, we can look at a variety of features in our network setup. Using the -ie option, we can examine the network interfaces in our system:
  [me@linuxbox ~]$ netstat -ie
  eth0 Link encap:Ethernet HWaddr 00:1d:09:9b:99:67
  inet addr:192.168.1.2 Bcast:192.168.1.255 Mask:255.255.255.0 inet6 addr: fe80::21d:9ff:fe9b:9967/64 Scope:Link
  UP BROADCAST RUNNING MULTICAST MTU:1500 Metric:1
  RX packets:238488 errors:0 dropped:0 overruns:0 frame:0
          TX packets:403217 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:100
          RX bytes:153098921 (146.0 MB)  TX bytes:261035246 (248.9 MB)
          Memory:fdfc0000-fdfe0000
  lo Link encap:Local Loopback
  inet addr:127.0.0.1 Mask:255.0.0.0
  inet6 addr: ::1/128 Scope:Host
  UP LOOPBACK RUNNING MTU:16436 Metric:1
  RX packets:2208 errors:0 dropped:0 overruns:0 frame:0 TX packets:2208 errors:0 dropped:0 overruns:0 carrier:0 collisions:0 txqueuelen:0
  RX bytes:111490 (108.8 KB) TX bytes:111490 (108.8 KB)
  In the example above, we see that our test system has two network inter- faces. The first, called eth0, is the Ethernet interface; the second, called lo, is the loopback interface, a virtual interface that the system uses to "talk to itself."
  When performing causal network diagnostics, the important things to look for are the presence of the word UP at the beginning of the fourth line for each interface, indicating that the network interface is enabled, and the presence of a valid IP address in the inet addr field on the second line. For systems using Dynamic Host Configuration Protocol (DHCP), a valid IP address in this field will verify that the DHCP is working.
     178 Chapter 16
  Using the -r option will display the kernel’s network routing table. This shows how the network is configured to send packets from network to network:
  [me@linuxbox ~]$ netstat -r
   Kernel IP routing table
  Destination  Gateway
  192.168.1.0  *
  192.168.1.1 0.0.0.0
  Genmask       Flags   MSS Window  irtt Iface
  255.255.255.0 U         0 0          0 eth0  default
  UG 0 0 0 eth0
   In this simple example, we see a typical routing table for a client machine on a local area network (LAN) behind a firewall/router. The first line of the listing shows the destination 192.168.1.0. IP addresses that end in zero refer to networks rather than individual hosts, so this destination means any host on the LAN. The next field, Gateway, is the name or IP address of the gateway (router) used to go from the current host to the destination network. An asterisk in this field indicates that no gateway is needed.
  The last line contains the destination default. This means any traffic destined for a network that is not otherwise listed in the table. In our example, we see that the gateway is defined as a router with the address of 192.168.1.1, which presumably knows what to do with the destination traffic.
  The netstat program has many options, and we have looked at only a couple. Check out the netstat man page for a complete list.
  Transporting Files over a Network
  What good is a network unless we know how to move files across it? There are many programs that move data over networks. We will cover two of them now and several more in later sections.
  ftp—Transfer Files with the File Transfer Protocol
  One of the true "classic" programs, ftp gets its name from the protocol it uses, the File Transfer Protocol. FTP is used widely on the Internet for file downloads. Most, if not all, web browsers support it, and you often see URIs starting with the protocol ftp://.
  Before there were web browsers, there was the ftp program. ftp is used to communicate with FTP servers, machines that contain files that can be uploaded and downloaded over a network.
  FTP (in its original form) is not secure, because it sends account names and passwords in cleartext. This means that they are not encrypted and any- one sniffing the network can see them. Because of this, almost all FTP done over the Internet is done by anonymous FTP servers. An anonymous server allows anyone to log in using the login name anonymous and a meaningless password.
  In the following example, we show a typical session with the ftp pro- gram downloading an Ubuntu ISO image located in the /pub/cd_images/ Ubuntu-8.04 directory of the anonymous FTP server fileserver.
  Networking 179
  [me@linuxbox ~]$ ftp fileserver
  Connected to fileserver.localdomain.
  220 (vsFTPd 2.0.1)
  Name (fileserver:me): anonymous
  331 Please specify the password.
  Password:
  230 Login successful.
  Remote system type is UNIX.
  Using binary mode to transfer files.
  ftp> cd pub/cd_images/Ubuntu-8.04
  250 Directory successfully changed.
  ftp> ls
  200 PORT command successful. Consider using PASV.
  150 Here comes the directory listing.
  -rw-rw-r-- 1 500 500 733079552 Apr 25 03:53 ubuntu-8.04-desktop- i386.iso
  226 Directory send OK.
  ftp> lcd Desktop
  Local directory now /home/me/Desktop
  ftp> get ubuntu-8.04-desktop-i386.iso
  local: ubuntu-8.04-desktop-i386.iso remote: ubuntu-8.04-desktop-i386.iso
  200 PORT command successful. Consider using PASV.
  150 Opening BINARY mode data connection for ubuntu-8.04-desktop-i386.iso (733079552 bytes).
  226 File send OK.
  733079552 bytes received in 68.56 secs (10441.5 kB/s)
  ftp> bye
  Table 16-1 gives an explanation of the commands entered during this session.
  Table 16-1: Examples of Interactive ftp Commands
    Command
  ftp fileserver
  anonymous
  cd pub/cd_images/Ubuntu-8.04
  ls
  Meaning
  Invoke the ftp program and have it connect to the FTP server fileserver.
  Login name. After the login prompt, a password prompt will appear. Some servers will accept a blank password. Others will require a password in the form of an email address. In that case, try something like user@example.com.
  Change to the directory on the remote system containing the desired file. Note that on most anonymous FTP servers, the files for public downloading are found somewhere under the pub directory.
  List the directory on the remote system.
          180 Chapter 16
  Table 16-1 (continued) Command
  lcd Desktop
   get ubuntu-8.04-desktop-i386.iso
  bye
  Meaning
  Change the directory on the local system to ~/Desktop. In the example, the ftp program was invoked when the working directory was ~. This command changes the working directory to ~/Desktop.
  Tell the remote system to transfer the file ubuntu-8.04-desktop-i386.iso to the local system. Since the working directory on the local system was changed to ~/Desktop, the file will be downloaded there.
  Log off the remote server and end the ftp program session. The commands quit and exit may also be used.
         Typing help at the ftp> prompt will display a list of the supported com- mands. Using ftp on a server where sufficient permissions have been granted, it is possible to perform many ordinary file management tasks. It’s clumsy, but it does work.
  lftp—A Better ftp
  ftp is not the only command-line FTP client. In fact, there are many. One of the better (and more popular) ones is lftp by Alexander Lukyanov. It works much like the traditional ftp program but has many additional convenience features, including multiple-protocol support (including HTTP), automatic retry on failed downloads, background processes, tab completion of path- names, and many more.
  wget—Non-interactive Network Downloader
  Another popular command-line program for file downloading is wget. It is useful for downloading content from both web and FTP sites. Single files, multiple files, and even entire sites can be downloaded. To download the first page of http://www.linuxcommand.org/, we could do this:
  [me@linuxbox ~]$ wget http://linuxcommand.org/index.php --11:02:51-- http://linuxcommand.org/index.php
             => `index.php'
  Resolving linuxcommand.org... 66.35.250.210
  Connecting to linuxcommand.org|66.35.250.210|:80... connected.
   Networking 181
  HTTP request sent, awaiting response... 200 OK Length: unspecified [text/html]
                   [ <=>                                 ] 3,120         --.--K/s
               11:02:51 (161.75 MB/s) - `index.php' saved [3120]
  The program’s many options allow wget to recursively download, down- load files in the background (allowing you to log off but continue down- loading), and complete the download of a partially downloaded file. These features are well documented in its better-than-average man page.
  Secure Communication with Remote Hosts
  For many years, Unix-like operating systems have had the ability to be administered remotely via a network. In the early days, before the general adoption of the Internet, there were a couple of popular programs used to log in to remote hosts: the rlogin and telnet programs. These programs, however, suffer from the same fatal flaw that the ftp program does; they transmit all their communications (including login names and passwords) in cleartext. This makes them wholly inappropriate for use in the Internet age.
  ssh—Securely Log in to Remote Computers
  To address this problem, a new protocol called SSH (Secure Shell) was developed. SSH solves the two basic problems of secure communication with a remote host. First, it authenticates that the remote host is who it says it is (thus preventing man-in-the-middle attacks), and second, it encrypts all of the communications between the local and remote hosts.
  SSH consists of two parts. An SSH server runs on the remote host, listen- ing for incoming connections on port 22, while an SSH client is used on the local system to communicate with the remote server.
  Most Linux distributions ship an implementation of SSH called OpenSSH from the BSD project. Some distributions include both the client and the server packages by default (for example, Red Hat), while others (such as Ubuntu) supply only the client. To enable a system to receive remote con- nections, it must have the OpenSSH-server package installed, configured, and running, and (if the system is either running or behind a firewall) it must allow incoming network connections on TCP port 22.
  Note: If you don’t have a remote system to connect to but want to try these examples, make sure the OpenSSH-server package is installed on your system and use localhost as the name of the remote host. That way, your machine will create network connections with itself.
   182
  Chapter 16
  The SSH client program used to connect to remote SSH servers is called, appropriately enough, ssh. To connect to a remote host named remote-sys, we would use the ssh client program like so:
  [me@linuxbox ~]$ ssh remote-sys
  The authenticity of host 'remote-sys (192.168.1.4)' can't be established. RSA key fingerprint is 41:ed:7a:df:23:19:bf:3c:a5:17:bc:61:b3:7f:d9:bb. Are you sure you want to continue connecting (yes/no)?
  The first time the connection is attempted, a message is displayed indi- cating that the authenticity of the remote host cannot be established. This is because the client program has never seen this remote host before. To accept the credentials of the remote host, enter yes when prompted. Once the connection is established, the user is prompted for a password:
  Warning: Permanently added 'remote-sys,192.168.1.4' (RSA) to the list of known hosts.
  me@remote-sys's password:
  After the password is successfully entered, we receive the shell prompt from the remote system:
  Last login: Tue Aug 30 13:00:48 2011
  [me@remote-sys ~]$
  The remote shell session continues until the user enters the exit com- mand at the remote shell prompt, thereby closing the remote connection. At this point, the local shell session resumes, and the local shell prompt reappears.
  It is also possible to connect to remote systems using a different user- name. For example, if the local user me had an account named bob on a remote system, user me could log in to the account bob on the remote system as follows:
  [me@linuxbox ~]$ ssh bob@remote-sys bob@remote-sys's password:
  Last login: Tue Aug 30 13:03:21 2011 [bob@remote-sys ~]$
  As stated before, ssh verifies the authenticity of the remote host. If the remote host does not successfully authenticate, the following message appears:
  [me@linuxbox ~]$ ssh remote-sys @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  @ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @ @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
  IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
  Someone could be eavesdropping on you right now (man-in-the-middle attack)! It is also possible that the RSA host key has just been changed.
           Networking 183
  The fingerprint for the RSA key sent by the remote host is 41:ed:7a:df:23:19:bf:3c:a5:17:bc:61:b3:7f:d9:bb.
  Please contact your system administrator.
  Add correct host key in /home/me/.ssh/known_hosts to get rid of this message. Offending key in /home/me/.ssh/known_hosts:1
  RSA host key for remote-sys has changed and you have requested strict checking.
  Host key verification failed.
  This message is caused by one of two possible situations. First, an attacker may be attempting a man-in-the-middle attack. This is rare, because every- body knows that ssh alerts the user to this. The more likely culprit is that the remote system has been changed somehow; for example, its operating system or SSH server has been reinstalled. In the interests of security and safety, however, the first possibility should not be dismissed out of hand. Always check with the administrator of the remote system when this message occurs.
  After determining that the message is due to a benign cause, it is safe to correct the problem on the client side. This is done by using a text editor (vim perhaps) to remove the obsolete key from the ~/.ssh/known_hosts file. In the example message above, we see this:
  Offending key in /home/me/.ssh/known_hosts:1
  This means that line 1 of the known_hosts file contains the offending key. Delete this line from the file, and the ssh program will be able to accept new authentication credentials from the remote system.
  Besides opening a shell session on a remote system, ssh also allows us to execute a single command on a remote system. For example, we can execute the free command on a remote host named remote-sys and have the results displayed on the local system:
      [me@linuxbox ~]$ ssh remote-sys free
  me@twin4's password:
               total
  shared    buffers     cached
       0     110068     154596
                         used     free
                       507184   268352
                       242520   533016
  It’s possible to use this technique in more interesting ways, such as this example in which we perform an ls on the remote system and redirect the output to a file on the local system:
  [me@linuxbox ~]$ ssh remote-sys 'ls *' > dirlist.txt me@twin4's password:
  [me@linuxbox ~]$
  Notice the use of the single quotes. This is done because we do not want the pathname expansion performed on the local machine; rather, we want it to be performed on the remote system. Likewise, if we had wanted the output
  Mem:        775536
  -/+ buffers/cache:
  Swap:      1572856        0    1572856
  [me@linuxbox ~]$
     184 Chapter 16
  redirected to a file on the remote machine, we could have placed the redir- ection operator and the filename within the single quotes:
  [me@linuxbox ~]$ ssh remote-sys 'ls * > dirlist.txt'
        TUNNELING WITH SSH
  Part of what happens when you establish a connection with a remote host via SSH is that an encrypted tunnel is created between the local and remote systems. Normally, this tunnel is used to allow commands typed at the local system to be transmitted safely to the remote system and the results to be transmitted safely back. In addition to this basic function, the SSH protocol allows most types of network traffic to be sent through the encrypted tunnel, creating a sort of VPN (virtual private network) between the local and remote systems.
  Perhaps the most common use of this feature is to allow X Window system traffic to be transmitted. On a system running an X server (that is, a machine displaying a GUI), it is possible to launch and run an X client program (a graph- ical application) on a remote system and have its display appear on the local system. It’s easy to do—here’s an example. Let’s say we are sitting at a Linux sys- tem called linuxbox that is running an X server, and we want to run the xload program on a remote system named remote-sys and see the program’s graphical output on our local system. We could do this:
       [me@linuxbox ~]$ ssh -X remote-sys me@remote-sys's password:
  Last login: Mon Sep 05 13:23:11 2011 [me@remote-sys ~]$ xload
     After the xload command is executed on the remote system, its window appears on the local system. On some systems, you may need to use the -Y option rather than the -X option to do this.
   scp and sftp—Securely Transfer Files
  The OpenSSH package also includes two programs that can make use of an SSH- encrypted tunnel to copy files across the network. The first, scp (secure copy) is used much like the familiar cp program to copy files. The most notable difference is that the source or destination pathname may be preceded with the name of a remote host followed by a colon character. For example, if we wanted to copy a document named document.txt from our home directory on the remote system, remote-sys, to the current working directory on our local system, we could do this:
  [me@linuxbox ~]$ scp remote-sys:document.txt .
  me@remote-sys's password:
  document.txt 100% 5581 5.5KB/s 00:00 [me@linuxbox ~]$
    Networking 185
  As with ssh, you may apply a username to the beginning of the remote host’s name if the desired remote host account name does not match that of the local system:
  [me@linuxbox ~]$ scp bob@remote-sys:document.txt .
  The second SSH file-copying program is sftp, which, as its name implies, is a secure replacement for the ftp program. sftp works much like the ori- ginal ftp program that we used earlier; however, instead of transmitting everything in cleartext, it uses an SSH-encrypted tunnel. sftp has an impor- tant advantage over conventional ftp in that it does not require an FTP server to be running on the remote host. It requires only the SSH server. This means that any remote machine that can connect with the SSH client can also be used as a FTP-like server. Here is a sample session:
  [me@linuxbox ~]$ sftp remote-sys Connecting to remote-sys... me@remote-sys's password:
  sftp> ls ubuntu-8.04-desktop-i386.iso sftp> lcd Desktop
  sftp> get ubuntu-8.04-desktop-i386.iso
  Fetching /home/me/ubuntu-8.04-desktop-i386.iso to ubuntu-8.04-desktop-i386.iso
  /home/me/ubuntu-8.04-desktop-i386.iso 100% 699MB 7.4MB/s 01:35 sftp> bye
  Note: The SFTP protocol is supported by many of the graphical file managers found in Linux distributions. Using either Nautilus (GNOME) or Konqueror (KDE), we can enter a URI beginning with sftp:// into the location bar and operate on files stored on a remote system running an SSH server.

### VO 300w

  $ nmap
  $ lsof

  ping—Send an ICMP ECHO_REQUEST to network hosts.
  traceroute—Print the route packets trace to a network host.


  $ ping google.com
  $ traceroute google.com
  (xtraceroute ?)

  ftp—Internet file transfer program.

  ftp archive.org

  wget—Non-interactive network downloader.

  $ wget -r $RAILS_GUIDES

  open `find guides.rubyonrails.org -iname "*active_record*"`

  ssh—OpenSSH SSH client (remote login program).

  keys

  As stated before, ssh verifies the authenticity of the remote host.

  If the remote host does not successfully authenticate, the following message appears:

  @ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @

  Add correct host key in /home/me/.ssh/known_hosts to get rid of this message.

  Offending key in /home/me/.ssh/known_hosts:1
  RSA host key for remote-sys has changed and you have requested strict checking.

  This message is caused by one of two possible situations. First, an attacker may be attempting a man-in-the-middle attack. This is rare, because every- body knows that ssh alerts the user to this.

  The more likely culprit is that the remote system has been changed somehow; for example, its operating system or SSH server has been reinstalled. In the interests of security and safety, however, the first possibility should not be dismissed out of hand.

  Always check with the administrator of the remote system when this message occurs.

  After determining that the message is due to a benign cause, it is safe to correct the problem on the client side.

  This is done by using a text editor (vim perhaps) to remove the obsolete key from the ~/.ssh/known_hosts file. In the example message above, we see this:

  Offending key in /home/me/.ssh/known_hosts:1

  This means that line 1 of the known_hosts file contains the offending key.

  Delete this line from the file, and the ssh program will be able to accept new authentication credentials from the remote system.

  Besides opening a shell session on a remote system, ssh also allows us to execute a single command on a remote system.

  For example, we can execute the free command on a remote host named remote-sys and have the results displayed on the local system:

  [me@linuxbox ~]$ ssh remote-sys free

  It’s possible to use this technique in more interesting ways, such as this example in which we perform an ls on the remote system and redirect the output to a file on the local system:

  [me@linuxbox ~]$ ssh remote-sys 'ls *' > dirlist.txt 
  
  me@twin4's password:
  [me@linuxbox ~]$

  Notice the use of the single quotes. This is done because we do not want the pathname expansion performed on the local machine; rather, we want it to be performed on the remote system. Likewise, if we had wanted the output
  Mem:        775536
  -/+ buffers/cache:
  Swap:      1572856        0    1572856
  [me@linuxbox ~]$

  redirected to a file on the remote machine, we could have placed the redir- ection operator and the filename within the single quotes:
  [me@linuxbox ~]$ ssh remote-sys 'ls * > dirlist.txt'

  scp and sftp—Securely Transfer Files

  [me@linuxbox ~]$ scp remote-sys:document.txt .
  me@remote-sys's password:
  document.txt 100% 5581 5.5KB/s 00:00 [me@linuxbox ~]$

  [me@linuxbox ~]$ scp bob@remote-sys:document.txt .






