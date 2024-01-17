# yolo_on_RPi
## Development environment
- Raspberry Pi CM4
- Raspberry Pi OS - Bullseye/Bookworm
- [Camera libraries](https://github.com/atsss/opencv_on_RPi)
    - Picamera2
- IMX219
- [boot/config.txt](https://github.com/atsss/RPi_configs/blob/main/bookworm/imx219.txt)

## Docs
- Yolo for Raspberry Pi
> https://docs.ultralytics.com/guides/raspberry-pi/

## How to run script
### Install Necessary Packages
1. Update the Raspberry Pi
```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get autoremove -y
```
2. Install the ultralytics Python package
```
pip3 install ultralytics
```
3. Reboot
```
sudo reboot
```

### Initiate TCP Stream with Libcamera
1. Start the TCP stream
```
libcamera-vid -n -t 0 --width 1280 --height 960 --framerate 1 --inline --listen -o tcp://127.0.0.1:8888
```

### Run script
1. Run `test.py`
```
python3 test.py
```
