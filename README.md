# rtl8733BS_WiFi_linux

## Info / Log

1) Make sure WL_DIS# & BT_DIS# is pulled high
2) Some module or stamp might not include pull-up resistor
3) Read vendor HW datasheet and double check pins requirement

This port version successfully ran on 6.19

```
mmc1: new high speed SDIO card at address 0001
sudo cat /sys/kernel/debug/mmc1/ios
clock:          25000000 Hz
actual clock:   25000000 Hz
vdd:            21 (3.3 ~ 3.4 V)
bus mode:       2 (push-pull)
chip select:    0 (don't care)
power mode:     2 (on)
bus width:      2 (4 bits)
timing spec:    2 (sd high-speed)
signal voltage: 0 (3.30 V)
driver type:    0 (driver type B)

Linux  6.18.0-xilinx-g235bd5e49f53-dirty #13 SMP PREEMPT Thu Nov 12 15:25:37 CST 2026 armv7l GNU/Linux

> sudo insmod 8733bs.ko


[   48.184359] RTW: module init start
[   48.184390] RTW: rtl8733bs v5.15.17-113-g1924716b3.20250521_COEX20241204-390f
[   48.184406] RTW: build time: Nov 12 2026 15:31:25
[   48.184420] RTW: rtl8733bs BT-Coex version = COEX20241204-390f
[   48.184447] RTW: rtw_inetaddr_notifier_register
[   48.184847] RTW: == SDIO Card Info ==
[   48.184866] RTW:   card: 396ed5aa
[   48.184884] RTW:   clock: 25000000 Hz
[   48.184897] RTW:   timing spec: sd high-speed
[   48.184923] RTW:   sd3_bus_mode: FALSE
[   48.184935] RTW:   func num: 1
[   48.184948] RTW:   func1: 538f28ce (*)
[   48.184963] RTW:   max_byte_size: 512
[   48.184975] RTW: ================
[   48.184989] RTW: CHIP TYPE: RTL8733B
[   48.185119] RTW: [HALMAC]139
               HALMAC_MAJOR_VER = 1
               HALMAC_PROTOTYPE_VER = 6
               HALMAC_MINOR_VER = 6
               HALMAC_PATCH_VER = 43
[   48.189660] RTW: Chip Version Info: CHIP_8733B_U4_1T1R_RomVer(3)
[   48.213062] RTW: SetHwReg: bMacPwrCtrlOn=1
[   48.261627] RTW: is_valid_id_status: HALMAC_FEATURE_DUMP_LOGICAL_EFUSE
[   48.261719] RTW: HW EFUSE
[   48.261747] RTW: 0x000: 29 81 80 86  10 00 84 00  B2 0D B5 35  08 94 8A 1B
[   48.261885] RTW: 0x010: FF FF FF FF  FF FF FF FF  FF FF FF FF  FF FF FF FF
[   48.262021] RTW: 0x020: FF FF 04 05  05 05 03 05  04 04 04 05  01 02 02 FD
[   48.262155] RTW: 0x030: FF FF FF FF  FF FF FF FF  FF FF 06 06  06 06 06 06

```

## Vendor Version - 5.15.17-113

## Report Version - 6.12 & 6.19

