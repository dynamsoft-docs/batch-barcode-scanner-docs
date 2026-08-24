---
layout: default-layout
title: Capture Vision Settings
description: The Capture Vision settings of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: false
---

# Capture Vision Settings

The barcode reading process can be controlled via the Capture Vision settings.

You can find more details on the capture vision doc site: <https://www.dynamsoft.com/barcode-reader/docs/core/parameters/structure-and-interfaces-of-parameters.html>.

Here is a sample of the JSON template.

```json
{
  "CaptureVisionTemplates": [
    {
      "Name": "CVT_Default",
      "OutputOriginalImage": 1,
      "ImageROIProcessingNameArray": [
        "TA_0"
      ],
      "Timeout": 3000,
      "MaxParallelTasks": 0
    }
  ],
  "TargetROIDefOptions": [
    {
      "Name": "TA_0",
      "TaskSettingNameArray": [ "BR_0" ]
    }
  ],
  "BarcodeReaderTaskSettingOptions": [
    {
      "Name": "BR_0",
      "ExpectedBarcodesCount": 9999,
      "MaxThreadsInOneTask": 1,
      "BarcodeFormatIds": [
        "BF_DATAMATRIX",
        "BF_QR_CODE"
      ],
      "SectionArray": [
        {
          "Section": "ST_REGION_PREDETECTION",
          "ImageParameterName": "IP_0"
        },
        {
          "Section": "ST_BARCODE_LOCALIZATION",
          "ImageParameterName": "IP_0",
          "StageArray": [
            {
              "LocalizationModes": [
                {
                  "Mode": "LM_CONNECTED_BLOCKS",
                  "ModelNameArray": [ "DataMatrixQRCodeLocalization" ]
                }
              ],
              "Stage": "SST_LOCALIZE_CANDIDATE_BARCODES"
            },
            {
              "Stage": "SST_LOCALIZE_BARCODES"
            }
          ]
        },
        {
          "ImageParameterName": "IP_0",
          "Section": "ST_BARCODE_DECODING",
          "StageArray": [
            {
              "Stage": "SST_DECODE_BARCODES",
              "DeblurModes": [
                { "Mode": "DM_BASED_ON_LOC_BIN" },
                { "Mode": "DM_THRESHOLD_BINARIZATION" },
                { "Mode": "DM_DIRECT_BINARIZATION" },
                { "Mode": "DM_DEEP_ANALYSIS" },
                { "Mode": "DM_SHARPENING_SMOOTHING" },
                { "Mode": "DM_GRAY_EQUALIZATION" },
                {
                  "ModelNameArray": [ "DataMatrixQRCodeDeblur" ],
                  "Mode": "DM_NEURAL_NETWORK"
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "ImageParameterOptions": [
    {
      "Name": "IP_0",
      "ApplicableStages": [
        {
          "ImageScaleSetting": {
            "EdgeLengthThreshold": 99999,
            "ReferenceEdge": "RE_SHORTER_EDGE",
            "ScaleType": "ST_SCALE_DOWN"
          },
          "Stage": "SST_SCALE_IMAGE"
        },
        {
          "BinarizationModes": [
            {
              "Mode": "BM_LOCAL_BLOCK",
              "BlockSizeX": 15,
              "BlockSizeY": 15,
              "EnableFillBinaryVacancy": 0,
              "ThresholdCompensation": 10
            }
          ],
          "Stage": "SST_BINARIZE_IMAGE"
        },
        {
          "Stage": "SST_DETECT_TEXTURE",
          "TextureDetectionModes": [
            {
              "Mode": "TDM_SKIP",
              "Sensitivity": 5
            }
          ]
        },
        {
          "Stage": "SST_DETECT_TEXT_ZONES",
          "TextDetectionMode": {
            "Mode": "TTDM_SKIP"
          }
        },
        {
          "IfEraseTextZone": 0,
          "Stage": "SST_REMOVE_TEXT_ZONES_FROM_BINARY"
        }
      ]
    }
  ],
  "GlobalParameter": {
    "IntraOpNumThreads": 1
  }
}
```

