# How to append extra modules to OpenBMC
To append extra modules to OpenBMC, you can simply put the command below in the local.conf file of your machine configuration file.
<pre>
  <code>
IMAGE_INSTALL:append = "apt"
  </code>
</pre>
According to this command, apt will be installed on OpenBMC after executing bitbake command again. The configuration file for ast2500-evb is located in this path:
<pre>
  <code>
openbmc/meta-aspeed/conf/machine
  </code>
</pre>
A sample configuration file is included in the repository.
