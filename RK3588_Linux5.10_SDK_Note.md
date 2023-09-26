# RK3588 Linux SDK Note

---

**Contents**

[TOC]

---
## rk3588_linux5.10_release_v1.3.0_20230920.xml Note

1 **Update Debian**

- Optimize Debian's Cheese app

1) Fixed a loop issue when the Cheese camera was turned on for recording and then turned off again
2) Add H264 encoding support, as Cheese only supports VP8 encoding by default, but many RK chips have    weak or unsupported VP8 encoding So by default, support for H264 encoding is added

- Update Xserver

1) Filtering Mali DDK does not support GBM_FORMAT_R8 error issue
2) Fix the issue of the menu bar sliding and getting stuck on the top left side of the Xfce desktop
3) Fix the issue of abnormal rotation function after opening the anti tearing FlipFB

- Update rkwifibt with new script processing for more complete functionality and compatibility

- Update Chromium x11 version from 91.0.4472.164 to 111.0.5563.147

1) Drop is_official_build=false GN arg for optimization
2) Support HEVC (H265)
3) Enable VEA
4) Support AV1 in V4L2 VDA

2 **Update Buildroot**

- Update Buildroot Launcher and add status bar for configuration

- Weston adds features for closing services and restarting display services

- Increase support for ubifs size setting

- Add the archives directory structure and preset some download packages in advance

- Update lvgl_demo

- Update components (glmark2\glibc\wayland\weston...)

3 **Update Yocto**

- Implement automatic login serial port function

- Implement the automatic mounting function of USB peripherals

- Implement the automatic configuration function of wifibt

4 **Update rockit**

- update rockit version to v1.7.12

5 **Update libmali**

- Update G31/G52/G610 to g13p0-8

1) support the gbm_bo_import GBM_BO_IMPORT_WL_BUFFER
2) add the gbm_bo_create DRM_FORMAT_R8
3) Error in glmark2 terrain scene alpha binding screen
4) Adaptation of gl4es
5) Solving fb leakage:gbm_device_get_fd directly returns fd without executing dup

- Update libmali header file

6 **Update rkbin**

- Update RK3588 BL31 to V1.42

1) Optimize the time of system resume.
2) Support any cpu to do system suspend/resume.
3) Support all pwm int to wakeup when virtual-poweroff.
4) Support L3 partition.
5) Update configuration of ddr vref_inner.
6) Support to config MCU sleep parameter through DTS.
7) Add support to reset vop sub mem pd.

- Update  RK3588 BL32 to V1.14

1) Pseudo random number seed will be set by default.
2) Supports read and write security flag interfaces.
3) Support check ta encryption key is written.
4) Fixed hardware crypto probability crash issue after enabling dynamic memory

7 **Update Kernel**

- enable cluster frame reset for rk3588 vop2

- amend to improve USB compatibility for rk3588

- add rk3588 evb7 v11 dts to support

8 **Update rkaiq/rkisp**

Update RKAIQ version to V5.3.0, RKISP driver version to V2.3.0

- fix drc and hdrmge err for multi sensor
- fix 3dlut for multi sensor
- fix stream init pause state
- fix refer to sram info for multi sensor
- add api get isp work mode for rockit
- remove isp_config_hdrshd
- add lock to save tb info
- fix list buf delete err
- fix get tb info
- add iqtool video for isp21
- fix image effect for frame two-run
- fix underperformance for frame two-run
- support unite mode for isp32
- demo: smartIr: fix compile error
- AF: fix SlowStep is too small
- PDAF: support pd offset in otp
- AE: fix IsReconfig bug caused by f99564a

9 **Update tools**

- Update SD tool to V1.76

1) Fix using empty misc size greater than 64k, SD card upgrade tool may have write errors.

- Update RKDevTool to V3.19
- Update window upgrade_tool to V2.23
- Update Rockchip_HdcpKey_Writer to V1.0.5

10 **Update documents**

- Update the SDK application process and instructions for using the Redmine system
- Update DDR related documents and integrate them into one development document
- Add Common/Secutiry document directory
- Add Rockit English documents
- Add RT performance related testing and performance analysis documents
- Add MCU_RGB and MIPI_DSI2  Display Development Document
- Update AVL/USB/PCIE/MMV/USB/NVM/SPI/PERF/WESTON/and other related development documents
- Update the relevant documents required for RK3588 release

11 **Update device/rockchip*

- Add `generate_logs` command is used to package log information.
- Compilation adds prompt SDK version information
- Default empty misc, go to resize partition in OS
- Support for clean module
- Yocto adds default desktop icon layout (synchronized with buildroot)
- Add some dependency checks and prompts for SDK compilation
- Fix AB partition packaging issue
- Fix issue with aarch64 precompiled tool not being able to use
- Yocto supports 3288w
- Ui partition supports automatic resizing
- Support command editing package file
- The yocto SDK supports automatic mounting of USB drives
- Default installation of rktoolkit for all SDKs
- Generate misc firmware from script at compile time
- Using a new wifibt script
- Added support for 'RK3588 EVB7 V11'  boards

