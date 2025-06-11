# Raspberry Pi 5 and Hailo AI Accelerator

---
## Raspberry Pi 5 Overview
https://www.raspberrypi.com/products/raspberry-pi-5/

* Arm Cortex-A Processor Comparison Table
  * https://developer.arm.com/documentation/102826/latest/

<img src="https://github.com/user-attachments/assets/509e5ebf-c3cd-4d29-9308-549432619e37" width=650>

* Broadcom BCM2712 2.4GHz quad-core 64-bit Arm Cortex-A76 CPU, with cryptography extensions, 512KB per-core L2 caches and a 2MB shared L3 cache
* VideoCore VII GPU, supporting OpenGL ES 3.1, Vulkan 1.2
* Dual 4Kp60 HDMI® display output with HDR support
* 4Kp60 HEVC decoder
* LPDDR4X-4267 SDRAM (2GB, 4GB, 8GB, and 16GB)
* Dual-band 802.11ac Wi-Fi®
* Bluetooth 5.0 / Bluetooth Low Energy (BLE)
* microSD card slot, with support for high-speed SDR104 mode
* 2 × USB 3.0 ports, supporting simultaneous 5Gbps operation
* 2 × USB 2.0 ports
* Gigabit Ethernet, with PoE+ support (requires separate PoE+ HAT)
* 2 × 4-lane MIPI camera/display transceivers
* PCIe 2.0 x1 interface for fast peripherals (requires separate M.2 HAT or other adapter)
* 5V/5A DC power via USB-C, with Power Delivery support
* Raspberry Pi standard 40-pin header
* Real-time clock (RTC), powered from external battery
* Power button

---
## Raspberry Pi 5 product brief
https://datasheets.raspberrypi.com/rpi5/raspberry-pi-5-product-brief.pdf

---
### Raspberry Pi AI Kit and AI HAT+  

* Raspberry Pi AI Kit
  * https://www.raspberrypi.com/products/ai-kit/
  * 13 TOPS Hailo-8L accelerator at USD 70
* Raspberry Pi AI HAT+
  * https://www.raspberrypi.com/news/raspberry-pi-ai-hat/
  * 26 TOPS Hailo-8 accelerator at USD 110

<img src="https://github.com/user-attachments/assets/25582b20-38ae-45b2-b9f5-aa50fd84556a" width=330>
<img src="https://github.com/user-attachments/assets/5a295757-284f-49a3-8c5f-ecd0db0ae2ae" width=350>

---
### Raspberry Pi HAT+ Specification
https://datasheets.raspberrypi.com/hat/hat-plus-specification.pdf

* A guide to designing Hardware-Attached-on-Top of a Raspberry Pi
* HAT+ boards should use 'HAT+' in their name. For example, "Raspberry Pi M.2 HAT+ M Key"
* Unlike the AI Kit, which utilises an M.2 connector, the Hailo accelerator chip is directly integrated onto the main PCB. 

---
<br/>
<img src="https://github.com/user-attachments/assets/949b412f-0974-4877-886e-9408dd305951" width=310>
<img src="https://github.com/user-attachments/assets/c4086ecf-cfaa-4459-9277-6b84574ee0be" width=300>
<br/>
<img src="https://github.com/user-attachments/assets/2eaa6fa0-6189-49a9-8353-0c6133d025e9" width=320>
<img src="https://github.com/user-attachments/assets/76bc28ca-1497-4ca9-911f-ba767c3c0804" width=250>

<br/>
<img src="https://github.com/user-attachments/assets/675ce227-33c5-44fe-9ae3-a4004023f4da" width=350>
<img src="https://github.com/user-attachments/assets/ea4cb516-aef0-4201-92ba-b530099a7593" width=350>


---
## Raspberry Pi 5 System Information
<img src="https://github.com/user-attachments/assets/d693150b-2672-4e36-b95b-ada7ccdfa4e7" width=900>

---
## RPi5 Ubuntu OS and RPI-Connect
 
<img src="https://github.com/user-attachments/assets/7297e230-f672-4157-957c-8e46cd60b69f" width=700>

