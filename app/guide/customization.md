---
layout: default-layout
title: Customization
keywords: Customization
breadcrumbText: Customization
description: This demostrates how to get your scanner customized.
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Get Your Scanner Customized

The scanning experience in **Dynamsoft Batch Barcode Scanner** is fully customizable. Open the settings page, you can configure it in the following aspects:

* Camera
* Scanning
* Barcode Reading

Settings screenshots:

![Settings 1](/assets/images/guide/settings-1.jpg){:width="215"} ![Settings 2](/assets/images/guide/settings-2.jpg){:width="215"}

## Camera

| Settings | Description |
| --------- | ----------- |
| Resolution | The resolution of the camera preview. |
| Camera Type | Available for iOS, where you can select whether to use AR or the default camera with [Dynamsoft Camera Enhancer](https://www.dynamsoft.com/camera-enhancer/overview/) (DCE). Using AR has a smoother tracking experience, but may have trouble scanning close objects or multi-plane objects. It is also recommend to use AR with a device having LiDAR for more accurate tracking.|
| Enable Video Decoding | Enable video decoding to provide live visual feedback. The barcodes decoded from the live video can also be used for the final result. It is enabled by default. Turn off this to save battery. |

## Scanning

| Settings | Description |
| --------- | ----------- |
| Scan Setting Name | The name of the scanning setting, which is used in the JSON template. |
| Scan Region  | Specifies the scan region.  |
| Stitch Level | Specifies how much effort to spend on stitching the images. |
| Auto Stop | Whether to stop scanning automatically when certain conditions are reached, like barcode count. |
| Layout | Specifies what layout analysis to enable. When enabled, it can highlight potential unrecognized barcodes based on layout. For example, a 20x20 grid. It is disabled by default. |


## Barcode Reading

| Settings | Description |
| --------- | ----------- |
| Barcode Setting Name | The name of the barcode reading setting, which is used in the JSON template. |
| Barcode Colour Options | Configure this to read inverted barcodes. |
| Barcode Decode Level  | Preset templates to control how much effort to spend on decoding barcodes.  |
| Barcode Formats | Specifies what formats of barcode to read and output. |
| Has Duplicate Barcodes | If disabled, it only outputs one of the many duplicate barcodes, which is suitable if one object has many barcodes with the same value. It is enabled by default. |
| Min Localized Barcode Confidence | The minimum confidence level of the localized barcode. If the value is lower than 100, it will draw barcodes which haven't been recognized but localized on the result image in red. The default value is 100. |

## Import and Export

You can import and export the settings in JSON. The JSON template has more options and the settings specified with the UI has higher priority.

You can [contact support](mailto:support@dynamsoft.com) to specify the default template for your account.

Read the [parameters](/parameters/index.md) page to learn more about the JSON templates.
