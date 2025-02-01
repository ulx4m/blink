# Blink ULX4M LED

## Connecting ULX4M

You need to connect to USB1 (US1) connector to the host computer in order to program the board.

<img src="https://github.com/intergalaktik/ulx4m-documentation/blob/main/pic/ulx4m-ld.png?raw=true" width="400">

<img src="https://github.com/intergalaktik/ulx4m-documentation/blob/main/pic/ulx4m-ls.png?raw=true" width="400">

## Download programmer

Download and install openFPGALoader for your OS

https://trabucayre.github.io/openFPGALoader/guide/install.html

## Uploading

To upload blink led bitstream, hold BTN1 or turn on DIP SW1 and plug
USB.

```
cd blink
openFPGALoader --dfu --vid 0x1d50 --pid 0x614b --altsetting 0 blink_85f.bit
```

On linux you may need to add udev rule

https://github.com/emard/ulx3s/blob/master/doc/MANUAL.md#programming-over-usb-port-us1

## Build your own blink LED

This blinky is based on the [ULX3S-Blinky project](https://github.com/DoctorWkt/ULX3S-Blinky) from @Doctorwkt. This example blinks an LED using FPGA code.

It is assumed the yosys, nextpnr toolchain has been already installed. If not, see [instructions here](https://github.com/emard/ulx3s/blob/master/doc/MANUAL.md#precompiled-opensource-tools-for-all-platforms)

First you will need to install verilator

```
sudo apt-get install verilator
```

Default size in Makefile is 85F - you can change it here:

https://github.com/ulx4m/blink/blob/main/Makefile#L69

Depending on your version make ls or ld bitstream

```
make clean
make ulx4m-ls.bit
make prog
```

```
make clean
make ulx4m-ld.bit
make prog
```

# Next steps

Now, you're ready for the next steps, we suggest following:

  - https://github.com/lawrie/ulx4m_examples
  - https://github.com/lawrie/ulx4m_amaranth_examples
  - https://github.com/emard/ulx3s-misc
  - https://github.com/emard/had2019-playground/tree/master/projects/bootloader
  - https://github.com/goran-mahovlic/mipi-csi-2
  - https://github.com/hdl4fpga/hdl4fpga

Or explore different projects available at: https://ulx4m.github.io/

# Chat and support

Discord chanel

  - https://discord.gg/qwMUk6W (problems/question/general chat)
