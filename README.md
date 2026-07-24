# SerDes Communication Protocol on Seven-Segment Display



A Verilog HDL implementation of a SerDes (Serializer/Deserializer) communication protocol, verified through simulation and displayed on a seven-segment display via FPGA implementation on Xilinx Vivado.


## About the Project

The SerDes (Serializer/Deserializer) Communication Protocol is designed to convert parallel data into serial form for transmission, and then reconstruct the original parallel data at the receiver. The received output is displayed on a seven-segment display.

This project demonstrates RTL design, digital communication concepts, Verilog coding, simulation, and FPGA-based implementation using Xilinx Vivado — covering the full flow from design to verification to hardware-ready output.

## Why This Project

Serial communication is at the core of nearly every modern digital system — from UART and SPI to high-speed interfaces like PCIe and USB. Building a SerDes from scratch, and visualizing the result on real hardware output (a seven-segment display), is a way to connect the theory of serialization/deserialization to a working, observable digital design.

## Technologies Used

| Category | Tools / Concepts |
|---|---|
| HDL | Verilog |
| Simulation | Xilinx Vivado Simulator |
| Synthesis / Implementation | Xilinx Vivado |
| Design Style | RTL (Register Transfer Level) |
| Verification | Testbench-based simulation |
| Target | FPGA / Seven-Segment Display |

## Architecture

```
Parallel Data
      │
      ▼
+-------------+
| Serializer  |
+-------------+
      │
Serial Data
      │
      ▼
+---------------+
| Deserializer  |
+---------------+
      │
Parallel Data
      │
      ▼
Seven-Segment Display
```

**Flow:**
1. Parallel input data is loaded into the **Serializer**, which shifts it out one bit at a time as serial data.
2. The **Deserializer** receives the serial stream and reconstructs it back into parallel form, bit by bit, using a shift register.
3. The reconstructed parallel data is decoded and driven onto a **seven-segment display**, confirming that the data survived the serialize → transmit → deserialize cycle intact.

## Folder Structure

```
SerDes-communication-protocol-on-seven-segment-display/
├── README.md
├── LICENSE
├── Project_Report.pdf
├── Source_Code/
│   ├── serializer.v
│   ├── deserializer.v
│   ├── seven_segment.v
│   └── top_module.v
├── Simulation/
│   ├── waveform.png
│   ├── testbench.v
│   └── simulation_result.pdf
└── Screenshots/
    ├── rtl.png
    ├── technology.png
    └── output.png
```

## Source Code

| File | Description |
|---|---|
| `serializer.v` | Converts parallel input data into a serial bitstream |
| `deserializer.v` | Reconstructs parallel data from the incoming serial stream |
| `seven_segment.v` | Decodes the recovered data and drives the seven-segment display |
| `top_module.v` | Top-level module integrating serializer, deserializer, and display driver |

## Simulation

![Waveform](Simulation/waveform.png)

Simulation was performed using the Xilinx Vivado simulator with a dedicated testbench (`testbench.v`) to verify correct serialization and deserialization timing, bit ordering, and data integrity.

- `waveform.png` — simulation waveform output
- `simulation_result.pdf` — detailed simulation report

## Output

![Output](Screenshots/output.png)

- The **Serializer** successfully converts parallel input data into serial format.
- The **Deserializer** reconstructs the original parallel data from the serial stream.
- The received data is correctly decoded and displayed on the **seven-segment display**, confirming end-to-end data integrity.

## Applications

- Communication Systems
- FPGA Prototyping
- Digital Electronics
- Embedded Systems
- ASIC Design

## Future Scope

- High-speed SerDes implementation
- Error detection and correction (parity/CRC)
- Multi-channel communication support
- ASIC-level implementation and timing closure

## Skills Demonstrated

- Verilog HDL
- RTL Design
- Digital Logic Design
- Testbench-based Simulation
- FPGA Design Flow
- Xilinx Vivado

## Author

**Medisetti Trisha**
B.Tech, Electronics and Communication Engineering
2027 Graduate

## License

This project is licensed under the [MIT License](LICENSE).
