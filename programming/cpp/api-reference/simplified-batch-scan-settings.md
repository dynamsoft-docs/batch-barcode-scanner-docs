# SimplifiedPanoramaSettings

```cpp
typedef struct tagSimplifiedPanoramaSettings
{
    StitchMode stitchMode;
    int calcMatrixThreadNum;
    int stitchThreadNum;
    bool hasDuplicateCode;
    bool hasDuplicateTextLine;
    int outputLandmarkTypes; //LandmarkType取或
    PreviewImageSize previewImageSize;
    int maxSideLength;
    char captureVisionTemplateName[64];
    char reserved[256];
    // 11/07/2024 new
    int maxBarcodesCount;
} SimplifiedPanoramaSettings;
```

## AutoStopMode

```cpp
typedef enum AutoStopMode
{
    ASM_OFF = 0,
    ASM_LAYOUT_ANALYSIS_APPROVED = 1,
    ASM_MAX_BARCODES_COUNT_REACHED = 2,
    ASM_NO_MORE_RESULTS = 4
} AutoStopMode;
```

## LayoutAnalysisMode

```cpp
typedef enum LayoutAnalysisMode
{
    LAM_SKIP = 0,
    LAM_AUTO = 1，
    LAM_LINE = 2,
    LAM_MATRIX = 3
} LayoutAnalysisMode;
```

## StitchMode

```cpp
typedef enum StitchMode
{
    STM_PANORAMA = 0,
    STM_TTSO = 1,
    STM_TTLO = 2
} StitchMode;
```
