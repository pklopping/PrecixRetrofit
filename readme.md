# Precix CNC Retrofit

## The Problem

This repo contains LinuxCNC configurations and electrical schematics for a Precix CNC retrofit. When this project started the author was spending a fair amount of time using a 30-year old CNC controller. The old controller ran an archaic version of linux (QNX 4.25) that couldn't connect to the internet, and also lacked any modern storage media interfaces. To copy g-code the only interface available was a floppy drive emulator requiring USB disks to only have 1.44MB partitions. 

## The Fix

The author decided to build a drop-in replacement controller using modern hardware and software. They chose to use Beckhoff EtherCAT modules for the servo controllers and IO, and LinuxCNC for the controlling software. What resulted was the build below. The physical interface is a 1:1 plug-for-plug match with the original controller.

## Complaints Addressed

The following are all of the complaints about the original Precix controller that have been, or can now be addressed

* No internet access :white_check_mark:
  * Users couldn't browse the internet, download files, or do research on the computer
* Limited g-code size per transfer :white_check_mark:
  * By using a modern version of linux users can use full-size flash drives, or download large files from the internet
* No helical moves :white_check_mark:
  * Users no longer need to configure their Fusion post processor to avoid helical moves, this dramatically reduces file sizes
* No drill macros :white_check_mark:
  * The Precix controller doesn't understand drill macros and can easily scrap parts if you try to use one
* Poor toolpath visualizations :white_check_mark:
  * The Precix software only provides a top-down view of the toolpaths with no depth. LinuxCNC will render an interactive 3D view of the toolpaths
* No tool probe :soon:
  * An electrical port on the spindle mount is now wired to enable a removable probe, but this needs to be designed, manufactured, and programmed before use

## What's in the repo

This repo contains two main folders

## [LinuxCNC](LinuxCNC/)

This folder contains all of the configurations to run a (fairly) vanilla version of the
Axis GUI in LinuxCNC. 

### Execution

__This needs validation and explanation__

```bash
linuxcnc precix.ini
```

## [Schematics](Schematics/)

This folder contains a KiCAD project that describes the physical build

![Schematic](docs/Precix%20Retrofit%20Schematic%20Rev~.svg)


# Lingering TODOs

* Spindle speed visualization and control improvements
  * Currently there's no feedback on the spindle speed and there are only rudimentary controls