---
## Raspberry Pi 5
Tech Spec: https://www.raspberrypi.com/products/raspberry-pi-5/
* Broadcom **BCM2712** 2.4GHz quad-core 64-bit **Arm Cortex-A76** CPU, with cryptography extensions, 512KB per-core L2 caches and a 2MB shared L3 cache
* VideoCore VII **GPU**, supporting OpenGL ES 3.1, Vulkan 1.2
* **Dual 4Kp60 HDMI®** display output with HDR support, 4Kp60 HEVC decoder
* LPDDR4X-4267 SDRAM (2GB, 4GB, and **8GB**)
* Dual-band 802.11ac **Wi-Fi®**, Bluetooth 5.0 / Bluetooth Low Energy (BLE)
* microSD card slot, with support for high-speed SDR104 mode
* 2 × **USB 3.0** ports, 2 × USB 2.0 ports
* Gigabit Ethernet, with PoE+ support (requires separate PoE+ HAT)
* 2 × 4-lane **MIPI camera**/display transceivers
* **PCIe 2.0** x1 interface for fast peripherals (requires separate **M.2 HAT** or other adapter)
* 5V/5A DC power via **USB-C**, with Power Delivery support
* Raspberry Pi OS (previously called Raspbian)
* **Raspberry Pi Connect** provides to access your Raspberry Pi from anywhere

---
## RPi5 AI kit (Hailo)

The Raspberry Pi 5 AI Kit bundles the Raspberry Pi **M.2 HAT+** with a **Hailo AI acceleration module**. The kit contains the following:
* Hailo AI module containing a Neural Processing Unit (NPU)
* Raspberry Pi M.2 HAT+, to connect the AI module to your Raspberry Pi 5
* Thermal pad pre-fitted between the module and the M.2 HAT+
* Mounting hardware kit
* 16mm stacking GPIO header

<img src="https://github.com/user-attachments/assets/55673538-d651-4ae7-afd6-07d2f5588eef" width=300>
<img src="https://github.com/user-attachments/assets/e4333ba6-222d-4a44-b167-2a43a7617929" width=450>

---
### Install the dependencies 

Run the following command from a terminal window:
```
$ sudo apt install hailo-all
$ sudo apt remove hailo-all
```
This installs the following dependencies:
* Hailo kernel device driver and firmware
* HailoRT middleware software
* Hailo Tappas core post-processing libraries
* rpicam-apps: Hailo post-processing software demo

---
### Validate device
```
$ hailortcli scan
$ hailortcli fw-control identify
```
The log message will be:
```
Executing on device: 0000:04:00.0
Identifying board
Control Protocol Version: 2
Firmware Version: 4.20.0 (release,app,extended context switch buffer)
Logger Version: 0
Board Name: Hailo-8
Device Architecture: HAILO8L
Serial Number: HLDDLBB243900626
Part Number: HM21LB1C2LAE
Product Name: HAILO-8L AI ACC M.2 B+M KEY MODULE EXT TMP
```

```
$ lspci
0000:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 21)
0000:01:00.0 Co-processor: Hailo Technologies Ltd. Hailo-8 AI Processor (rev 01)
0001:00:00.0 PCI bridge: Broadcom Inc. and subsidiaries BCM2712 PCIe Bridge (rev 21)
0001:01:00.0 Ethernet controller: Raspberry Pi Ltd RP1 PCIe 2.0 South Bridge
```

---
## Hailo RPi5 Examples
https://github.com/hailo-ai/hailo-rpi5-examples

* Clone the repository and navigate to the repository directory:
* Run the following script for quick installation
```
$ git clone https://github.com/hailo-ai/hailo-rpi5-examples.git
$ cd hailo-rpi5-examples
$ ./install.sh
```

---
### Detection Example:
This example demonstrates object detection using the **YOLOv8s** model for Hailo-8L (13 TOPS) and the **YOLOv8m** model for Hailo-8 (26 TOPS) by default. It also supports all models compiled with HailoRT NMS post process. Hailo's Non-Maximum Suppression (NMS) layer is integrated into the HEF file, allowing any detection network compiled with NMS to function with the same codebase.

####  Run the Example:
* Opening a new terminal session and sourced the environment setup script
* Run the detection example using Python script
* To close the application, press Ctrl+C.

```
$ source setup_env.sh
$ python basic_pipelines/detection.py
$ python basic_pipelines/get_usb_camera.py
$ python basic_pipelines/detection.py --input /dev/video0
$ python basic_pipelines/detection.py --help
```

---
<img src="https://github.com/user-attachments/assets/302bc752-8eaf-4949-9307-cd2eee852d6a" width=450>
<img src="https://github.com/user-attachments/assets/949b412f-0974-4877-886e-9408dd305951" width=350>

