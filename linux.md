# Linux Command Cheat Sheet

This document provides a quick reference guide for commonly used Linux commands, along with their syntax and examples. 

## Table of Contents

1. [SSH](#ssh)
2. [LS](#ls)
3. [PWD](#pwd)
4. [CD](#cd)
5. [TOUCH](#touch)
6. [ECHO](#echo)
7. [NANO](#nano)
8. [VIM](#vim)
9. [CAT](#cat)
10. [SHRED](#shred)
11. [MKDIR](#mkdir)
12. [CP](#cp)
13. [RM](#rm)
14. [RMDIR](#rmdir)
15. [LN](#ln)
16. [CLEAR](#clear)
17. [WHOAMI](#whoami)
18. [USERADD](#useradd)
19. [SUDO](#sudo)
20. [ADDUSER](#adduser)
21. [SU](#su)
22. [EXIT](#exit)
23. [PASSWD](#passwd)
24. [APT](#apt)
25. [FINGER](#finger)
26. [MAN](#man)
27. [WHATIS](#whatis)
28. [CURL](#curl)
29. [ZIP](#zip)
30. [UNZIP](#unzip)
31. [LESS](#less)
32. [HEAD](#head)
33. [TAIL](#tail)
34. [CMP](#cmp)
35. [DIFF](#diff)
36. [SORT](#sort)
37. [FIND](#find)
38. [CHMOD](#chmod)
39. [CHOWN](#chown)
40. [IFCONFIG](#ifconfig)
41. [IP ADDRESS](#ip-address)
42. [GREP](#grep)
43. [AWK](#awk)
44. [RESOLVECTL STATUS](#resolvectl-status)
45. [PING](#ping)
46. [NETSTAT](#netstat)
47. [SS](#ss)
48. [IPTABLES](#iptables)
49. [UFW](#ufw)
50. [UNAME](#uname)
51. [NEOFETCH](#neofetch)
52. [CAL](#cal)
53. [FREE](#free)
54. [DF](#df)
55. [PS](#ps)
56. [TOP](#top)
57. [HTOP](#htop)
58. [KILL](#kill)
59. [PKILL](#pkill)
60. [SYSTEMCTL](#systemctl)
61. [HISTORY](#history)
62. [REBOOT](#reboot)
63. [SHUTDOWN](#shutdown)

---

## SSH

- **Description:** Securely connect to a remote server.
- **Syntax:** `ssh user@hostname`
- **Example:** `ssh john@192.168.1.10`

## LS

- **Description:** List directory contents.
- **Syntax:** `ls [options] [directory]`
- **Example:** `ls -l /home`

## PWD

- **Description:** Print Working Directory.
- **Syntax:** `pwd`
- **Example:** `pwd`

## CD

- **Description:** Change Directory.
- **Syntax:** `cd [directory]`
- **Example:** `cd /home/user/Documents`

## TOUCH

- **Description:** Create an empty file or update the timestamp of an existing file.
- **Syntax:** `touch filename`
- **Example:** `touch newfile.txt`

## ECHO

- **Description:** Display a line of text.
- **Syntax:** `echo [text]`
- **Example:** `echo "Hello World"`

## NANO

- **Description:** Command-line text editor.
- **Syntax:** `nano [filename]`
- **Example:** `nano test.txt`

## VIM

- **Description:** Advanced text editor.
- **Syntax:** `vim [filename]`
- **Example:** `vim test.txt`

## CAT

- **Description:** Concatenate and display file content.
- **Syntax:** `cat [filename]`
- **Example:** `cat file.txt`

## SHRED

- **Description:** Securely delete files by overwriting their contents.
- **Syntax:** `shred [options] [filename]`
- **Example:** `shred -u file.txt`

## MKDIR

- **Description:** Make a directory.
- **Syntax:** `mkdir [directory name]`
- **Example:** `mkdir newfolder`

## CP

- **Description:** Copy files or directories.
- **Syntax:** `cp [source] [destination]`
- **Example:** `cp file.txt /backup/`

## RM

- **Description:** Remove files or directories.
- **Syntax:** `rm [file]`
- **Example:** `rm file.txt`

## RMDIR

- **Description:** Remove an empty directory.
- **Syntax:** `rmdir [directory name]`
- **Example:** `rmdir oldfolder`

## LN

- **Description:** Create symbolic links to files or directories.
- **Syntax:** `ln -s [target] [link name]`
- **Example:** `ln -s /path/to/file linkname`

## CLEAR

- **Description:** Clear the terminal screen.
- **Syntax:** `clear`
- **Example:** `clear`

## WHOAMI

- **Description:** Display the current logged-in username.
- **Syntax:** `whoami`
- **Example:** `whoami`

## USERADD

- **Description:** Add a new user.
- **Syntax:** `sudo useradd [username]`
- **Example:** `sudo useradd john`

## SUDO

- **Description:** Execute a command as another user (usually root).
- **Syntax:** `sudo [command]`
- **Example:** `sudo apt update`

## ADDUSER

- **Description:** Add a new user and set up their home directory and password.
- **Syntax:** `sudo adduser [username]`
- **Example:** `sudo adduser john`

## SU

- **Description:** Switch to another user.
- **Syntax:** `su [username]`
- **Example:** `su root`

## EXIT

- **Description:** Exit the current shell or session.
- **Syntax:** `exit`
- **Example:** `exit`

## PASSWD

- **Description:** Change a user's password.
- **Syntax:** `passwd [username]`
- **Example:** `passwd john`

## APT

- **Description:** Advanced Package Tool, used for package management in Debian-based systems.
- **Syntax:** `sudo apt [command]`
- **Example:** `sudo apt install vim`

## FINGER

- **Description:** Display information about a user.
- **Syntax:** `finger [username]`
- **Example:** `finger john`

## MAN

- **Description:** View the manual of any command.
- **Syntax:** `man [command]`
- **Example:** `man ls`

## WHATIS

- **Description:** Show a one-line description of a command.
- **Syntax:** `whatis [command]`
- **Example:** `whatis ls`

## CURL

- **Description:** Transfer data from or to a server.
- **Syntax:** `curl [options] [URL]`
- **Example:** `curl http://example.com`

## ZIP

- **Description:** Package and compress files.
- **Syntax:** `zip [archive name] [files]`
- **Example:** `zip archive.zip file1.txt file2.txt`

## UNZIP

- **Description:** Extract compressed files from a .zip archive.
- **Syntax:** `unzip [archive.zip]`
- **Example:** `unzip archive.zip`

## LESS

- **Description:** View the content of a file one screen at a time.
- **Syntax:** `less [filename]`
- **Example:** `less file.txt`

## HEAD

- **Description:** Display the first 10 lines of a file.
- **Syntax:** `head [filename]`
- **Example:** `head file.txt`

## TAIL

- **Description:** Display the last 10 lines of a file.
- **Syntax:** `tail [filename]`
- **Example:** `tail file.txt`

## CMP

- **Description:** Compare two files byte by byte.
- **Syntax:** `cmp [file1] [file2]`
- **Example:** `cmp file1.txt file2.txt`

## DIFF

- **Description:** Show the differences between two files.
- **Syntax:** `diff [file1] [file2]`
- **Example:** `diff file1.txt file2.txt`

## SORT

- **Description:** Sort lines of text in a file.
- **Syntax:** `sort [filename]`
- **Example:** `sort file.txt`

## FIND

- **Description:** Search for files in a directory hierarchy.
- **Syntax:** `find [path] [options] [expression]`
- **Example:** `find /home -name "*.txt"`

## CHMOD

- **Description:** Change file permissions.
- **Syntax:** `chmod [permissions] [filename]`
- **Example:** `chmod 755 file.txt`

## CHOWN

- **Description:** Change file owner and group.
- **Syntax:** `chown [owner]:[group] [filename]`
- **Example:** `chown john:users file.txt`

## IFCONFIG

- **Description:** Configure a network interface.
- **Syntax:** `ifconfig [interface]`
- **Example:** `ifconfig eth0`

## IP ADDRESS

- **Description:** Display or manipulate routing, devices, and tunnels.
- **Syntax:** `ip address`
- **Example:** `ip address show`

## GREP

- **Description:** Search text using patterns.
- **Syntax:** `grep [pattern] [file]`
- **Example:** `grep "hello" file.txt`

## AWK

- **Description:** Pattern scanning and processing language.
- **Syntax:** `awk '{pattern + action}' [file]`
- **Example:** `awk '{print $1}' file.txt`

## RESOLVECTL STATUS

- **Description:** Resolve domain names using the system's resolver.
- **Syntax:** `resolvectl status`
- **Example:** `resolvectl status`

## PING

- **Description:** Send ICMP ECHO_REQUEST to network hosts.
- **Syntax:** `ping [hostname or IP]`
- **Example:** `ping google.com`

## NETSTAT

- **Description:** Network statistics.
- **Syntax:** `netstat [options]`
- **Example:** `netstat -tuln`

## SS

- **Description:** Socket statistics.
- **Syntax:** `ss [options]`
- **Example:** `ss -tuln`

## IPTABLES

- **Description:** Manage IPv4 packet filtering and NAT.
- **Syntax:** `iptables [options]`
- **Example:** `iptables -L`

## UFW

- **Description:** Uncomplicated Firewall, manage firewall rules.
- **Syntax:** `ufw [command]`
- **Example:** `sudo ufw enable`

## UNAME

- **Description:** Print system information.
- **Syntax:** `uname [options]`
- **Example:** `uname -a`

## NEOFETCH

- **Description:** Display system information with aesthetic formatting.
- **Syntax:** `neofetch`
- **Example:** `neofetch`

## CAL

- **Description:** Display a calendar.
- **Syntax:** `cal`
- **Example:** `cal`

## FREE

- **Description:** Display memory usage.
- **Syntax:** `free [options]`
- **Example:** `free -h`

## DF

- **Description:** Display disk space usage.
- **Syntax:** `df [options]`
- **Example:** `df -h`

## PS

- **Description:** Display information about active processes.
- **Syntax:** `ps [options]`
- **Example:** `ps aux`

## TOP

- **Description:** Display real-time process information.
- **Syntax:** `top`
- **Example:** `top`

## HTOP

- **Description:** Interactive process viewer.
- **Syntax:** `htop`
- **Example:** `htop`

## KILL

- **Description:** Terminate a process by ID.
- **Syntax:** `kill [PID]`
- **Example:** `kill 1234`

## PKILL

- **Description:** Terminate processes by name.
- **Syntax:** `pkill [process name]`
- **Example:** `pkill chrome`

## SYSTEMCTL

- **Description:** Control the systemd system and service manager.
- **Syntax:** `systemctl [command]`
- **Example:** `systemctl start apache2`

## HISTORY

- **Description:** Show the history of commands entered.
- **Syntax:** `history`
- **Example:** `history`

## REBOOT

- **Description:** Reboot the system.
- **Syntax:** `reboot`
- **Example:** `sudo reboot`

## SHUTDOWN

- **Description:** Shut down the system.
- **Syntax:** `shutdown [options]`
- **Example:** `sudo shutdown now`

---

This cheat sheet should provide you with a handy reference for many commonly used Linux commands. Feel free to add more commands as you learn them!
