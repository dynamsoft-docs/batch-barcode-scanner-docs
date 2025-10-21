---
layout: default-layout
title: CaptureVisionTemplate - Dynamsoft Batch Barcode Scanner
description: The CaptureVisionTemplate of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# BatchBarcodeScanner Parameters

## BatchScanTemplates Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](batch-scan-settings.md#name) | The name of the template. Must be unique. |
| [`CaptureVisionTemplateName`](batch-scan-settings.md#capturevisiontemplatename) | Specifies a name of the `CaptureVisionTemplate`. A `CaptureVisionTemplate` defines how to decode the barcodes. |
| [`BarcodeFormatIds`](batch-scan-settings.md#barcodeformatids) | Defines which formats are output in the final result. |
| [`ResultOutputSettings`](batch-scan-settings.md#resultoutputsettings) | Result output settings. |
| [`SectionLayoutOptions`](batch-scan-settings.md#sectionlayoutoptions) | Defines the layout sections with their layout analysis mode and maximum number of barcodes. |
| [`AutoStopOption`](batch-scan-settings.md#autostopoption) | Definds whether to stop scanning automatically and when to auto-stop. |
| [`ARCorrectionLevel`](batch-scan-settings.md#arcorrectionlevel) | A higher level means the algorithm will spend more efforts on correcting the AR data. |
| [`DuplicationCorrectionOption`](batch-scan-settings.md#duplicationcorrectionoption) | Determines how the algorithm deals with the duplicated barcodes. |
| [`EnableOutputFrameMappedResult`](batch-scan-settings.md#enableoutputframemappedresult) | Whether to map the result coordinates from panoramic image to the video frame. |
| [`EnableOutputPreviewPanorama`](batch-scan-settings.md#enableoutputpreviewpanorama) | Whether to enable result preview when scanning. |
| [`EnableOutputResultImage`](batch-scan-settings.md#enableoutputresultimage) | Whether to save image data and generate panoramic image in the final result. |
| [`MaxOverlappingFrames`](batch-scan-settings.md#maxoverlappingframes) | The maximum number of overlapping frames of TTLO mode. |
| [`MinLocalizedBarcodeConfidence`](batch-scan-settings.md#minlocalizedbarcodeconfidence) | The minimum confidence level of the localized barcodes. |
| [`PanoramicImageScalePercent`](batch-scan-settings.md#panoramicimagescalepercent) | Determines the scale down rate of the panoramic image. Measured by percentage. |
| [`PerspectiveLevel`](batch-scan-settings.md#perspectivelevel) | Determines how much efforts to spend on correcting the perspective. |
| [`PreviewImageOption`](batch-scan-settings.md#previewimageoption) | Defines how the preview image is output. |
| [`StitchLevel`](batch-scan-settings.md#stitchlevel) | Determines the how much effort to spend on stitching the video frames. |
| [`StitchMode`](batch-scan-settings.md#stitchmode) | Determines the stitching mode. |
| [`UniqueBarcodeFormatIds`](batch-scan-settings.md#uniquebarcodeformatids) | If there exist duplicated barcodes, this option will be used to determine which barcodes are unique. |

## CameraAndUITemplates Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](camera-and-ui-settings.md#name) | The name of the template. |
| [`CameraType`](camera-and-ui-settings.md#cameratype) | Specifies the camera for batch barcode scanning. It can be a AR camera or a physical camera. |
| [`ScanUIScenario`](camera-and-ui-settings.md#scanuiscenario) | Defines the scan UI by the scenario. |
| [`Resolution`](camera-and-ui-settings.md#resolution) | Specifies the resolution of the camera. |
| [`ScanDirection`](camera-and-ui-settings.md#scandirection) | Specifies the scan direction of the camera. It determines how the preview image is displayed. |
| [`ScanRegion`](camera-and-ui-settings.md#scanregion) | Specifies the scan region. It reduces the scan size to improve the speed and the accuracy. |
| [`BatchScanTemplateName`](camera-and-ui-settings.md#batchscantemplatename) | Specifies the `BatchScanTemplate` object required by this template for batch scanning with its name. |

## CaptureVisionTemplates

View in [Dynamsoft Barcode Reader docs](https://www.dynamsoft.com/barcode-reader/docs/core/parameters/structure-and-interfaces-of-parameters.html){:target="_blank"}
