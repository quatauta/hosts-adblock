hosts-adblock.sh - Ad-blocker for dnsmasq hosts file
===

host-adblock.sh is a bash script to create ad blocking hosts files for [dnsmasq][1].

Home routers based on DD-WRT, OpenWrt or ASUSWRT-Merlin often use dnsmasq as local DNS
server. Dnsmasq reads additional hosts files based on the [`addn-hosts`][2] option.

hosts-adblock.sh downloads some ad block hosts files, does some processing and stores the
processed files for dnsmasq.

The following ad block hosts files are currently used:

* https://adaway.org/hosts.txt
* http://winhelp2002.mvps.org/hosts.txt
* http://hosts-file.net/ad_servers.txt
* https://pgl.yoyo.org/adservers/serverlist.php?hostformat=hosts&showintro=0&mimetype=plaintext
* https://www.malwaredomainlist.com/hostslist/hosts.txt

On ASUSWRT-Merlin, [jffs-scripts-dnsmasq.postconf][3] can be used as [post-configuration
script][4] for dnsmasq is used to run hosts-adblock.rb and add the `addn-hosts` option to
the dnsmasq configuration file `/etc/dnsmasq.conf`.

[1]: http://www.thekelleys.org.uk/dnsmasq/doc.html
[2]: http://www.thekelleys.org.uk/dnsmasq/docs/dnsmasq-man.html
[3]: jffs-scripts-dnsmasq.postconf
[4]: https://github.com/RMerl/asuswrt-merlin/wiki/Custom-config-files#postconf-scripts
