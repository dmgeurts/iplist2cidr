# iplist2cidr
Random list of IP addresses to ordered list of CIDRs

** Bring together existing tools to be more useful **

Occasionally I find myself cleaning up firewall, router/switch and proxy configurations. Often there's a list of host addresses in some random order, with duplicates and other atrocities. Too big for anyone to dare to touch. For ease of use, readability and efficiency it's best to convert these things to a shorter list of CIDR notations. I've found some useful tools but nothing where I can just dump a list of unordered IP addresses and see what the resulting list of CIDRs would be.

PHP seems an obvious candidate due to the available code and ease of web integration as well as terminal usage.

Tools:
- [x] Sort a list of IP addresses. http://www.brainbell.com/tutorials/php/Sorting_IP_Addresses_(as_A_Human_Would).htm
- [ ] Deduplicate sorted list, if the sort above doesn't do this.
- [ ] Convert consecutive IP addresses to IP ranges, for feeding to the next stage.
- [x] IP range to CIDR conversion. http://www.derman.com/blogs/IP-Range-to-CIDR-Calculator "The bulk of the following code is from /etc/inc/util.inc in pfSense v2.0.2"

The result should be a sorted list of CIDRs.

** Limitations of existing tools **
- ip2cidr requires IP ranges, it only takes two arguments and not a list like: 1.1.1.1 / 1.1.1.2 / 1.1.1.3 etc., you get the point.
- A few existing online tools allow multiple IP ranges to be pasted, on per line. But this does not help me as I'd still have to feed it a sanitised list, by which time I'm quicker converting it manually.
