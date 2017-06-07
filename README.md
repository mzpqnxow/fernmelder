## fernmelder - asynchronous, high-speed mass DNS resolver / brute-forcer

* (C) 2014 by Sebastian Krahmer, sebastian [dot] krahmer [at] gmail [dot] com
* Released under GPLv3 or later

### Use

This tool is very useful for getting a list of HTTP virtual hostnames from a list of IP addresses during an Internet perimeter assessment. You should only do this if it is legal in your particular situation of course, etc. It is a tool useful for penetration testers as well as DNS and system administrators. It essentially allows you to use a wordlist to discover existing DNS names for a TLD. The example below will discover hosts for "victim.com"

### Howto

```
$ make && rm -f fqdn.in
$ export TARGET_TLD=victim.com
$ for i in $(IFS=$'\n' cat /usr/share/dict/words); do echo ${i}.${TARGET_TLD} >> fqdn.in; done
$ head -5 
$ for x in $(cat /usr/share/dict/
$ ./fernmelder -4 -N 4.2.2.2 -N 4.2.2.3 -N 4.2.2.4 -N 4.2.2.5 < fqdn_list.in | tee fqdn_responses.out
$ grep -v NXDOMAIN fqdn_responses.out | cut -d ' ' -f 1 | awk '{print $1, $5}'
vpn.victim.com
barney.victim.com
repo.victim.com
github.victim.com
smith.victim.com
```

... and so on, you get the point

### Why

This is really important when websites are behind load balancers or reverse proxies as they will not allow you to reach the web application without the correct FQDN. Sometimes SSL certificates will provide a subject or subject altName but other times wildcard certificates will prevent this from working. Other times, a "target" will only use HTTP, and thus SSL certificates don't help at all.
