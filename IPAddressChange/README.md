# How to change OpenBMC IP address during runtime?

To modify the OpenBMC IP address during runtime, it is necessary to execute the following commands in sequence:
<pre>
  <code>
$ busctl set-property xyz.openbmc_project.Network /xyz/openbmc_project/network/eth0 xyz.openbmc_project.Network.EthernetInterface DHCPEnabled s     
  "xyz.openbmc_project.Network.EthernetInterface.DHCPConf.none"
$ busctl call xyz.openbmc_project.Network /xyz/openbmc_project/network/eth0 xyz.openbmc_project.Network.IP.Create IP ssys "xyz.openbmc_project.Network.IP.Protocol.IPv4" 
  "XXX.XXX.XXX.XXX" 24 "XXX.XXX.XXX.0"
$ ip link set eth0 down
$ ip link set eth0 up
$ networkctl reload
$ ifconfig
  </code>
</pre>
Upon the execution of the provided commands, the IP address of the eth0 interface will be modified to XXX.XXX.XXX.XXX, set as a static address with a subnet mask of 255.255.255.0. You are free to adjust the IP address as needed. The configuration file is accessible via the specified path:
<pre>
  <code>
/etc/systemd/network
  </code>
</pre>
