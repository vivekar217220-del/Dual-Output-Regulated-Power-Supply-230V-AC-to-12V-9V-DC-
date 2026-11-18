# Dual-Output Regulated Power Supply

A Proteus simulation of a supply that converts a 230 V AC input into regulated 12 V and 9 V DC outputs.

![Dual-output power supply schematic in Proteus](<Screenshot 2026-02-07 115247.png>)

## Circuit stages

| Stage | What it does |
| --- | --- |
| Step-down transformer | Lowers the AC voltage before rectification. |
| Bridge rectifier | Produces pulsating DC. |
| Filter capacitors | Smooth the rectified voltage before regulation. |
| 7812 and 7809 regulators | Provide the 12 V and 9 V outputs. |

The repository contains a [screenshot of the Proteus simulation](<Screenshot 2026-02-07 115247.png>).
