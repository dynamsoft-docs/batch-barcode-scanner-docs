---
layout: default-layout
title: CameraAndUITemplate
description: The CameraAndUITemplate of Dynamsoft Batch Barcode Scanner
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
      "BatchScanTemplateName": "BST_Stardard"
    }
  ]
}
```

## Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](#name) | The name of the template. |
| [`CameraType`](#cameratype) | Specifies the camera for batch barcode scanning. It can be a AR camera or a physical camera. (Only valid for iOS) |
| [`Resolution`](#resolution) | Specifies the resolution of the camera. |
| [`ScanRegion`](#scanregion) | Specifies the scan region. It reduces the scan size to improve the speed and the accuracy. |
| [`BatchScanTemplateName`](#batchscantemplatename) | Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name. |

### Name

The name of the template.

### CameraType

Specifies the camera for batch barcode scanning. It can be a AR camera or a physical camera. It is only valid for iOS.

- CMT_AR_PLANE_PROJECTION
- CMT_AR_FRAME_TRACE
- CMT_DCE_AUTO
- CMT_DCE_ULTRA_WIDE
- CMT_DCE_WIDE_ANGLE

DCE Camera: Supports auto-switching between Wide-Angle and Ultra-Wide-Angle camera.

### Resolution

Specifies the resolution of the camera.

- 3840x2160: Read-Rate first.
- 1920x1080: Speed first.

### ScanRegion

Specifies the scan region with a scan region object. It reduces the scan size to improve the speed and the accuracy.

```json
"ScanRegion":
{
   "ScanRegionEnable": 0,
   "ScanRegionLeft": 0,
   "ScanRegionRight": 100,
   "ScanRegionTop": 0,
   "ScanRegionBottom": 100
}
```

### BatchScanTemplateName

Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name.
