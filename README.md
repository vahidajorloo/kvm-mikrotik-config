# kvm-mikrotik-config
1- kvm must installed on ubuntu 22
2- we need 2 ethernet links on virtualizor server, one for internet that is connected to network switch and another one that is connected to ILO switch.
3- we create 2 network bridges:
+ viibr0 for internet that is called permanent bridge in virtulizor site (with eno49 or eno50)
+ viifbr-ilo for accessing to ILO switch (with eno1 to eno4)
+ we need to download the mikrotik image for kvm with qcow2 format that is available in internet and place it in /var/virtualizor/kvm/mikrotik.qcow2
+ then we create a vm from virtualizor panel and after the server is ready we must shutdown it.
+ then we connect to virtualizor server with ssh and edit that vm configs:
+ for example if the server's id that we created is 1002 we execute:
virsh edit --domain v1002
+ then copy the v1002.xml file contents in it.
after that if everything is ok we execute:
virsh start --domain v1002
after that we can login to our mikrotik server.
