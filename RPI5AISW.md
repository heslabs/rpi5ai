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

* A Raspberry Pi AI HAT+ or AI HAT+ 2 (recommended), both of which have an on-board Hailo module.  
* A Raspberry Pi AI Kit, which includes an M.2 HAT+ with a Hailo-8L AI accelerator pre-installed.  

---
## Software prerequisites
Before running vision AI models or GenAI models on your Raspberry Pi 5, you must configure the required software. Broadly, this consists of the following tasks, performed in order:

1. Enable PCIe Gen 3.0 (AI Kit only). Manually configure the PCIe interface to allow the Hailo NPU to communicate at full speed. This is only necessary for the AI Kit.
2. Update Raspberry Pi OS. Ensure that your Raspberry Pi OS packages are fully up to date.
3. Install required dependencies. Install the necessary software dependencies that allow the operating system (OS) and applications to detect, communicate with, and run AI models on the Hailo NPU.
4. Reboot and verify. Verify that your AI hardware is correctly detected and ready to use.

---
## Run vision AI models on Raspberry Pi 5

### Object detection
The following rpicam-apps demos perform object detection using rpicam-hello with different YOLO models. Each demo draws bounding boxes around detected objects and supports optional flags to modify the output, such as -n to turn off the viewfinder and -v 2 to display textural output only.

Different demos have different tradeoffs in speed and accuracy. Run the following commands to try each of the demos on your Raspberry Pi 5:

<img width="900" height="350" alt="image" src="https://github.com/user-attachments/assets/b186e250-98d5-4586-8b93-bfc9033e2391" />

---
## Run LLMs on Raspberry Pi 5 (AI HAT+ 2 only)
https://www.raspberrypi.com/documentation/computers/ai.html#step1-llm

This section provides instructions for setting up the Hailo 10 NPU on your AI HAT+ 2 with a Raspberry Pi 5 so that you can locally run Large Language Models (LLM). With the following setup, you can access LLMs through:

* POST requests (API calls), where you directly send queries to the hailo-ollama server.
* The Web UI frontend, where you use a browser-based chat-like interface.


### AI model layer
The Hailo Gen-AI Model Zoo contains the pre-trained LLMs suitable for running on Hailo-10H. These models are installed as part of Step 1. Install the Hailo Ollama server. These models are then loaded by the runtime and run by the AI accelerator.

### Backend layer
LLMs are loaded and run by the Hailo Ollama server. This backend layer:

* Loads LLMs from the Hailo Gen-AI Model Zoo.
* Manages inference on the Hailo-10H NPU.
* Exposes a REST API for sending requests (submitting prompts) to the NPU and returning AI inference results (receiving responses).

The Hailo Ollama server is installed as part of Step 2. Start the Hailo Ollama server and run LLMs.

---
### Step 1. Install the Hailo Ollama server
https://www.raspberrypi.com/documentation/computers/ai.html#step1-llm

---
### Step 2. Start the Hailo Ollama server and run LLMs
https://www.raspberrypi.com/documentation/computers/ai.html#step2-llm
