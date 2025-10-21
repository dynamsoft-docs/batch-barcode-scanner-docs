---
layout: default-layout
title: Introduction - Dynamsoft Batch Barcode Scanner
keywords: BBS, introduction
breadcrumbText: Introduction
description: The introduction of DynamsoftBatchBarcodeScanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# How to use - Configure Settings

A customized setting is available after you log in. If needed, you can adjust these settings in the app. By default, the in-app settings are protected. To make changes, please contact Dynamsoft Technical Support to unlock them.

- [!Note]
- A `Restore Default` button is available under the settings page.
- Contact Dynamsoft if you need further customization. 

### Camera Selection

- Type:
  - `AR`: Scan and trace the barcodes with the AR technology. The first choice when scanning large items from a long distance.
  - `DCE`: The first choice when scanning small items from a close distance.
- Resolution:
  - `3840*2160`: 99% choice. Large resolution takes some longer time but make the barcodes earsier to recognize.
  - `1920*1080`: If you are free to close-up to the barcodes in your scenario, this resolution setting might improve the scanning speed.  

#### Barcode Format Settings

Even if a barcode is not required in the output result, it still contributes to the panoramic image stitching. As a result, we have 2 barcode format configurations:

- Decode: Enable the scanner to decode the barcodes but finally they are not included in the output result. 
- Output: The barcode format that you want to include in the output result.

#### Decode Level

Defines how much effort to spend on decoding the barcodes.

#### Barcode Color Options

Defines whether to read barcodes with the original color or the inverted color or both.

#### Duplication Settings

Defines whether there are `duplicated barcodes` in the target area.

- [!Note]
- `duplicated barcodes`: The barcodes with the same format and text.

#### Auto-Stop & Layout

The scanner can stop automatically if one of the following conditions are enabled and met:

- The `layout analysis` confirms that all barcodes are decoded.
- The `MaxBarcodesCount` is reached.
- It has been a long time (counted by the number of frames) since the last new barcode is decoded.

```json
"SectionLayoutOptions": [
    {
        "LayoutAnalysisMode" : "LAM_LINE",
        "MaxBarcodesCount": 18
    },
    {
        "LayoutAnalysisMode" : "LAM_LINE",
        "MaxBarcodesCount": 18
    },
    {
        "LayoutAnalysisMode" : "LAM_LINE",
        "MaxBarcodesCount": 18
    }
]
```

#### How to Use Debug Mode


