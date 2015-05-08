# uniqueXenServer
Make a XenServer unique after cloning from a template

When you clone a XenServer from a template, they all get the same uuid. Add this
script to the template and make sure it is executed on the first boot. This will
make it unique.

Usage
=====

./xenserver_make_unique.sh start

Add this script to the template and make it run just once after cloning. It will
reboot twice and then your unique XenServer is ready for use.

To use this in a VM template for testing XenServer hosts in VMs:

scp xenserver_make_unique.sh root@xenserver-host-ip:/opt/
scp init.d/xenserver_make_unique root@xenserver-host-ip:/etc/init.d/
ssh root@xenserver-host-ip "chmod +x /etc/init.d/xenserver_make_unique && chkconfig xenserver_make_unique on"

When the XenServer host starts for the first time, it would reset the host uuid
by running the script from /opt/xenserver_make_unique.sh, then remove the init.d
script and reboot the host.
