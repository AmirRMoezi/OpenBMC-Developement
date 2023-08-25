# How to change OpenBMC IP address at runtime?

To change OpenBMC IP address at runtime, the commands below should be executed in order:
<pre>
  <code>
$ busctl set-property xyz.openbmc_project.Network /xyz/openbmc_project/network/eth0 xyz.openbmc_project.Network.EthernetInterface DHCPEnabled s     
  "xyz.openbmc_project.Network.EthernetInterface.DHCPConf.none"
$ busctl call xyz.openbmc_project.Network /xyz/openbmc_project/network/eth0 xyz.openbmc_project.Network.IP.Create IP ssys "xyz.openbmc_project.Network.IP.Protocol.IPv4" 
  "111.222.111.222" 24 "111.222.111.0"
$ ip link set eth0 down
$ ip link set eth0 up
$ networkctl reload
$ ifconfig
  </code>
</pre>

After executing the commands<=, IP address of eth0 interface will be changed to 111.222.111.222 static address with 255.255.255.0 subnet mask. change the IP address to whatever you want. 
