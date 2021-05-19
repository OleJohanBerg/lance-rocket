# Lance Rocket

If you want to see the implementation of the latest specification of RISC-V, [Rocket Chip Generator] (https://github.com/freechipsproject/rocket-chip) is good. However, with this alone, there are no peripheral device modules, so it is not interesting to run it on the FPGA. [Freedom] (https://github.com/sifive/freedom) is a Rocket Chip with a module for controlling peripheral devices and an SDK such as the Board Support Package. It includes modules for various peripherals and even a software development environment. It can be said that this is enough, but Freedom seems to keep the company by selling customized SoC (System on Chip), and the code for FPGA should add wrapper code to the code of SoC. It has a nice shape. Therefore, if you try to port it to an FPGA board other than the one supported by Freedom, it will be quite difficult.

In this project, we will bring code from Rocket Chip Generator and Freedom, implement it in a simple form for FPGA, and create an implementation that can be ported to various boards by editing the constraint file.

We plan to implement the following four levels.

1. RISC-V for learning (TinyLance)
This is for the purpose of studying RISC-V by moving the 32-bit version of Rocket Chip. Port [KOZOS] (http://kozos.jp/kozos/) so that you can study embedded OS. It has a switch, LED, and UART as peripheral devices.
2. For embedded microcontrollers (BabyLance)
It is for applications such as IoT (Internet of Things). In addition to the peripheral devices in 1., it is equipped with DRAM, SD card, Ethernet, and GPIO.
3. For personal computers (Frying Lance)
Based on the 64-bit version of Rocket Chip, in addition to 2 peripherals, a VGA adapter, keyboard and mouse, and USB will be added. Here, we will create a RISC-V version of [Haribote OS] (http://hrb.osask.jp/) called "Kakiwari OS". (If possible, I want to run Linux as well)
4. For high performance computers (ThunderLance)
It is a multi-core version of 3. (If possible, I would like to connect multiple boards to implement a NUMA architecture ...)

At present, "1. RISC-V for learning (TinyLance)" has been completed, and "[Introduction to self-made embedded OS made in 12 steps] (https://www.amazon.co.jp/dp/4877832394)" I have ported up to the 8th step of. The following 12th step is ported in "[Lance Rocket Software Development Kit] (https://github.com/horie-t/lance-rocket-sdk)".

Please refer to [here] (https://github.com/horie-t/freedom) for the build method.
