---
layout: default-layout
title: BatchScanTemplate - Dynamsoft Batch Barcode Scanner
description: The BatchScanTemplate of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# Batch Scan Settings

```json
{
  "BatchScanTemplates": [
    {
      "Name": "BST_Default",
      "CaptureVisionTemplateName": "CVT_Default",
      "BarcodeFormatIds": [
        "BF_ALL"
      ],
      "BarcodeTextRegExPattern": "",
      "ResultOutputSettings": 
      {
        "LandmarkHighlightOptions": 
        [
          {
            "Status": "RecognizedUnique",
            "HighlightColor": "green"
          },
          {
            "Status": "RecognizedDuplicate",
            "HighlightColor": "red"
          },
          {
            "Status": "RecognizedNonTarget",
            "HighlightColor": "orange",
          },
          {
            "Status": null,
            "HighlightColor": "",
            "LandmarkFilterConditionNames": ["1"]
          }
        ],
        "LandmarkFilterConditions":
        [
          {
            "Name": "1",
            "BarcodeFormatIds": ["BF_DATAMATRIX"],
            "BarcodeTextRegExPattern": ""
          }
        ],
        "CSVOption": {
          "IncludeTitles": ["INDEX", "BARCODE_TEXT", "BARCODE_FORMAT", "STATUS", "LOCATION"],
        }
      },
      "ARCorrectionLevel": 4,
      "AutoStopOption": {
        "AutoStopMode": null,
        "CheckFramesCount": 8
      },
      "PanoramicImageScalePercent": 0,
      "EnableOutputFrameMappedResult": 1,
      "EnableOutputPreviewPanorama": 1,
      "EnableOutputResultImage": 1,
      "MaxOverlappingFrames": -1,
      "DuplicationCorrectionOption": {
        "DuplicateBarcodeInterval": 4,
        "HasDuplicateBarcodes": 1
      },
      "SectionLayoutOptions": [
        {
          "LayoutAnalysisMode" : "",
          "MaxBarcodesCount": 100
        }
      ],
      "MinLocalizedBarcodeConfidence": 100,
      "OutputLandmarkTypes": [
        "LT_BARCODE"
      ],
      "PerspectiveLevel": 5,
      "PreviewImageOption": {
        "MaxVisibleLength": 0,
        "ScaleRatio": 20
      },
      "StitchLevel": 0,
      "StitchMode": 0,
      "ThreadManagementMode": 1,
      "UniqueBarcodeFormatIds": null
    }
  ]
}
```

## Parameters

