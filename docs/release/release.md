# Release notes

## Version 2.0.2 - Nov. 10, 2026

### Improved

- Updated the README to list AMD 7-series and UltraScale FPGA support and Vivado 2025.2 or earlier as the tested tool environment. No RTL changes were included. ([06e2c4d](https://github.com/RyotaroHonda/LACCP/commit/06e2c4d4e5a27d66a8ccca254e68a29a3297d7d8))

## Version 2.0.1 - Dec. 19, 2025

### Fixed

- Restored Heartbeat Unit changes that had been lost or changed in the initial v2.0 commit. ([169bad7](https://github.com/RyotaroHonda/LACCP/commit/169bad76d0051376401bb518c8a00de032bde187))
    - Restored the `clkDiv16` output and divide-by-16 logic in both `HeartBeatUnit` and `PrimaryHeartBeatUnit`.
    - Corrected heartbeat-frame state packing in `PrimaryHeartBeatUnit` and decoding in `HeartBeatUnit`, using the four-bit state field in register bits 31:28.

## Version 2.0 - Dec. 16, 2025

### New

- Expanded support to AMD Xilinx UltraScale/UltraScale+ FPGAs, in addition to 7-series FPGAs. ([fc2d2b1](https://github.com/RyotaroHonda/LACCP/commit/fc2d2b160a74a1b499776b3c29508d70b76b5020))
    - Added `CalcFineLantency_US` for receiver-delay calculation using initial master and slave IDELAY counter values, tap count, and SerDes latency.
    - Extended RCAP to exchange the initial counter values and calibration parameters at local address `0x2`.
- Added timing and calibration interfaces to `LaccpMainBlock` and RCAP.
    - Added `cntValueInitIn`, `cntValueSlaveInitIn`, `cntValueInitOut`, and `cntValueSlaveInitOut` for initial IDELAY counter values.
    - Added the `roundTripTime` output.
    - Added `calibDelay`, `calibDelayOut`, and the `enCalibDelay` generic for optional calibration, including a family-dependent digital-delay correction.

## Update - May 27, 2025

### New

- Added the `clkDiv16` output to `PrimaryHeartBeatUnit`. The divide-by-16 counter is reset by the unit's reset or heartbeat signal. ([0aa6944](https://github.com/RyotaroHonda/LACCP/commit/0aa6944a0cc8dd5a6682696c820c4a0339dc8ced))

## Update - May 19, 2025

### New

- Added the `clkDiv16` output to `HeartBeatUnit`, with the same reset and heartbeat realignment behavior. ([a050381](https://github.com/RyotaroHonda/LACCP/commit/a0503819584c4a1a792e0a43384d653bb0f0a7c1))

## Update - Dec. 24, 2024

### Fixed

- Corrected heartbeat-frame state decoding in `HeartBeatUnit`. Added `kWidthFrameState = 4` and used it to extract register bits 31:28 instead of including the reserved bits. ([7e7d6b2](https://github.com/RyotaroHonda/LACCP/commit/7e7d6b2acb91fd15bbfa34a8f7c20aa788f8e58c))

## Update - Dec. 12, 2024

### Fixed

- Corrected the frame-information register value in `PrimaryHeartBeatUnit` by inserting two reserved zero bits between the frame state and frame flags. This produces the required 32-bit register value. ([c650e5a](https://github.com/RyotaroHonda/LACCP/commit/c650e5a85402f5bd9ea570ebde1b8917dba4dc39))

## Version 1.0 - Dec. 4, 2024

### New

- First de facto release, supporting AMD 7-series FPGAs. ([0f53a79](https://github.com/RyotaroHonda/LACCP/commit/0f53a7969d51b6413137c37c36158c4ec603cec3))
- Added dual licensing under the Apache License Version 2.0 and Mozilla Public License Version 2.0.
