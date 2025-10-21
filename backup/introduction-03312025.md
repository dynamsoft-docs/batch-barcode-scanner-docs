# BatchBarcodeScanner introduction

Dynamsoft `BatchBarcodeScanner` enables you to scan a batch of barcodes from the video stream and reaches a read-rate close to 100%.

<div align="center">
    <img src="assets/abstract.png" width="70%">
    <p>BatchBarcodeScanner resolves the missing barcodes and reach 100% read rate.</p>
</div>

With `BatchBarcodeScanner`, you can:

- Easily achieve 100% Read rate when scanning innumerate of barcodes.
- Preview the real-time barcode scanning status (whether all barcodes are read) with a `panoramic image`.
- If there are unread barcodes, the multiple `scan modes` and other auxiliary features will help you on handling the missing barcodes.

## 1. Key Features

The following features are how `BatchBarcodeScanner` achieves high read-rate:

1. `Scan modes` for decoding barcodes with different conditions.
2. `Result editing` for correcting and completing the result.
3. `Camera technology` for high-quality image acquisition.
4. Auxiliary features enhance barcode recognition throughout the scanning process.

### 1.1. Scan Modes

You can use multiple `scan modes` to complete the entire Barcode recognition.

- `Panorama` Mode: Scan a large area separately but output all scanned barcodes in a `panoramic image`.
- `To-the-Start Overlap (TTSO)` Mode: Complete all barcodes in an area by overlapping results to the initial photo.
- `To-the-Latest Overlap (TTLO)` Mode: Keep high read-rate on scanning the same area by overlapping the most recent frames.

#### 1.1.1. Panorama Mode

`Panorama Mode` is a scan mode that allow you to move the capture device to scan all the barcodes and output them as one panoramic result.

1. No need to capture all barcodes at once.
2. Start from any where.
3. Move toward any directions to scan more barcodes.
4. Close up to recognize small-scale barcodes.
5. Finally output all scanned barcodes in a panoramic image.

<div align="center">
    <img src="assets/mode-panorama.png" width="60%">
</div>

**Useful links**

