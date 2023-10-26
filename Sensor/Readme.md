# Step1 : edit dts file in linux kernel:

devtool modify linux-aspeed     #change dts in the generated source code in build/workspace directory. then save it.
bitbake obmc-phosphor-image -c clean
bitbake obmc-phosphor-image

# Step2 : add new sensors to i2c bus
open dts file
