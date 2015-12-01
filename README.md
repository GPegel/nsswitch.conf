# nsswitch.conf
DNS issues Virtual Box / Example configuration of GNU Name Service Switch functionality.

The original /etc/nsswitch.conf looks like this:

# /etc/nsswitch.conf


passwd:         compat
group:          compat
shadow:         compat

hosts:          files mdns4_minimal [NOTFOUND=return] dns
networks:       files

protocols:      db files
services:       db files
ethers:         db files
rpc:            db files

netgroup:       nis


But to get rid of the DNS issues in a .local environemnt while being loggen in into a virtual Ubuntu instance in VirtualBox you have to change line that says "hosts" into "files dns"
