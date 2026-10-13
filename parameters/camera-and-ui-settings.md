---
layout: default-layout
title: Camera and UI Settings
description: The camera and UI settings of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# Camera and UI Settings

The camera and UI settings are available under `CameraAndUITemplates`.

```json
{
  "CameraAndUITemplates": [
    {
      "Name": "CUT_Default",
      "CameraType": "CMT_DCE_WIDE_ANGLE",
      "ScanRegion":{
          "ScanRegionEnable": 0,
          "ScanRegionLeft": 0,
          "ScanRegionRight": 100,
          "ScanRegionTop": 0,
          "ScanRegionBottom": 100
      },
      "Resolution": "RESOLUTION_1080P",
      "BatchScanTemplateName": "BST_Default"
    }
  ]
}
```

## Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](#name) | The name of the template. |
| [`CameraType`](#cameratype) | Specifies the camera for batch barcode scanning. (Only valid for iOS) |
| [`Resolution`](#resolution) | Specifies the resolution of the camera. |
| [`ScanRegion`](#scanregion) | Specifies the scan region. It reduces the scan size to improve the speed and the accuracy. |
| [`BatchScanTemplateName`](#batchscantemplatename) | Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name. |
| [`EnablePhotoModeVideoDecode`](#enablephotomodevideodecode) | Specifies whether to enable barcode reading via live camera frames. |
| [`ModeSelectionComponent`](#modeselectioncomponent) | Configures the mode selection component. |


### Name

The name of the template.

### CameraType

Specifies the camera for batch barcode scanning. It is only valid for iOS.

- `CMT_DCE_AUTO`
- `CMT_DCE_ULTRA_WIDE`
- `CMT_DCE_WIDE_ANGLE`

### Resolution

Specifies the resolution of the camera.

- `RESOLUTION_4K`: Use 4K resolution. Read-Rate first.
- `RESOLUTION_1080P`: USe 1080P resolution. Speed first.

### ScanRegion

Specifies the scan region with a scan region object. It reduces the scan size to improve the speed and the accuracy.

```json
{
    "ScanRegion": {
        "ScanRegionEnable": 0,
        "ScanRegionLeft": 0,
        "ScanRegionRight": 100,
        "ScanRegionTop": 0,
        "ScanRegionBottom": 100
    }
}
```

* `ScanRegionEnable`: 0 to disable and 1 to enable.
* `ScanRegionLeft`: left measured in percentage.
* `ScanRegionRight`: right measured in percentage.
* `ScanRegionTop`: top measured in percentage.
* `ScanRegionBottom`: bottom measured in percentage.

### BatchScanTemplateName

Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name.

### EnablePhotoModeVideoDecode

Specifies whether to enable barcode reading via live camera frames. Disable it to save battery.

Note: Batch Batch Scanner uses barcode reading via photo by default. If you disable this live decoding option, you can still continuously read barcodes by taking photos, but live tracking and feedbacks will not be available.

### ModeSelectionComponent

Configures the mode selection component.

```json
{
    "ModeSelectionComponent":{
        "Display" : false,
        "Options" : ["TTSO"]
    }
}
```

Supported options:

* `TTLO`: FOV mode (To the latest overlap).
* `TTSO`: Snap and Scan mode (To the start overlap).
* `Panorama`: Panorama mode.
