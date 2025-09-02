# Raspberry Pi5 Demos

The code examples are provided for demo purpose on an “AS IS” basis. No responsibility or liability is accepted or shall be imposed regarding the accuracy, merchantability, completeness or suitability of the code example. 

---
### Demo examples
1. RPI5 CPU
    * IP Camera: Object detection
    * USB camera: Object detection, Pose estimation, Instance segmentation
3. RPI5 CPU + Halio8L (13TOPS)
    * USB camera: Object detection, Pose estimation, Instance segmentation
    * Recorded video: Object detection, Pose estimation, Instance segmentation
5. RPI5 CPU: Whisper
    * Whisper: Recorded audio to text
    * Whisper: Live audio to text
7. RPI5 CPU: Ollama Chatbot
    * Ollama Chatbot: Use text as the prompt input for Chatbot
    * Ollama Chatbot: Use recorded audio as the prompt input for Chatbot

---
### Connect Raspberry Pi 5 device

```
## Setup WIFI connection on Pi deivce
## SSID: DEVLABS, WIFI Password: arm12345
$ sudo nmcli dev wifi connect DEVLABS password arm12345
$ ifconfig
=> 192.168.72.65 
```

```
## Connect Pi deivce use SSH from remote
$ sshpass -p rpi5demo ssh demo@192.168.72.65 -X
```

---
### RPI5 CPU: IP Camera

```
## Use IP Camera as inpout source
## Choose the target (URL) in ./src/yolov8n-ipcam.py
$ cd ~/rpi5cpu
$ make ipcam    # IP camera: Object detection
```

```
## Use usb canera as inpout source
$ cd ~/rpi5cpu
$ make det      # Object detection
$ make pos      # Pose estimation
$ make seg      # Instance segmentation
```

---
### RPI5 CPU + Halio8L (13TOPS)

```
$ cd ~/rpi5hailo/hailo-rpi5-examples
$ source ./setuo_env.sh

## Use recorded videos as inpout source
$ make det       # Object detection
$ mkae pos       # Pose estimation
$ make seg       # Instance segmentation

## Use USB camera as inpout source
$ make det-u     # Object detection
$ make pos-u     # Pose estimation
$ make seg-u     # Instance segmentation
```

---
### RPI5 CPU: Whisper

```
## Connect bluetooth speaker device
$ cd ~/whisper
$ make ble
$ bluetoothctl scan on
## [NEW] Device 64:68:76:1A:84:23 EDIFIER MF200
$ bluetoothctl remove 64:68:76:1A:84:23
$ bluetoothctl connect 64:68:76:1A:84:23
```

```
## Recorded audio to text
$ cd ~/whisper
$ make demo-flac model=small
$ make demo-ch model=small
```

```
## Live audio to text
$ cd ~/whisper
$ make live model=small
$ make live-ch2en model=small
```

---
### RPI5 CPU: Ollama Chatbot

```
## Start Ollama service for Chatbot
$ cd ~/ollama-chat
$ make serve
```

```
## Use text as the prompt input for Chatbot
$ cd ~/ollama-chat
$ make run-chat MM=llama3.2:1b
```

```
## Use recorded audio as the prompt input for Chatbot
$ cd ~/ollama-chat
$ make run-audio MM=llama3.2:1b
```