| Parameter | Description |
| --------- | ----------- |
| [`Name`](#name) | The name of the template. Must be unique. |
| [`CaptureVisionTemplateName`](#capturevisiontemplatename) | Specifies a name of the `CaptureVisionTemplate`. A `CaptureVisionTemplate` defines how to decode the barcodes. |
| [`BarcodeFormatIds`](#barcodeformatids) | Defines which formats are output in the final result. |
| [`BarcodeTextRegExPattern`](#barcodetextregexpattern) | The regular expression pattern used to filter the barcodes. |
| [`ResultOutputSettings`](#resultoutputsettings) | Result output settings. |
| [`SectionLayoutOptions`](#sectionlayoutoptions) | Defines the layout sections with their layout analysis mode and maximum number of barcodes. |
| [`AutoStopOption`](#autostopoption) | Definds whether to stop scanning automatically and when to auto-stop. |
| [`ARCorrectionLevel`](#arcorrectionlevel) | A higher level means the algorithm will spend more efforts on correcting the AR data. |
| [`DuplicationCorrectionOption`](#duplicationcorrectionoption) | Determines how the algorithm deals with the duplicated barcodes. |
| [`EnableOutputFrameMappedResult`](#enableoutputframemappedresult) | Whether to map the result coordinates from panoramic image to the video frame. |
| [`EnableOutputPreviewPanorama`](#enableoutputpreviewpanorama) | Whether to enable result preview when scanning. |
| [`EnableOutputResultImage`](#enableoutputresultimage) | Whether to save image data and generate panoramic image in the final result. |
| [`MaxOverlappingFrames`](#maxoverlappingframes) | The maximum number of overlapping frames of TTLO mode. |
| [`MinLocalizedBarcodeConfidence`](#minlocalizedbarcodeconfidence) | The minimum confidence level of the localized barcodes. |
| [`PanoramicImageScalePercent`](#panoramicimagescalepercent) | Determines the scale down rate of the panoramic image. Measured by percentage. |
| [`PerspectiveLevel`](#perspectivelevel) | Determines how much efforts to spend on correcting the perspective. |
| [`PreviewImageOption`](#previewimageoption) | Defines how the preview image is output. |
| [`StitchLevel`](#stitchlevel) | Determines the how much effort to spend on stitching the video frames. |
| [`StitchMode`](#stitchmode) | Determines the stitching mode. |
| [`UniqueBarcodeFormatIds`](#uniquebarcodeformatids) | If there exist duplicated barcodes, this option will be used to determine which barcodes are unique. |

### Name

The name of the template. Must be unique.

### CaptureVisionTemplateName

Specifies a name of the `CaptureVisionTemplate`. A `CaptureVisionTemplate` defines how to decode the barcodes.

### BarcodeFormatIds

Defines which formats are output in the final result. If the format of the recognized barcodes don't match this pattern, their status will be set to "RecognizedNonTarget".

**Type**

String[]

**Range**

Each element of the array should be one of the enum BarcodeFormat.

**Default Value**

"BF_ALL"

### BarcodeTextRegExPattern

The regular expression pattern used to filter the barcodes. If the text of the recognized barcodes don't match this pattern, their status will be set to "RecognizedNonTarget".

### ResultOutputSettings

Result output settings. It defines how the CSV files and panoramic images are output.

#### CSVOption

Defines what fields should be included when generating the CSV file.

Supported fields:

- "INDEX"
- "BARCODE_TEXT"
- "BARCODE_FORMAT"
- "STATUS"
- "LOCATION"
- "ROW_NUMBER"
- "COLLUMN_NUMBER"
- "CONFIDENCE"
- "TIME_STAMP"
- "COUNT"

**Default Value**

```json
"CSVOption": {
  "IncludeTitles": ["INDEX", "BARCODE_TEXT", "BARCODE_FORMAT", "STATUS", "LOCATION"],
}
```

#### LandmarkHighlightOptions

Defines the color of the barcodes with the specified status or filter conditions.

- The color defined by the `LandmarkFilterCondition` is prioritized.
- If a barcode matches more than one `LandmarkFilterCondition`, the color of the first matched condition is used.

```json
"LandmarkHighlightOptions": 
[
  {
    "Status": "RecognizedUnique",
    "HighlightColor": "green"
  },
  {
    "Status": "RecognizedDuplicate",
    "HighlightColor": "red"
  },
  {
    "Status": "LocatedByBarcodeReader",
    "HighlightColor": ""
  },
  {
    "Status": "LocatedByLayout",
    "HighlightColor": ""
  },
  {
    "Status": "RecognizedNonTarget",
    "HighlightColor": "orange",
  },
  {
    "Status": null,
    "HighlightColor": "",
    "LandmarkFilterConditionNames": ["1","2"]
  },
  {
    "Status": null,
    "HighlightColor": "",
    "LandmarkFilterConditionNames": ["3"]
  }
],
```

#### LandmarkFilterConditions

```json
"LandmarkFilterConditions":
[
  {
    "Name": "1",
    "BarcodeFormatIds": ["BF_DATAMATRIX"],
    "BarcodeTextRegExPattern": ""
  },
  {
    "Name": "2",
    "BarcodeFormatIds": ["BF_CODE_128"],
    "BarcodeTextRegExPattern": ""
  },
  {
    "Name": "3",
    "BarcodeFormatIds": ["BF_CODE_128"],
    "BarcodeTextRegExPattern": ""
  }
],
```

### SectionLayoutOptions

Defines the layout sections with their layout analysis mode and maximum number of barcodes.

**Type**

Array of SectionLayout objects.

**Default Value**

null

For example:

```json
"SectionLayoutOptions":
[
    {
        "LayoutAnalysisMode" : "LAM_MATRIX",
        "MaxBarcodeCount": 20
    },
    {
        "LayoutAnalysisMode" : "LAM_LINE",
        "MaxBarcodeCount": 16
    }
]
```

#### LayoutAnalysisMode

Specifies the layout analysis mode that applies to the section.

**Type**

String

**Range**

- "LAM_SKIP"
- "LAM_AUTO"
- "LAM_LINE"
- "LAM_MATRIX"

#### MaxBarcodeCount

The maximum number of barcodes in a section.

**Type**

int

**Range**

[0,0x7fffffff]

0 means unlimited.

**Default Value**

0

### AutoStopOption

Definds whether to stop scanning automatically and when to auto-stop.

#### AutoStopMode

The mode of auto-stop. You can specify multiple modes. If you do so, when one of the modes is met, the scanning will be stopped.

**Type**

String

**Range**

- "ASM_OFF"
- "ASM_LAYOUT_ANALYSIS_APPROVED"
- "ASM_MAX_BARCODES_COUNT_REACHED"
- "ASM_NO_MORE_RESULTS"

**Default Value**

"ASM_OFF"

#### CheckFramesCount": 8

The number of frames to check for auto-stop when the mode `ASM_MAX_BARCODES_COUNT_REACHED` is specified.

**Type**

int

**Range**

[0,999]

**Default Value**

8

### ARCorrectionLevel

A higher level means the algorithm will spend more efforts on correcting the AR data.

**Type**

int

**Range**

[0,9]

**Default Value**

4

### DuplicationCorrectionOption

Determines how the algorithm deals with the duplicated barcodes.

#### DuplicateBarcodeInterval

The distance between two duplicated barcodes. Measured in barcode size.

#### HasDuplicateBarcodes

Whether there exist duplicated barcodes. 1 yes, 0 no.

**Type**

int

**Range**

0 or 1

**Default Value**

0

### EnableOutputFrameMappedResult

Whether to map the result coordinates from panoramic image to the video frame.

**Type**

int

**Range**

[0,1]

**Default Value**

1

### EnableOutputPreviewPanorama

Whether to enable result preview when scanning.

**Type**

int

**Range**

[0,1]

**Default Value**

1

### EnableOutputResultImage

Whether to save image data and generate panoramic image in the final result.

**Type**

int

**Range**

[0,1]

**Default Value**

1

### MaxOverlappingFrames

The maximum number of overlapping frames of TTLO mode.

**Type**

int

**Range**

[0, 0x7fffffff]

**Default Value**

1

### Name

### MinLocalizedBarcodeConfidence

The minimum confidence level of the localized barcodes.

**Type**

int

**Range**

[0,100]

**Default Value**

100

<!-- 
### OutputLandmarkType

目前是只支持Barcode -->

### PanoramicImageScalePercent

Determines the scale down rate of the panoramic image. Measured by percentage.

**Type**

int

**Range**

[0,100]

> - 0 means auto.
> - 100 means original size.

**Default Value**

0

### PerspectiveLevel

Determines how much efforts to spend on correcting the perspective.

**Type**

int

**Range**

[0,9]

0: Not perspective
5: Normaly perspective
9: Seriously perspective

**Default Value**

5

### PreviewImageOption

Size of preview image.

#### MaxVisibleLength

The maximum visible length of the preview image.

**Type**

int

Range

**Default Value**

0

#### ScaleRatio

The scale down ratio of the preview image (comparing with the size of the video frame).

**Type**

int

**Range**

[0,100]

**Default Value**

20

### StitchLevel

Determines the how much effort to spend on stitching the video frames.

**Type**

int

**Range**

[0,9]

**Default Value**

0

### StitchMode

Determines the stitching mode.

0：Panorama
1：To-the-Start overlap
2：To-the-Latest overlap

**Type**

int

**Range**

- "STM_PANORAMA"
- "STM_TTSO"
- "STM_TTLO"

**Default Value**

"STM_PANORAMA"

<!-- 
### ThreadMode

Determines how the program allocate the thread. 0 is required for web platform. -->

### UniqueBarcodeFormatIds

If there exist duplicated barcodes, this option will be used to determine which barcode Formats are unique.

**Type**

String[]

**Range**

Each element of the array should be one of the enum BarcodeFormat.

**Default Value**

null

```json
{
  "BatchScanTemplates": [
    {
      "ARErrorLevel": 4,
      "AutoStopOption": {
        "AutoStopMode": null,
        "CheckFramesCount": 8
      },
      "BarcodeFormatIds": [
        "BF_ALL"
      ],
      "CanvasImageScalePercent": 0,
      "CaptureVisionTemplateName": "CVT_Default",
      "EnableOutputFrameMappedResult": 1,
      "EnableOutputPreviewPanorama": 1,
      "EnableOutputResultImage": 1,
      "InvalidWorldBarContinueNoDecodedFrameNum": -1,
      "LandmarkDuplicateOption": {
        "DuplicateBarcodeInterval": 4,
        "HasDuplicateBarcodes": 1
      },
      "LayoutSections": null,
      "Name": "BST_Default",
      "OutputFailedBarcodeMinScore": 100,
      "OutputLandmarkType": [
        "LT_BARCODE"
      ],
      "PerspectiveLevel": 5,
      "PreviewImageSize": {
        "MaxSideLength": 0,
        "ScaleRatio": 20
      },
      "StitchLevel": 0,
      "StitchMode": 0,
      "ThreadMode": 1,
      "UniqueBarcodeFormatIds": null
    }
  ]
}
```
