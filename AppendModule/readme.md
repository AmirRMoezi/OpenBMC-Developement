# How to append extra modules to OpenBMC
To append extra modules to OpenBMC, you can simply put the command below in the local.conf file of your OpenBMC/buld directory:
<pre>
  <code>
IMAGE_INSTALL:append = " python3 apt"
  </code>
</pre>
According to this command, apt and python will be installed to OpenBMC after executing bitbake command again.