---
### Pose Estimation Example
This example demonstrates human pose estimation using the yolov8s_pose model for Hailo-8 Lite (H8l) and the yolov8m_pose model for Hailo-8 (H8)

#### To Run the Example:
* Opening a new terminal session andsourced the environment setup script
* Run the example using Python script
* To close the application, press Ctrl+C
* For additional options, execute command with --help option
 
```
$ source setup_env.sh
$ python basic_pipelines/pose_estimation.py
$ python basic_pipelines/get_usb_camera.py
$ python basic_pipelines/pose_estimation.py --input /dev/video0
$ python basic_pipelines/pose_estimation.py --help
```

---
<img src="https://github.com/user-attachments/assets/2f5edc26-8755-4cac-be16-02550d535664" width=450>
<img src="https://github.com/user-attachments/assets/949b412f-0974-4877-886e-9408dd305951" width=350>

---
### Instance Segmentation Example
This example demonstrates instance segmentation using the yolov5n_seg model for Hailo-8 Lite (H8l) and the yolov5m_seg model for Hailo-8 (H8).
* Opening a new terminal session andsourced the environment setup script
* Run the example using Python script
* To close the application, press Ctrl+C
* For additional options, execute command with --help option

```
$ source setup_env.sh
$ python basic_pipelines/instance_segmentation.py
$ python basic_pipelines/get_usb_camera.py
$ python basic_pipelines/instance_segmentation.py --input /dev/video0
$ python basic_pipelines/instance_segmentation.py --help
```

---
<img src="https://github.com/user-attachments/assets/bf88d093-2b67-4215-8b3e-f07afd2d074a" width=450>
<img src="https://github.com/user-attachments/assets/949b412f-0974-4877-886e-9408dd305951" width=350>

---
## Raspberry AI from Zero to Hero

1. Introduction to AI
2. Set up your Raspberry Pi and AI Kit
3. Computer vision projects and practice
4. LLM projects and practice
5. Custom model development and deployment
6. Raspberry Pi and AIoT

<br/>
<img src="https://github.com/user-attachments/assets/3c82a92c-7fa2-4b99-b426-ccc453643f76" width=800>

---
## Reference

---
### Reference: Installation
* Raspberry Pi hardware - Introduction
  * https://www.raspberrypi.com/documentation/computers/raspberry-pi.html#introduction 
* Raspberry Pi 5 uses PCIe hat/dual hat
  * https://wiki.seeedstudio.com/raspberry_pi_5_uses_pcie_hat_dual_hat/
* Raspberry Pi - AI Kit and AI HAT+ software
  * https://www.raspberrypi.com/documentation/computers/ai.html
* Install Hailo Software & Verify Installation
  * https://wiki.seeedstudio.com/clip_application_on_rpi5_with_ai_kit/
* Hailo’s Software Downloads and Documentation
  * https://community.hailo.ai
* HailoRT v4.19.0 - Installing HailoRT on Ubuntu
  * https://hailo.ai/developer-zone/documentation/hailort-v4-19-0/?sp_referrer=install/install.html#installation-on-ubuntu
* HailoRT v4.20.0 documentation
  * https://hailo.ai/developer-zone/documentation/hailort-v4-20-0
* Hailo TAPPAS - Optimized Execution of Video-Processing Pipelines: 
  * https://github.com/hailo-ai/tappas

---
### Reference: Examples
* Hailo Raspberry Pi5 Examples
  * https://github.com/hailo-ai/hailo-rpi5-examples
* Hailo RPi5 Basic Pipelines
  * https://github.com/hailo-ai/hailo-rpi5-examples/blob/main/doc/basic-pipelines.md
* RPI5 + Hailo8 - CLIP Application
  * https://github.com/hailo-ai/hailo-CLIP
* Pose-Based Light Control with Node-Red and Raspberry Pi with AIkit
  * https://wiki.seeedstudio.com/pose_based_light_control_with_nodered_and_rpi_with_aikit/
* Benchmark of Multistream Inference on Raspberrypi 5 with Hailo8
  * https://wiki.seeedstudio.com/benchmark_of_multistream_inference_on_raspberrypi5_with_hailo8
  * https://www.youtube.com/watch?v=CHxg7qWTMYw
* YOLOv8 - Ultralytics
  * https://docs.ultralytics.com/models/yolov8
* Testing Raspberry Pi's AI Kit - 13 TOPS for $70 (2024.07)
  * https://www.jeffgeerling.com/blog/2024/testing-raspberry-pis-ai-kit-13-tops-70)