[How to use - Panorama Mode](how-to-use.md#panorama-mode)

#### 1.1.2. To-the-Start Overlap Mode

This mode requires the user to first capture a photo containing all the barcodes. Then, the user can move closer to the barcode areas to capture any barcodes that were not detected in the photo. Ultimately, all the detected barcodes and the initial photo will be output together as the scanning result.

1. Capture all barcodes in the first photo.

<div align="center">
    <img src="assets/mode-tts-overlap.png" width="60%">
</div>

**Useful links**

[How to use - TTS-Overlap Mode](how-to-use.md#panorama-mode)

#### 1.1.3 To-the-latest Overlap Mode

In this mode, when there is no significant difference between the target objects in consecutive frames, the valid results from the latest few frames are continuously overlaid onto the most recent frame for output. When the camera is nearly stationary at a certain position, this mode can improve the barcode read-rate and stability on the target area.

<div align="center">
    <img src="assets/mode-ttl-overlap.png" width="60%">
</div>

> [!NOTE] If a barcode is moved out of the camera's view, it will be removed from the result list.

**Useful links**

[How to use - TTL-Overlap Mode](how-to-use.md#panorama-mode)

#### Multi-Mode Combination

对初步处理结果不满意
分开扫描了多个区域，事后合并

### 1.2. Result Previewing & Editing

Omissions, misrecognitions, and counting errors are common issues when scanning batch of barcodes. `BatchBarcodeScanner` provides various solutions to address these problems. Result Previewing & Editing is one of these solutions, offering users the following capabilities:

<div align="center">
    <img src="assets/result-modification.png" width="60%">
    <p>Result modification</p>
</div>

- Preview results on the `panoramic image`. With the real-time highlights, users can verify and troubleshoot the unrecognized or misrecognized barcodes.
- Extends the current result with new barcode images.
- Highlight localization results, enabling users to quickly identify unrecognized barcodes.
- Allows editing and removing operations on the non-target, mislocalized, misrecognized or miscounted barcodes.
- Input values manually for the hard-decoding barcodes.

#### 1.2.1. Result Preview

The **decoded barcodes** and **localized but not decoded barcodes** are highlighted on the result `panoramic image`.

<div align="center">
    <img src="assets/result-preview.png" width="30%">
    <p>Preview</p>
</div>

#### 1.2.2. Result Extension

Users only need to click the scan button to continue scanning based on the current result. The continued scanning can be:

- Scanning a new area
- Expanding the existing area
- Completing unrecognized barcodes in the existing area

<div align="center">
    <img src="assets/result-extension.png" width="60%">
    <p>Result extension</p>
</div>

#### 1.2.3. Result Editing

Due to damage, obstruction, or blurry printing, some barcodes are always remained to be unrecognized. Some of the barcodes might not be your targets, and some of the barcodes might be mislocalized. As a result, the result editor of `BatchBarcodeScanner` supports you to:

- Remove the mis-localized barcodes or non-target barcodes.
- Edit the value for the misreading barcodes.
- Input a "newly decoded barcode" manually in the result list.

When using the manual input feature, you have 2 options when inputting the barcode value:

- Scan the barcode from a recognizable image source.
- Manually input the barcode format and the barcode text.

<div align="center">
    <img src="assets/result-manual-input.png" width="60%">
    <p>Manual input</p>
</div>

**Useful links**

[How to use - Edit Your Batch Scan Results](how-to-use/edit.md)

#### 1.2.4. Reuse Historical Data

`BatchBarcodeScanner` supports using historical data as the image source for BatchScan. Since historical data stores both the images and their decoded barcode results, there is no need to re-recognize the images when using historical data. It significantly improves the scanning efficiency. Historical data can be merged with new images and existing `panoramic image`s to create a larger `panoramic image`, or it can be used as the BaseImage for the TTS Overlap mode to further complete the result. Multiple pieces of historical data can also be merged, allowing users to combine the results of multiple tasks saved earlier and export them all at once after the scan is completed.

**Save & Read**

You can save ongoing scanning tasks in the history record, where historical results can also be extended, edited, or manually entered. Therefore, for tasks that are not yet completed or whose processing results are unsatisfactory, you don't need to finish them as soon as possible. Instead, you can save them and wait for unified processing later.

**Merge**

Historical data supports merge operations, including merging images and decoded results.

- If two pieces of historical data share a common area, they will be merged into one image based on the information within the common area. The barcodes in the common area will not be counted repeatedly.
- If two pieces of historical data do not share a common area, they will be merged into a Panoramic Image with two `Sections`. There will be a clear boundary between the two `Sections`.

<div align="center">
    <img src="assets/result-history.png" width="60%">
    <p>You get 2 sections if the historys don't share a common area.</p>
</div>

### 1.3. Camera Technologies

`BatchBarcodeScanner` applies various camera technologies. The differences in these technologies are not only reflected in the quality of image capture, but also in the scanning experience.

#### 1.3.1. AR Camera

The advantage of the AR Camera lies in its better tracking of the recognized barcodes. It allows customers to clearly observe the real-time decoding results.

We got 2 sub-modes under AR Camera:

1. `Frame Trace`: Fluently tracing the previously scanned video frames with decoded barcode information on it.
2. `Plane Projection`: Project the decoded barcode result on a detected plane and continuously tracing the barcode result. Highly recommended when the barcodes are sparse.

#### 1.3.2. DCE Camera

The DCE camera leverages a series of advanced camera control features from DynamsoftCameraEnhancer library. It ensures that the device captures higher quality video frames during the scanning process, improving the accuracy of decoding results and the quality of `panoramic image` stitching. The following features are used in `BatchBarcodeScanner`:

- Auto-switching lenses for ensuring the camera's macro focus quality.
- Blurry video frame filtering.

### 1.4. Auxiliary Features

#### 1.4.2. Layout Analysis

During the scanning process, `BatchBarcodeScanner` can perform layout analysis on the results. Layout analysis can further improve the accuracy of the results and help users identify errors in item placement. It can also be used as one of the `auto-stop` conditions. Layout analysis supports the following modes:

- Matrix Analysis
- Line Analysis
- Auto

<div align="center">
    <img src="assets/layout-example.png" width="80%">
</div>

Layout analysis can tells you here is a missing item:

<div align="center">
    <img src="assets/layout-analysis.png" width="40%">
</div>

#### 1.4.5. Auto-Stop

When the recognition results reach a certain standard, `BatchBarcodeScanner` can automatically end the task. Users can configure the conditions for the `auto-Stop`. The currently supported stop conditions include:

1. Auto-stops when the `layout analysis` confirms that all barcodes are decoded.
2. Auto-stops when the `MaxBarcodesCount` is reached.
3. Auto-stops when it has been a long time since the last new barcode is decoded.

The task is finished when any of the above conditions is met. You can define whether to enable the `auto-stop` and the details of each conditions.

#### 1.4.3. Multi-Section

`BatchBarcodeScanner` supports merging barcode results from different areas into a single output. The results from multiple areas are merged into one `panoramic image`, allowing users to preview all decoded results in a single image.

If the connection between several pieces of `historical data` is not strong enough, they will be merged into a `multi-section` result when using the `Panorama Mode`.
Layout analysis can tells you here is a missing item:

<div align="center">
    <img src="assets/multi-section.png" width="50%">
    <p>.</p>
</div>

## 2. Typical Use Cases

<!-- 场景要大一些，有什么难处，我们是怎么处理的，虚拟相机，视频。。。 -->
<!-- 这块还没想好 -->

### 2.1. Stocktaking by Barcodes

In industries such as manufacturing, retail, and healthcare, you can complete inventory checks using the barcodes on items.

#### For large areas

Concern(s):

1. Scanning one by one is time-consuming.
2. Scan the whole area at once might remain unread barcodes.
3. You might want the information of the whole area but the area is too large for scanning entirely.
4. You want the scanner to tell you whether all barcodes are located in the correct place.

Solution(s):

1. Process multiple barcodes at the same time.
2. Process the whole area at once or seprately.
   1. When scanning the whole area, the result is overlapped based on the latested few frames' information.
   2. When scanning the area seprately, you can closeup and move to scan all the barcodes. A `panoramic image` of the entire area is generated at the end.

<div align="center">
    <img src="assets/batch-scan-typical.png" width="50%">
</div>

### 2.2. Scan Different Planes

Concern(s):

1. User can't decode all planes because a camera can't focus on different planes.
2. If scanned plane by plane, the results will be hard for classifying.
3. The termination between planes is hard to control.

Solution(s):

1. Scans planes by planes. You can either scan the plane entirely or seprately.
2. The results of each plane are merged into a single `panoramic image`.

https://github.com/user-attachments/assets/87e3370e-0042-403c-ad72-b0292bed42d0

### 2.3. Large-scale Inventory Check

Concern(s):

1. The barcode size is too small for scanning entirely.
2. Duplicate barcodes within the area may result in inaccurate or misleading quantity counts.

Solution(s):

1. Separately scan the barcodes but returns all scanned results entirely at the end.
2. Use the plane projection information to record the position of the barcodes.

<div align="center">
    <img src="assets/plane-projection.png" width="50%">
    <p></p>
</div>

`BatchBarcodeScanner` takes a different approach. You can move closer to the targets to scan barcodes that are difficult to recognize. You can continuously move the camera until each barcode is successfully identified. The candidate barcode images are reconstructed during scanning. Once all barcodes have been recognized, you will receive a `panoramic image` of the entire area (equals to what you get by capturing the whole area).

## 3. Supported Platforms

### iOS

- iOS 12.0+
- iPhone x or later
- Xcode 14.0+

### Android

## 4. Try Our Demo

Please contact us to get the download link.
