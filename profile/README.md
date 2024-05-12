# DSCeltic AOSP Repositories 


## 1. DSIW-10T1 AOSP build
- 소스 다운로드
```
repo init -u git@github.com:DSCelticAOSP/platform_manifest.git
repo sync -j16
repo forall -c git lfs pull

```

-  BSP Config

```
cd longan
./build.sh config


Welcome to mkscript setup progress
All available platform:
   0. android
   1. linux
Choice [linux]: 0  <-- 0 입력<Enter>
All available ic:
   0. t507
Choice [t507]: 0   <-- 0 입력<Enter>
All available board:
   0. celtic_800p_r2
   1. dsceltic_a10_r0
Choice [dsceltic_a10_r0]: 1  <-- 1 입력<Enter>

```

- BSP build

```
./build.sh   <--- BSP full build
./build.sh kernel <--- kernel build
./build.sh clean <--- build clean
```

- Android Config
```
cd android
source build/envsetup.sh
lunch 12


============================================
PLATFORM_VERSION_CODENAME=REL
PLATFORM_VERSION=10
TARGET_PRODUCT=dsceltic_a10_r0
TARGET_BUILD_VARIANT=userdebug
TARGET_BUILD_TYPE=release
TARGET_ARCH=arm
TARGET_ARCH_VARIANT=armv7-a-neon
TARGET_CPU_VARIANT=cortex-a7
HOST_ARCH=x86_64
HOST_2ND_ARCH=x86
HOST_OS=linux
HOST_OS_EXTRA=Linux-5.15.0-101-generic-x86_64-Ubuntu-20.04.6-LTS
HOST_CROSS_OS=windows
HOST_CROSS_ARCH=x86
HOST_CROSS_2ND_ARCH=x86_64
HOST_BUILD_TYPE=release
BUILD_ID=QP1A.191105.004
OUT_DIR=out
============================================

```
- Android Build
```
extract-bsp  <-- kernel등 BSP 이미지 복사
make -j24
```

