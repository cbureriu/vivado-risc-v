# RISC-V SoC for Xilinx Vivado running Debian Linux

based on work by Eugene Tarassov https://github.com/eugene-tarassov/vivado-risc-v

## Prerequisites
```
Ubuntu (recommended: 8-core CPU, 32 GB RAM)
Xilinx Vivado 2021.2
```
## Build Environment
```
git clone https://github.com/cbureriu/vivado-risc-v
make update-submodules
```
## CPU Configurations
```
https://github.com/cbureriu/vivado-risc-v/blob/master/src/main/scala/rocket.scala
```
## build FPGA bitstream
```
make CONFIG=rocket64b2 BOARD=nexys-video vivado-gui
```

### 64-bit RISC-V cores (Linux supported)
```
rocket64b1 - 1 core
rocket64b2 - 2 cores
rocket64b2l2 - 2 cores with 512KB level 2 cache
rocket64b2gem - 2 cores with 512KB level 2 cache and Gemmini accelerator
rocket64b4l2w - 4 cores with 512KB level 2 cache and wide 256-bit memory bus
rocket64b4 - 4 cores
rocket64b8 - 8 cores
```
### 64-bit Sonic BOOM cores (Linux supported)
```
rocket64w1 - 1-wide Small BOOM, 1 core
rocket64x1 - 2-wide superscalar Medium BOOM, 1 core
rocket64y1 - 3-wide superscalar Large BOOM, 1 core
rocket64z1 - 4-wide superscalar Mega BOOM, 1 core
```
### 32-bit small RISC-V cores (Linux not supported)
```
rocket32s1 - 1 core
rocket32s2 - 2 cores
rocket32s4 - 4 cores
rocket32s8 - 8 cores
rocket32s16 - 16 cores
```
## FPGA utilization [LUTs]
```
32-bit small RISC-V: 10,800 + 6,100 per core
64-bit big RISC-V: 10,800 + 27,500 per core
2-wide superscalar Medium BOOM, 1 core, L2 cache: 148,500
3-wide superscalar Large BOOM, 1 core, L2 cache: 252,700
```
