# Precix CNC Retrofit

## The Problem

This repo contains LinuxCNC configurations and electrical schematics for a Precix CNC retrofit. When this project started the author was spending a fair amount of time using a 30-year old CNC controller. The old controller ran an archaic version of linux (QNX 4.25) that couldn't connect to the internet, and also lacked any modern storage media interfaces. To copy g-code the only interface available was a floppy drive emulator requiring USB disks to only have 1.44MB partitions. 

## The Fix

The author decided to build a drop-in replacement controller using modern hardware and software. They chose to use Beckhoff EtherCAT modules for the servo controllers and IO, and LinuxCNC for the controlling software. What resulted was the build below. The physical interface is a 1:1 plug-for-plug match with the original controller.

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