## rk3588_linux5.10_release_v1.2.1_20230720.xml Note

1 **Update Debian**

- Filtering Mali DDK does not support GBM_FORMAT_R8 error issue
- Fix the issue of the menu bar sliding and getting stuck on the top left side of the Xfce desktop
- Fix the issue of abnormal rotation function after sretting FlipFB to always
- Add support for Cheese H264 encoding and default to using H264 encoding
- Update rkaiq to release v5.0x1.3
- Update mpp/gstreamer rockchip

2 **Update Buildroot**

- Update lvgl
- Update weston to suppor some issues
- Update rkaiq to release v5.0x1.3
- Support pre-downloaded archives for download

3 **Update rkbin**

- Update bl31 supports to reset vop sub mem pd
- Update ddr.bin to fix init fail issue that max freq between 1066-1600MHz
- Update ddr.bin to fix the issue painc in ddrbin caused by multiple initialization of DDR

4 **Update Kernel**

- Add vicap compatible with rk3588s2
- update vop to support dual connector split mode
- Update of RK3588J and RK3588M frequency Voltmeter

5 **Update documents and tools**

- Upgrade pin_debug_tool to v1.12
- Upgrade programmer_image_tool to v1.26
- Upgrade SDDiskTool to v1.75
- Upgrade FactoryTool to v1.81
- update RKDevTool to v3.18
- Upgrade programming_image_tool to v1.26
- Upgrade Linux_Upgrade_Tool to v2.22
- Update the relevant documents required for RK3588 release

## rk3588_linux_release_v1.2.0_20230620.xml Note

1 **Update device/rockchip**

- Fix Secureboot

2 **Update Debian**

- Update Blueman to resolve abnormal Bluetooth power management issues after sleep wake-up
- Update alsa to address audio issues after sleep wake-up
- Update rkaiq to v5.0x1.2-rc5
- Update mpp/gstreamer rockchip

3 **Update Buildroot**

- Resolve task - c command line exception issues
- Add Weston alpha channel support
- Update rkaiq to v5.0x1.2-rc5
- Add Gstreamer NV16_10LE40 format support
- Increase the use of domestic kgithub image sources for DL packages

5 **Update Kernel**

- Add rk3588-evb7-v11 board to support
- Update RK817/RK809 driver to address sleep wake-up issues
- Fix low-volt-mem-read-margin
- Fixed the rkvenc1 init frequency
- Assign VOP_ACLK to 750MHZ for rk3588-linux.dtsi
- add camera sensor configuration for rk3588s-evb1-lp4x-v10-linux.dts
- Fixed the init frequency

6 **Update documents and tools**

- Update Rockdev to resolve address resolution exceptions
- Update the relevant documents required for RK3588 release

## rk3588_linux_release_v1.1.1_20230520.xml Note

The main update list is as follows:

1 **Update device/rockchip**

- buildroot/yocto installs Chinese fonts by default
- recovery does not install additional overlay
- Fixed hostname exception after dynamically switching rootfs
- Add dependency check and installation prompt
- Add repair owner permission
- Fix the problem that repeated compilation of yocto post-rootfs does not execute

2 **Update recovery**

- Repair press the recovery button to reset to enter the system, nothing is displayed
- U disk upgrade startup support
- Solve the problem that the first upgrade of the SD card starts abnormally
- Fix userdata partition unmount failure

3 **Update Debian**

- Solve the problem of cheese app recording screen freeze
- Support xfce4 power management configuration
- There are hidden problems in updating system permissions
- Update rkwifibt to solve problems related to switch or sleep wake-up
- Update adb to add some feature support
- Update mpp and gstreamer-rockchip
- Update rockchip-test to V2.1
- Solve the abnormal double-click problem of Debian desktop icons

4 **Update Buildroot**

- Optimize rknpu2 compilation configuration
- Add support for setting the location of Gstreamer glimagesink/xvimagesink plugin
- Fixed crash when Weston destroys dmabuf
- Add power/dictionary pen/sweeping machine and other product configurations
- Added support for external toolchains
- Add support for GCC8.X
- Fix the problem that the video source size may overflow after Gstreamer kmssink scaling
- Add Chromium 111.0.5563.147, support video H265 decoding
- Update Frecon, solve zoom and switch VT1 support
- Update rockit to v1.7.4
- Add support for lvgl demo

5 **Update rkbin**

- Adjust the pvtpll configuration of cpu/gpu/npu according to the correlation chip test results
- Increase chip version judgment
- Update RK3588 lp5 mr configuration \ improve the stability of hdmirx related functions \ add ddr spread spectrum mode / optimize boot time.

6 **Update Kernel**

- Solve the problem that the rk3588 hdmiphy lane skew is too large
- Update rknpu driver to V0.8.8
- Solve isp switch abnormal error
- System panic after opening KASAN with Logo buf non-PAGE aligned

7 **Update Uboot**

