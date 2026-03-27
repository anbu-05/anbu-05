# Anbu

RTL design | Electronics & Embedded Systems | PCB Design

If you look at the engineering iceberg, you'll find me around the hardware-firmware layer - I've worked on designing RTL, designing the hardware the firmware goes on, written the firmware itself, and put all of this together on physical hardware.

---

## Mars Rover - Team Vyadh

I've been the electrical backbone of a 33-member multidisciplinary rover team for two years, going from junior member to Electrical Head. Most of what I know about hardware came from this.

![rover moving](/attachments/rover_moving.gif)

### Electrical & Firmware
i built a custom **LoRa RF link (SX1278)** for 1 km bidirectional control and telemetry

compared to an off-the-shelf RC, it can carry mixed data (arm position, science feedback, encoder states) on a noise-resistant 433MHz channel.

i also built the traversal control board of the rover you see moving above. it uses an **STM32F446ZE nucleo** board and six **BTS7960 motor drivers**. it can control six seperate 100W 24v motors

![controller](/attachments/half_controller.png)
![trav_ctrl_board](/attachments/half_trav_ctrl_board.png)

### PCB Design

i made a power distribution board able to supply >80A of continuous current to six slot-able cytron MD10C motor drivers at 24v, fits within 100mm x 100mm, has per-rail current sensing shunts

that's a lot of words, but this was the end product:

![PDB_1](/attachments/half_PDB_1.png)
![PDB_4](/attachments/half_PDB_4.png)

and this is the Altium design

![PDB_2](/attachments/half_PDB_2.png)
![PDB_3](/attachments/half_PDB_3.png)

i have also designed a **STM32F103 + RFM98W LoRa devboard** and a 55A 24V motor driver board based on the **IFX007T half H-bridge IC**. these designs have been sent for manufacturing the PCBs, and i'll get it soldered soon 

![LoRa_DB](/attachments/half_LoRa_DB.png)
![motor driver](/attachments/half_motor_driver.png)

<!-- ### Mechanical -->

---

## RISCV SoC

[github.com/anbu-05/Tetrel-RISCV](https://github.com/anbu-05/Tetrel-RISCV)
 
A RISC-V SoC built around PicoRV32 with a custom AXI4-lite interconnect, SRAM, UART, and GPIO.
 
The interesting part isn't the peripherals — it's the interconnect design. Each peripheral assumes it lives at address `0x0`. The interconnect handles offset translation, which means peripheral RTL is completely decoupled from the system memory map. Adding a new peripheral doesn't touch the core or any existing slave.
 
The verification flow uses a signature-based approach — firmware writes pass/fail values to reserved memory addresses. No testbench rewrites when a new peripheral gets added.
 
C firmware built with the RISC-V GCC toolchain and a custom Makefile. Currently migrating from QuestaSim to Cadence Xcelium for a unified toolchain toward physical design.

---

## Skills

**RTL & Digital Design** — Verilog, SystemVerilog, AXI4-lite, FPGA (Cyclone IV, DE2-115), RISC-V assembly  
**Embedded & Firmware** — C, C++, Python, STM32 HAL, bare-metal, UART, SPI, I2C, CAN  
**Hardware & PCB** — Altium, KiCad, schematic capture, layout & routing, SMD soldering, protection circuitry  
**Mechanical** — Fusion 360, 3D printing  
**Tools** — Cadence Xcelium, Virtuoso, QuestaSim, RISC-V GCC Toolchain, Git, STM32CubeIDE  
**Automation** — Siemens S7-1500, TIA Portal

---

## Find me

- 📧 anbuazhagudurai1@gmail.com
- 💼 [linkedin.com/in/anbu2005](https://linkedin.com/in/anbu2005)
- 🌐 [Portfolio](https://anbu-05.github.io)