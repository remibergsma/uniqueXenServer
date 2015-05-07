# uniqueXenServer
Make a XenServer unique after cloning from a template

When you clone a XenServer from a template, they all get the same uuid. Add this script to the template and make sure it is executed on the first boot. This will make it unique.

Usage
=====
./xenserver_make_unique.sh

Add this script to the template and make it run just once after cloning. It will reboot twice and then your unique XenServer is ready for use.
