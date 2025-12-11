# Prusa MK4(S) Klipper configuration

## Installation

This configuration uses features which are not yet available in the Klipper
master branch. Use the `mk4` branch in the prusa-custom-firmware klipper
repository. https://codeberg.org/prusa-custom-firmware/klipper/src/branch/mk4

An MCU configuration is provided in `mcu-config`.

 - Copy it to your Klipper source directory
 - Rename the copy to `.config`
 - Optionally run `make menuconfig` to see the settings
 - Follow the steps at https://prusa-cfw.fox.gal/installation_guide/mk4/

It is recommended that you do not edit most of the `.cfg` files provided, but
instead override the values.

 - Copy printer.cfg.example to printer.cfg in your Klipper config directory
 - Crease symlinks in your Klipper config directory which point to the
   `prusa-mk4` and `macros` directories within this repository. eg, `cd
   ~/printer_data/config ; ln -s ~/mk4-klipper-config/{macros,prusa-mk4} .`

## Configuration/calibration

Most values are configured to match the default Prusa firmware, some are
values which seemed to work while developing this configuration, and others are
set to try to make it less likely that you break your printer while setting up,
and will require changes to work. Here are the values which you should tune:

 - You must set the correct serial device path for the MCU to use. An example
   is provided in `printer.cfg.example`.
 - The StallGuard thresholds should be configured for your printer. Example
   sections are provided in `printer.cfg.example`.
   https://www.klipper3d.org/TMC_Drivers.html#sensorless-homing
 - You must calibrate the load cell for probing.
   https://www.klipper3d.org/Load_Cell.html#calibrating-a-load-cell
