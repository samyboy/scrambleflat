scrambleflat
===========

Scrambles a flat file

This Python script gives you the ability to hide sensitive data from your files
before giving them away. For example you can anonymyze logins or hide IP adresses.

A simple example would be a log file to send to someone but you don't want
to show the real names. This script is for you.

Prerequisites
-------------

* Linux (or similar)
* Python 2.x

Installation
------------

I have nothing better yet

    wget https://raw.github.com/samyboy/scrambleflat/master/scrambleflat -O scrambleflat /usr/local/bin
    chmod +x /usr/local/bin/scrambleflat

How it works
------------

`scrambleflat` takes the standard input, scrambles the data, and gives the
result on the standard output.
You will have to provide a file containing the terms to hide.

Usage
-----

The best option to have an idea is to type `scrambleflat --help`.

This example scrambles the last system events and anonymyzes the local users:

```bash
# 1. create a list of terms to hide
cut -d ':' -f 1 /etc/passwd > my_users
# 2. scramble the logins on your machine
scrambleflat --terms my_users < /var/log/syslog
```