- fastboot: Burning more than 4G firmware causes the system to fail to start
- System panic after opening KASAN with Logo buf non-PAGE aligned

## rk3588_linux_release_v1.1.0_20230420.xml Note

The main update list is as follows:

### SDK update main core component versions

- Kernel upgrade from 5.10.110 to 5.10.160
- Update Debian to 11.6
- Update Yocto to 4.0.9
- Update Buildroot to November 2021
- Weston updated to 11.0.1
- Gstreamer updated to 1.22

### SDK optimization and adjustment

- Reconstruct SDK configuration compilation mechanism
- Adjusting the compilation mechanism of the wifibt module
- Import a new version of Camera rkaiq to optimize its functionality and performance

### SDK New features

- Added Linux headers support, making it convenient for third-party applications without the need for kernel compilation and debugging
- Added yocto support for x11
- Added gst mpp support for av1
- Added gst mpp support for afbc encoding
- New support for OTA differential function
- New UDL support
- Added adaptation support for libcamera
- New rk3588 venc support for dynamic voltage regulation to improve stability

### SDK main fix issues

- Fix ubi format partition packaging and mounting issues
- Fix recovery mount partition exception
- Fix [webgl](https://webglsamples.org/aquarium/aquarium.html) Flash screen issue
- Fixed the issue of resetting the time to 0 after standby wake-up
- Fix fiq debugger driver, serial port RX interference, resulting in system stuck
- Fixed a low probability of error after starting KASAN: KASAN: use after free in rga_ job_ next
- Support for addressing Weston touch related configurations
- Solve HDMI/MIPI plug and display issues
- Solve the problem of PDM recording channel confusion
- Resolve the issue of playback noise caused by RK809 · RK817-pdm recording
- Solving the unexpected startup of PMU MCU during sleep of rk3588 may cause ddr data to be overwritten
- Improve the stability of RK3588 DDR

## rk3588_linux_release_v1.0.3_20220920.xml Note

- Upgrade bifrost DDK from g12p0-01eac0 to g13p0-01eac0
- Upgrade NPU verison to V1.4.0
- Refactor rkwifibt code
- Update Weston to support to set cursor size and launchers
- Add pm-utils for PowerManager
- Use chromium R88 by default
- Update some packages to buildroot upstream version
- Update Linux_Upgrade_Tool to v2.17
- Update UEFI
- Update audio/crypto/sata/PCIe/usb/rockit/gstreamer/rga... docs

## rk3588_linux_release_v1.0.2_20220820.xml Note

- Remove libglCompositor/avb repositories
- Add rockit/librkcrypto repositories
- Fix a few download/extract errors
- Upgrade Weston version to 10.0.1 and improve its stability
- Add support for buildroot X11 related functions
- Add support for Linux enlightment Wayland desktop
- Upgrade kernel to 5.10.110
- Update the chromium browser version of Debian to R101
- Update Linux_Upgrade_Tool, RKDevTool and SDDiskTool
- Improve HDMI compatibility and HDMI-IN stability
- Upgrade GStreamer of builderroot to 1.20.3 to improve audio and video compatibility
- Add gamma support for xserver and fix the problem of multi touch
- Update loader to improve chip stability
- Update NPU and fix memory leakage
- Update MPP to improve compatibility
- Update docs

## rk3588_linux_release_v1.0.1_20220620.xml Note

- Fixes Secureboot function issue
- Fixes SD boot and upgrade issue
- Update docs include secureboot,pinctrl,display,AVl and so on
- Update kernel to fix some issues
- Add RK3588M Socs to support
- Add RK3588 evb7 to support single pmic hardware design

## rk3588_linux_release_v1.0.0_20220520.xml Note

- Update all the projects with lastest
- Update kernel/uboot/rkbin to improve the chips stability
- Update documents and tools to make the SDK more better
- Fixes some bugs on buildroot weston10
- Fixes the multivideo hang issue
- Fixes the suspend to resume issues
- Fixes the kmssink/rksimageink plugins on gstreamer
- Fixes the bluthooth on/off during the suspend to resume
- Fixes the pcie-ssd performance with write/read
- Fixes the userdata address in parameter.txt
- Fixes the cheese app on debian
- Fixes the permission with pulseaudio
- Improve the video decode performance with mpp fast mode
- Improve the Audio/Video compatibility
- Upgrade RKNN SDK to v1.3.0
- Upgrade RKAIQ from v3.0x8.7 to v3.0x8.8
- Upgrade Debian version from 11.2 to 11.3
- Reduce the debian rootfs size from 5.5G to 3.2G

## rk3588_linux_beta_v0.1.1_20220421.xml Note

- Support midi and fluidsynth format for gstreamer
- Convert github git:// to https:/ on buildroot
- Support mpp fast-mode property

## rk3588_linux_beta_v0.1.0_20220414.xml Note

```
- The first beta version
```

## rk3588_linux_alpha_v0.0.1_20220115.xml Note

```
- The first alpha version
```
