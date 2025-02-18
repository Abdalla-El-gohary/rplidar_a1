# RPLidar A1M8

## Information

The Python3 scripts for [RPLIDAR A1](https://www.slamtec.com/en/Lidar/A1) run on Linux, macOS, and Windows. 
Latest rplidar documentation can be found [here](https://rplidar.readthedocs.io/en/latest/). 
If you prefer C++, please have a look [here](https://github.com/slamtec/rplidar_sdk).

Examples:

- COM3 (_Windows_)
- /dev/ttyUSB0 (_Linux_)
- /dev/tty.usbserial-0001 (_macOS_)

Additional documents are available:

- [A1M8 Datasheet](https://bucket-download.slamtec.com/d1e428e7efbdcd65a8ea111061794fb8d4ccd3a0/LD108_SLAMTEC_rplidar_datasheet_A1M8_v3.0_en.pdf)
- [A1M8 Dev Kit User Manual](https://bucket-download.slamtec.com/269e60a69933dffb1067a2ee3405f2918168064a/LM108_SLAMTEC_rplidarkit_usermanual_A1M8_v2.1_en.pdf)
- [Protocol](https://bucket-download.slamtec.com/f010c72be308cdc618e91746d643278185ed02b2/LR001_SLAMTEC_rplidar_protocol_v2.2_en.pdf)

## Setup

**Clone Repository**

```shell
# clone repository
$ git clone https://github.com/Abdalla-El-gohary/rplidar_a1.git

# change directory
$ cd rp_lidar
```

**Create virtualenv (_for Python 3.x_)**

> The use of virtualenv is not mandatory but recommended.

```shell
# create virtualenv
$ python3 -m venv venv

# activate virtualenv
$ source venv/bin/activate

# install packages
(venv) $ pip install -r requirements.txt 
```

## Execute Python scripts

**Test Lidar Connection**

```shell
# display rplidar connection information
(venv) $ python3 test_lidar.py
```

**Visualize Lidar Data**

```shell
# visualize rplidar data in a plot
(venv) $ python3 test_visualize.py
```

## Error

**General**

[Error] Could not find device: /dev/ttyUSB0...

> Make sure the RPLIDAR is properly connected via USB and visible.

```shell
# list all /dev/tty devices and grep for USB
$ ls -la /dev/tty* | grep -i USB
```

**Linux**

Cannot read from /dev/ttyUSB0...

> Root privilege is needed to access the ttyUSB device under Linux.

```shell
# change permissions
$ sudo chmod 0666 /dev/ttyUSB0
```

**Stop virtualenv**

```shell
# stop virtualenv
(venv) $ deactivate
```

## Directory Structure

```
rplidar_a1/
│   README.md
│   requirements.txt
│   test_lidar.py
│   test_visualize.py
│
└───rp_lidar/
        __init__.py
        rp_lidar.py
```

The `rp_lidar` directory contains the class implementation for handling RPLidar A1M8.

