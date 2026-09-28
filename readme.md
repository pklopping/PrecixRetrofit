# Precix CNC Retrofit

This repo contains two main folders
* [LinuxCNC](LinuxCNC/)
* [Schematics](Schematics/)

## LinuxCNC

This folder contains all of the configurations to run a (fairly) vanilla version of the
Axis GUI in LinuxCNC. 

### Execution

__This needs validation and explanation__

```bash
linuxcnc precix.ini
```

## Schematics

This folder contains a KiCAD project that describes the physical build

![Schematic](docs/Precix%20Retrofit%20Schematic%20Rev~.svg)


# Lingering TODOs

* Spindle speed visualization and control improvements
  * Currently there's no feedback on the spindle speed and there are only rudimentary controls
