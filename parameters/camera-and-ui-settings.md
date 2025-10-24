---
layout: default-layout
title: CameraAndUITemplate - Dynamsoft Batch Barcode Scanner
description: The CameraAndUITemplate of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# Camera and UI Settings

The camera and UI settings are also available under `CameraAndUITemplates`

```json
{
  "CameraAndUITemplates": [
    {
      "Name": "CUT_Default",
      "CameraType": "CMT_DCE_WIDE_ANGLE",
      "ScanUIScenario": "Inventory",
      "ScanRegion":{
          "ScanRegionEnable": 0,
          "ScanRegionLeft": 0,
          "ScanRegionRight": 100,
          "ScanRegionTop": 0,
          "ScanRegionBottom": 100
      },
      "ScanDirection": "SD_LEFT_TO_RIGHT",
      "Resolution": "RESOLUTION_1080P",
      "PanoramaTemplateName": "Panorama"
    }
  ]
}
```

## Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](#name) | The name of the template. |
| [`CameraType`](#cameratype) | Specifies the camera for batch barcode scanning. It can be a AR camera or a physical camera. |
| [`ScanUIScenario`](#scanuiscenario) | Defines the scan UI by the scenario. |
| [`Resolution`](#resolution) | Specifies the resolution of the camera. |
| [`ScanDirection`](#scandirection) | Specifies the scan direction of the camera. It determines how the preview image is displayed. |
| [`ScanRegion`](#scanregion) | Specifies the scan region. It reduces the scan size to improve the speed and the accuracy. |
| [`BatchScanTemplateName`](#batchscantemplatename) | Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name. |

### Name

The name of the template.

### CameraType

Specifies the camera for batch barcode scanning. It can be a AR camera or a physical camera.

- CMT_AR_PLANE_PROJECTION
- CMT_AR_FRAME_TRACE
- CMT_DCE_AUTO
- CMT_DCE_ULTRA_WIDE
- CMT_DCE_WIDE_ANGLE

DCE Camera: Supports auto-switching between Wide-Angle and Ultra-Wide-Angle camera.

### ScanUIScenario

Defines the scan UI by the scenario.

- "Inventory"
- "TargetLookup"

### Resolution

Specifies the resolution of the camera.

- 3840x2160: Read-Rate first.
- 1920x1080: Speed first.

### ScanDirection

Specifies the scan direction. It determines how the preview image is displayed.

Available values:

- "SD_LEFT_TO_RIGHT"
- "SD_RIGHT_TO_LEFT"
- "SD_TOP_TO_BOTTOM"
- "SD_BOTTOM_TO_TOP"

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
