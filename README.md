# PC Build & Troubleshooting Guide

My 2024 gaming PC build with my cousin, from planning and assembly to setup and diagnosing a real hardware fault. It shows hands-on hardware skills and a structured approach to troubleshooting.

---

## Contents

1. [Build specification](#build-specification)
2. [Planning and compatibility checks](#planning-and-compatibility-checks)
3. [Build process](#build-process)
4. [Software setup and testing](#software-setup-and-testing)
5. [Troubleshooting case study: no power after GPU install](#troubleshooting-case-study-no-power-after-gpu-install)
6. [No-boot troubleshooting checklist](#no-boot-troubleshooting-checklist)
7. [Lessons learned](#lessons-learned)
8. [Future improvements](#future-improvements)

---

## Build specification

| Component | Part |
|---|---|
| CPU | AMD Ryzen 7 7800X3D (8 cores, 3D V-Cache) |
| Motherboard | ASUS TUF Gaming (AM5 socket) |
| GPU | NVIDIA GeForce RTX 4070 |
| RAM | 32 GB DDR5 6000 MHz |
| Storage | 1 TB NVMe SSD (OS and games) + 2 TB HDD (bulk storage) |
| Power supply | Corsair RM850x 850 W 80+ Gold |
| Case | NZXT H510 |
| CPU cooler | Noctua NH-D15 air cooler |

---

## Planning and compatibility checks

Before buying, we checked that the parts would work together:

- **CPU socket and chipset:** the CPU and motherboard both use the AM5 socket, and the board supports DDR5.
- **RAM:** DDR5 at 6000 MHz, a good speed for AM5, enabled through the EXPO profile in BIOS.
- **Power:** an RTX 4070 system draws well under 850 W, leaving headroom for upgrades.
- **Clearance:** the NH-D15 is a very tall cooler, so we checked it against the H510's maximum CPU cooler height (165 mm), and checked GPU length against the case.
- **Storage:** confirmed the motherboard has an M.2 slot for the NVMe SSD and SATA ports for the HDD.

---

## Build process

1. **Prepare:** cleared workspace, used an anti-static wrist strap, and unboxed parts on a non-conductive surface.
2. **Motherboard prep (outside the case):** installed the CPU (aligned the triangle marker, no force), the RAM in the recommended slots (A2/B2 for dual-channel), and the NVMe SSD in the M.2 slot.
3. **Cooler:** applied thermal paste and mounted the NH-D15, then connected the fan to the CPU_FAN header.
4. **Case prep:** installed the I/O shield (if not built-in) and checked the motherboard standoffs.
5. **Mount the motherboard** in the case and screw it in.
6. **PSU:** installed the RM850x and routed the 24-pin, CPU 8-pin and PCIe power cables.
7. **GPU:** fitted the RTX 4070 in the top PCIe x16 slot and connected its power.
8. **HDD:** mounted the 2 TB drive and connected SATA data and power.
9. **Front panel:** connected power switch, USB and audio headers.
10. **Cable management:** tidied cables for airflow, then did a first power-on test before closing the case.

---

## Software setup and testing

1. **BIOS:** checked the CPU, RAM and drives were detected, enabled **EXPO** for 6000 MHz RAM, and set the NVMe SSD as the boot drive.
2. **Windows:** installed Windows on the NVMe SSD from a bootable USB drive.
3. **Drivers:** installed the chipset and GPU drivers, then ran Windows Update.
4. **Storage:** initialised and formatted the 2 TB HDD in Disk Management.
5. **Stability testing:** ran the system under load and monitored temperatures to confirm it was stable.

---

## Troubleshooting case study: no power after GPU install

**Problem**
After installing the GPU, the PC would not power on at all: no fans, no lights.

**Approach** (CompTIA troubleshooting methodology)

| Step | What we did |
|---|---|
| 1. Identify the problem | Total no-power: no fans, LEDs or beeps. This pointed to power delivery, not a boot or display issue. |
| 2. Establish a theory | Possible causes: loose power cables, front-panel power switch, faulty component short, or a faulty PSU. |
| 3. Test the theory | Checked all power connections and the seating of every component. Tested the RAM and GPU individually to rule them out. Researched the symptoms in troubleshooting guides. |
| 4. Isolate | With the cables, RAM and GPU ruled out, the evidence pointed to the PSU, which we identified as faulty. |
| 5. Fix | Replaced the faulty unit with the **Corsair RM850x 850 W**. |
| 6. Verify | The system booted, all components were detected, and it stayed stable under load. |
| 7. Document | Recorded the fault and fix here. |

**Result:** the system booted successfully and has run reliably since.

**What it showed me:** changing one thing at a time and working from the simplest setup up is faster and more reliable than guessing.

---

## No-boot troubleshooting checklist

| Symptom | Check first | Then |
|---|---|---|
| No power at all | Wall socket, PSU switch, 24-pin and CPU 8-pin cables, front-panel power header | Test with a known-good PSU |
| Fans spin but no display | Monitor plugged into the **GPU** (not the motherboard), GPU power cables | Re-seat RAM and GPU, check motherboard debug LEDs |
| Long first boot on AM5 | Normal: DDR5 memory training can take a few minutes | Wait before assuming a fault |
| RAM not at rated speed | EXPO/XMP disabled | Enable EXPO in BIOS |
| Overheating or shutdowns | Cooler mounting, thermal paste, fan headers | Check temps in HWMonitor |
| Drive not detected | M.2 screw/seating, SATA cables | Initialise in Disk Management, check BIOS |

---

## Lessons learned

- **Follow a logical process.** Isolate one variable at a time instead of guessing.
- **Check compatibility before building.** Socket, RAM type, cooler clearance and PSU wattage all matter.
- **Communicate clearly.** Explaining each step to my cousin made the build smoother and safer.
- **Attention to detail prevents damage**, from bent pins to poorly seated cables.

---

## Future improvements

- Add photos of each build stage.
- Document future upgrades (storage expansion, RAM).
- Expand into a knowledge base of common PC faults and fixes.

---

*Author: [ArcSkt1](https://github.com/ArcSkt1) · CompTIA A+ · CompTIA Network+*
