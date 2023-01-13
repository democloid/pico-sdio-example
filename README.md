# PIO SDIO for Raspberry Pi PICO example

This is an standalone example of the [bench](https://github.com/greiman/SdFat/tree/master/examples/bench) code from [SdFat](https://github.com/greiman/SdFat) using an SDIO PIO implementation from [ZuluSCSI](https://github.com/ZuluSCSI/ZuluSCSI-firmware)

This is WIP as performance has been lower than expected, so checking out what is the issue.

Current numbers with a supposedly good SD Card:

```
FreeStack: 241592
Type is FAT32
Card size: 15.9315 GB (GB = 1E9 bytes)

Manufacturer ID: 0X3
OEM ID: SD
Product: SS16G
Revision: 8.0
Serial number: 0XB4064393
Manufacturing date: 12/2016

FILE_SIZE_MB = 5
BUF_SIZE = 512 bytes
Starting write test, please wait.

write speed and latency
speed,max,min,avg
KB/Sec,usec,usec,usec
454.422,70708,933,1126
454.669,70438,932,1125

Starting read test, please wait.

read speed and latency
speed,max,min,avg
KB/Sec,usec,usec,usec
2162.63,256,234,236
2162.63,254,234,236

Done
```

## Build
```
<BUILD_DIR> $ PICO_SDK_PATH=<PATH_TO_SDK> cmake <PATH_TO_SOURCE>
```

Target code will output bench results via UART and save results in `bench.dat` file on SD card root.
