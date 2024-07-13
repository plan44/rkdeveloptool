# rkdeveloptool



rkdeveloptool gives you a simple way to read/write rockusb device.
let's start.

## compile and install on linux

1. install libusb and libudev
    ```
    sudo apt-get install libudev-dev libusb-1.0-0-dev dh-autoreconf
    ```
2. go into root of rkdeveloptool, then:
    ```
    aclocal
    autoreconf -i
    autoheader
    automake --add-missing
    ./configure
    make
    ```

compile error help
if you encounter the error like below:

```
./configure: line 4269: syntax error near unexpected token `LIBUSB1,libusb-1.0'
./configure: line 4269: `PKG_CHECK_MODULES(LIBUSB1,libusb-1.0)'
```

You should install pkg-config libusb-1.0:

```
sudo apt-get install pkg-config libusb-1.0
```


## compile and install on macOS

1. install autotools and libusb
    ```
    brew install libusb
    brew install autoconf
    brew install automake
    ```

2. go into root of rkdeveloptool, then:
    ```
    aclocal
    autoreconf -i
    autoheader
    automake --add-missing
    ./configure
    make
    ```

## rkdeveloptool usage

input `rkdeveloptool -h` to see options

## examples
1. download kernel.img (=flash it to device)

    ```
    sudo ./rkdeveloptool db RKXXLoader.bin    // download usbplug to device
    sudo ./rkdeveloptool wl 0x8000 kernel.img // 0x8000 is base of kernel partition, unit is sector.
    sudo ./rkdeveloptool rd                   // reset device
    ```


