---
title: 🐧 Linux
date: 0002-01-01
layout: post
---

### Overview

[**Linux**](https://en.wikipedia.org/wiki/Linux) is a family of open source [**Unix**](https://en.wikipedia.org/wiki/Unix)-like **operating systems** based on the [**Linux**](https://en.wikipedia.org/wiki/Linux) kernel, an operating system kernel first released on September 17, 1991, by [**Linus Torvalds**](https://es.wikipedia.org/wiki/Linus_Torvalds).

---

### Enumeration

```bash
# username
whoami
# user groups
id
# connected users
w
# machine name
hostname
# os & kernel
uname -a
hostnamectl
lsb_release -a
# list files and folders
ls
ls -l
ls -la
ls -laR
tree
tree -fas
# file size
du -hc filename
du -hc *
# environment variables
env
set
history
alias
# processes
ps aux
ps -faux
ps -eo command
ps -eo command "root"
```

---

### Network

```bash
# all
ip a
ifconfig
# ipv4
ip -4 a
# ipv6
ip -6 a
# interface eth0
ip a show eth0

cat /proc/net/arp

route
route -n
routel
ip route show

hostname -I

iptables -L

ss -ltun
ss -ltun | grep "127"
ss -nltp
pwdx 8505
netstat -nat
netstat -nat | grep "127"

lsof -i :22
lsof | grep "1234"
fuser 65000/tcp
fuser -k 3306/tcp
```

---

### Interesting Files

#### System

```bash
/etc/passwd
/etc/shadow
/etc/hosts
/etc/hostname
/etc/issue
/etc/motd
/etc/sudoers
/etc/crontab
/etc/group
```

#### Keys

```bash
/home/user/.ssh/id_rsa
/home/user/.ssh/authorized_keys

/root/.ssh/id_rsa
/root/.ssh/authorized_keys
```

#### SSH

```bash
/etc/ssh/sshd_config
/var/log/auth.log
```

#### Apache & Nginx

```bash
/var/www/html
/var/log/apache2/access.log
/var/log/apache2/error.log
/etc/apache2/sites-available/000-default.conf
/etc/apache2/apache2.conf
```

---

### Restricted Bash (rbash)

#### Escape (Bypass)

Some ways to escape restricted context in shell.

```bash
ssh low@192.168.1.2 -t 'bash --noprofile'
ssh low@192.168.1.2 bash
ssh -i id_rsa low@192.168.1.2 -t 'bash --noprofile'
```

---

### Compilate Binary

##### Windows

```bash
# apt-get install mingw-w64
i686-w64-mingw32-gcc main.c -o binary.exe        # x86 - 32 bits
x86_64-w64-mingw32-gcc main.c -o binary.exe      # x64 - 64 bits
```

##### Linux

```bash
gcc -m32 main.c -o binary      # x86 - 32 bits
gcc main.c -o binary           # x64 - 64 bits

gcc main.c -o binary -static   # fix errors
```

##### Go

```bash
go build .                     # default (no compress)

go build  -ldflags '-s -w' .   # compress
upx binary
```

---

<div style="display: flex; justify-content: center; align-items: center; width: 100%; margin-top: 20px;">
  <img src="/assets/gitbook/images/favicon.png" style="width: 30px; height: auto; margin-right: 6px;">
  <span style="color: #ffffffa4;">© VulNyx 2023-2025</span>
</div>
