#McDebian - for Linksys WRT1900AC V1
Linux Kernel version is "4.7.6".

Debian root files system is "Jessie" stable.


#####The wireless driver is updated to the lastest version.
#####NAND timeout patch.
#####fancontrol implementation.
#####bridge all card
#####firewall 
#####gpio_keys(wps: need testing)
#####

#### Care with an Intel 7260AC client, You must disable power save in your options card.

Only for advertising user.

I make a try : DHCP failover between wrt1900ac and firewall.
<pre>
  +------+              +------+
  |      |              |      |
  |      +--------------+      |
  |      |              |      |
  +------+              +------+
  firewall              wrt1900ac
192.168.10.1           192.168.10.10
</pre>


Firewall: The rules are inspired from ipfire rules, script from debian.org's forum.

While wrt1900ac is in middle of my local network, 
it'll drop all broadcast 67/68 udp port in forward.
bypassed log of DROPNEWNOTSYN.
