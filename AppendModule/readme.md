# How to append extra modules to OpenBMC
To append extra modules to OpenBMC, you can simply put the command below in the local.conf file of your OpenBMC/buld directory:
<pre>
  <code>
IMAGE_INSTALL:append = "apt"
  </code>
</pre>
According to this command, apt will be installed on OpenBMC after executing bitbake command again.
