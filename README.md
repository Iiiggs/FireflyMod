# Firefly platform modification

This is the binary release of Firefly platform modification to support Microvision UVC lidar camera.

Instrcutions for applying the platform modification:
1. Download and flash published Firefly Android image:
http://www.t-firefly.com/share/index/listpath/id/a2bdd74136fc8d2bfd68fb956dd6ca2e.html
Firefly-RK3399_Android7.1.1_MP_171209/

2. Download and apply the modification to the device by running the following commands in firefly mod directory:
```
adb root
adb wait-for-device
adb remount
adb wait-for-device
adb push system/lib64/hw/libisp_isi_drv_OV5645.so system/lib64/hw/
adb push system/lib/hw/libisp_isi_drv_OV5645.so system/lib/hw/
adb push system/lib64/hw/libisp_isi_drv_OV13850.so system/lib64/hw/
adb push system/lib/hw/libisp_isi_drv_OV13850.so system/lib/hw/
adb push system/lib64/hw/camera.rk30board.so system/lib64/hw/
adb push system/lib/hw/camera.rk30board.so system/lib/hw/
adb push system/lib/libisp_silicomimageisp_api.so system/lib/
adb push system/lib64/libisp_silicomimageisp_api.so system/lib64/
adb push system/lib/hw/sensors.rk30board.so system/lib/hw/
adb push system/lib64/hw/sensors.rk30board.so system/lib64/hw/
adb push data/camera/media_profiles.xml data/camera/
adb reboot
```