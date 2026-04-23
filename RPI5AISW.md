#  Raspberry Pi 5 AI Software
https://www.raspberrypi.com/documentation/computers/ai.html

This page provides instructions for running AI models powered by Hailo NPUs on Raspberry Pi 5. The Hailo NPU is an AI accelerator chip designed to run neural networks; instead of Raspberry Pi’s CPU doing the AI work, the NPU handles it more efficiently.

You can connect a Hailo NPU to your Raspberry Pi 5 using either:
* Raspberry Pi AI Kit, which consists of an M.2 HAT+ with a pre-installed Hailo-8L NPU.
* Raspberry Pi AI HAT+ with either an on-board Hailo-8L NPU or an on-board Hailo-8 NPU.
* Raspberry Pi AI HAT+ 2 with an on-board Hailo-10H NPU.

---
## Hardware prerequisites

Running AI models requires a Raspberry Pi 5 with a 64-bit Raspberry Pi OS installation (Trixie) and one of the following Hailo AI accelerator (NPU) options:

* A Raspberry Pi AI HAT+ or AI HAT+ 2 (recommended), both of which have an on-board Hailo module. For more information about these accessories, see AI HATs.
* A Raspberry Pi AI Kit, which includes an M.2 HAT+ with a Hailo-8L AI accelerator pre-installed. For more information about the AI Kit, see AI Kit.

---
## Software prerequisites
Before running vision AI models or GenAI models on your Raspberry Pi 5, you must configure the required software. Broadly, this consists of the following tasks, performed in order:

1. Enable PCIe Gen 3.0 (AI Kit only). Manually configure the PCIe interface to allow the Hailo NPU to communicate at full speed. This is only necessary for the AI Kit.
2. Update Raspberry Pi OS. Ensure that your Raspberry Pi OS packages are fully up to date.
3. Install required dependencies. Install the necessary software dependencies that allow the operating system (OS) and applications to detect, communicate with, and run AI models on the Hailo NPU.
4. Reboot and verify. Verify that your AI hardware is correctly detected and ready to use.

---
## Run vision AI models on Raspberry Pi 5
