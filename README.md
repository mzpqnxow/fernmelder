## fernmelder - asynchronous, high-speed mass DNS resolver / brute-forcer

* (C) 2014 by Sebastian Krahmer, sebastian [dot] krahmer [at] gmail [dot] com
* Released under GPLv3 or later

### Howto

$ make && rm -f fqdn.in
$ export TARGET_TLD=victim.com
$ for i in $(IFS=$'\n' cat /usr/share/dict/words); do echo ${i}.${TARGET_TLD} >> fqdn.in; done
$ head -5 
$ for x in $(cat /usr/share/dict/
$ ./fernmelder -4 -N 4.2.2.2 -N 4.2.2.3 -N 4.2.2.4 -N 4.2.2.5 < fqdn_list.in | tee fqdn_responses.out
