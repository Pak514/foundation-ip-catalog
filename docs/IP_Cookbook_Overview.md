# Foundation IP & Basic Blocks Cookbook
## Nodes: TSMC 12nm (12FFC/N12), Samsung 14nm (14LPP/14LPE), GlobalFoundries 12nm (12LP)

**Disclaimer**: All content is educational/conceptual. Actual standard cell libraries, PDKs, and hard IP are proprietary to foundries and IP vendors. No foundry-qualified layouts or silicon-proven models are provided. Use only for learning RTL concepts.

### Process Node Public Parameters (Approximate)
- **TSMC 12FFC**: Poly pitch ~90-96 nm, Fin pitch ~42-48 nm, Cell heights: 6T (UHD), 7.5T, 9T, 10.5T, 12T. Multi-VT (SVT/HVT/LVT). Optical shrink from 16FFC.
- **Samsung 14LPP**: Fin pitch ~48 nm, Poly pitch 78 nm (HD) / 84 nm (HP), Cell heights: 9T (HD/HP), 10.5T (UHP). Density ~32-37 MTr/mm².
- **GF 12LP**: Derived from Samsung 14nm, Fin pitch ~48 nm, Poly ~84 nm, New 7.5T HD cell (~480 nm height), ~36.7 MTr/mm². Improved density ~1.2x vs 14LPP.

### Core Catalog Entries (Starter Set)

#### 1. Standard Cell / Foundation Logic
- **INV (Inverter)**: Basic CMOS inverter. Multi-drive strength (X1-X16), multi-VT. Track height variants for density vs performance.
- **NAND2 / NOR2 / AOI21**: Complex gates for area efficiency.
- **DFF (D Flip-Flop)**: Async reset/set, scan-enabled variants. Clock gating cells.
- Recipe: Synthesize with multi-VT libs; use short tracks for density, tall for drive.

#### 2. Power Management
- **LDO Digital Interface**: Enable, voltage select, status.
- **DCDC PWM Controller**: Digital PWM generator, soft-start, current limit interface.
- Recipe: Combine with analog power FETs (proprietary hard IP).

#### 3. Data Conversion
- **8-bit SAR ADC Controller**: Sample, binary search sequencer, result register.
- **DAC Interface**: Parallel or SPI input to analog output (analog proprietary).

#### 4. SerDes
- **Digital Serializer / Deserializer**: Parallel-to-serial, serial-to-parallel with simple CDR interface.

#### 5. Signal Processing
- **MAC Unit**: Multiply-accumulate for DSP.
- **Simple FIR Filter**: Tap delay line + MAC.

#### 6. Processing
- **16-bit RISC CPU Skeleton**: Fetch-decode-execute, basic ALU, register file.
- **32-bit Extension**: Wider datapath version.

#### 7. Memory Digital
- **SRAM Wrapper**: Address decoder conceptual, BIST interface (compiler proprietary).

#### 8. Emerging
- **RRAM/MRAM Digital Controller**: Pulse generation interface for write/read (array proprietary).
