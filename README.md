## How To Adapt tree to build ROM

Add this line to the ROM manifest.xml before ```repo sync``` in the hardware/qcom-caf/common line :

```
    <linkfile src="os_pickup_audio-ar.mk" dest="hardware/qcom-caf/sm6225/audio/Android.mk" />
    <linkfile src="os_pickup_qssi.bp" dest="hardware/qcom-caf/sm6225/Android.bp" />
    <linkfile src="os_pickup.mk" dest="hardware/qcom-caf/sm6225/Android.mk" />
```

Add this line to HAL repository line :

```
  <project path="hardware/qcom-caf/sm6225/audio/agm" name="Xiaomi-SD685-Devs/vendor_qcom_opensource_agm" remote="github" revision="lineage-20.0-caf-sm6225" />
  <project path="hardware/qcom-caf/sm6225/audio/pal" name="Xiaomi-SD685-Devs/vendor_qcom_opensource_arpal" remote="github" revision="lineage-20.0-caf-sm6225" />
  <project path="hardware/qcom-caf/sm6225/audio/primary-hal" name="Xiaomi-SD685-Devs/hardware_qcom_audio" remote="github" revision="lineage-20.0-caf-sm6225" />
  <project path="hardware/qcom-caf/sm6225/display" name="Xiaomi-SD685-Devs/hardware_qcom_display" remote="github" revision="lineage-20.0-caf-sm6225" />
  <project path="hardware/qcom-caf/sm6225/media" name="Xiaomi-SD685-Devs/hardware_qcom_media" remote="github" revision="lineage-20.0-caf-sm6225" />
```

After successfully repo sync finished. Then pick this commit to your'e vendor/ROM :
- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/6b63aae0039f065eeacf4f96305c732f67ded67e
- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/03bdcbe88c0cb22148aac8a5699ca4c06fb8a42a
- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/c039930871be5683a968a1be1f46a2524441da69

- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/1472107160bdb423e37670de7edc9f773b88a40b

- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/da8d9686e637528e492620108e3403d285c69adb

- https://github.com/Xiaomi-SD685-Devs/vendor_lineage/commit/5c08577e08053fab5ff37fb14923645ca9909a52

Clone device tree to your initialize repo.
Done! Compile the ROM.

## Notes :
- We have a device with the bengal_515 platform.  It looks the same as bengal 4.19 legacy.