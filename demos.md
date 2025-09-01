# Raspberry Demos


---
### RPI5: IPCam 

```
sshpass -p rpi5demo ssh demo@192.168.52.65 -X
cd ~/rpi5cpu
make ipcam
make det      # Object detection
make pos      # Pose estimation
make seg      # Instance segmentation
```

---
### RPI5 + Halio8L (13TOPS)

````
sshpass -p rpi5demo ssh demo@192.168.52.65 -X
cd ~/rpi5hailo/hailo-rpi5-examples
source ./setuo_env.sh
### Use recrded videos as inpout source
make det       # Object detection
mkae pos       # Pose estimation
make seg       # Instance segmentation
### Use usb canera as inpout source
make det-u     # Object detection
make pos-u     # Pose estimation
make seg-u     # Instance segmentation
```
