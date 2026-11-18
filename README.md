# Dual-Output Regulated Power Supply

A Proteus schematic study of an AC-to-DC supply with intended 12 V and 9 V regulated outputs. The project explores the relationship between transformer voltage, full-wave rectification, filtering, and fixed linear regulators.

![Proteus schematic showing the source, transformer, bridge, regulators, and example load branches](<Screenshot 2026-02-07 115247.png>)

## Design intent

| Stage | Component shown | Purpose |
| --- | --- | --- |
| AC source | V1 | Represents a 50 Hz sine source at 325 V peak, approximately 230 V RMS. |
| Voltage conversion | TR1 | Models a step-down transformer for the secondary voltage. |
| Rectification | BR1 | Uses a diode bridge to turn both half-cycles of the secondary waveform into pulsating DC. |
| Filtering | C1 and C2 | Capacitors shown in the draft schematic. In a conventional reservoir stage, a capacitor across the rectified DC rails supplies the load between waveform peaks and reduces ripple. |
| Regulation | U1 and U2 | The 7812 and 7809 target nominal fixed outputs of 12 V and 9 V respectively. |
| Output demonstration | Switched load branches | Provide example points for observing each intended output under load in simulation. |

```text
Intended signal flow
AC source -> transformer -> bridge rectifier -> filtered DC -> fixed regulators -> load outputs
```

## What to inspect in Proteus

- **Transformer secondary.** Compare the secondary waveform with the input waveform and check how much voltage is available for the rectifier and regulators.
- **Bridge output and return.** Identify both DC terminals of the bridge and trace a complete return path for the following stages.
- **Filter behavior.** Compare the rectified waveform with the filtered regulator input. With a 50 Hz source and full-wave rectification, ripple repeats at 100 Hz.
- **Regulator headroom.** Observe the minimum input between ripple peaks and compare it with the needs of the chosen regulator model under load.
- **Load changes.** Compare both output voltages with their switches open and closed. Record the observed voltages and ripple separately from the intended 12 V and 9 V setpoints.

## Schematic review notes

The screenshot shows C1 inline between the bridge and the 7812 input, and C2 inline between the two regulators. The connection from the bridge's other DC terminal to the regulator return is unclear. These are points to check before using the drawing to evaluate DC regulation. The reference image contains no output waveforms or measurements, so 12 V and 9 V describe the design targets.

## Repository contents

- [Full-size Proteus schematic screenshot](<Screenshot 2026-02-07 115247.png>)
- This README with the design intent and a simulation review checklist

The available artifact is a schematic image. An editable Proteus project and simulation measurements would be useful additions for reproducibility. This project is documented as a simulation study.
