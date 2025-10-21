# BatchBarcodeScanner introduction

Dynamsoft Batch Barcode Scanner is a solution for you to quickly set up an app for scanning a batch of barcodes. `BatchBarcodeScanner` scans a large number of barcodes in one or more areas via video stream, outputting the barcode results obtained during this process in a unified manner. A `panoramic image` is included as part of the result, alongside the decoded data. This `panoramic image` highlights and contains all the decoded barcodes, allowing the user to preview and verify them. `BatchBarcodeScanner` is preset with three scanning modes, `panorama`, `to-the-start overlap`, and `to-the-latest overlap`. These modes allows users to choose the most suitable mode based on the scenario. Additionally, multiple modes can be used in a single scanning task to collaborate and complete the process.

When comparing with the traditional barcode scanner:

- `BatchBarcodeScanner` can scan multiple barcodes continuously and output all the results at once, while traditional barcode scanning apps scan them one by one.
- `BatchBarcodeScanner` can output a `panoramic image` of all the barcodes scanned in a batch.
- BatchBarcodeScanner has more accurate counting capabilities. It focuses on the entire batch, ensuring that each barcode in the batch is counted only once. In contrast, traditional barcode scanners will count the same barcode multiple times if it is repeatedly captured by the camera.

When comparing with decode from a photo:

- `BatchBarcodeScanner` has higher barcode read rate. Idealy, the read rate of `BatchBarcodeScanner` can be close to 100%, which is much higher than decoding from a photo.

## 1. Key Features

### 1.1. Scan Modes

`BatchBarcodeScanner` provides 3 scan modes for you to choose from:

- Panorama Mode
- To-the-Start Overlap Mode
- To-the-Latest Overlap Mode

You can complete a barcode scanning task using a single mode or by combining multiple modes. There are no restrictions on switching between modes, so regardless of the mode you start with, you can switch to any another mode to continue the task.

#### 1.1.1. Panorama Mode

In this mode, you can continuously move the camera to look for new barcodes. After the scanning task is completed, these barcodes will be bundled and output. During the scanning process, information about the barcodes and video frames will be constantly recorded, and a `panoramic image` will be generated in real-time for the user to preview. In this mode, you can easily see where there are still unrecognized barcodes. You can approach these areas to recognize them right away, or you can choose to recognize the remaining barcodes after most of the task is completed.

<div>
    <img src="assets/mode-panorama.png" width="60%">
</div>

**Useful links**

[How to use - Panorama Mode](how-to-use.md#panorama-mode)

#### 1.1.2. To-the-Start Overlap Mode

This mode requires the user to first capture a photo containing all the barcodes. Then, the user can move closer to the barcode areas to capture any barcodes that were not detected in the photo. Ultimately, all the detected barcodes and the initial photo will be output together as the scanning result.

<div>
    <img src="assets/mode-tts-overlap.png" width="60%">
</div>

**Useful links**

[How to use - TTS-Overlap Mode](how-to-use.md#panorama-mode)

#### 1.1.3 To-the-latest Overlap Mode

In this mode, when there is no significant difference between the target objects in consecutive frames, the valid results from the latest few frames are continuously overlaid onto the most recent frame for output. When the camera is nearly stationary at a certain position, this mode can improve the barcode read-rate and stability on the target area.

<div>
    <img src="assets/mode-ttl-overlap.png" width="60%">
</div>

**Useful links**

[How to use - TTL-Overlap Mode](how-to-use.md#panorama-mode)

### 1.2. Camera Technologies

`BatchBarcodeScanner` applies various camera technologies. The differences in these technologies are not only reflected in the quality of image capture, but also in the scanning experience.

#### 1.2.1. AR Camera

The advantage of the AR Camera lies in its better tracking of the recognized barcodes. It allows customers to clearly observe the real-time decoding results.

We got 2 sub-modes under AR Camera:

1. `Frame Trace`: Fluently tracing the previously scanned video frames with decoded barcode information on it.
2. `Plane Projection`: Project the decoded barcode result on a detected plane and continuously tracing the barcode result. Highly recommended when the barcodes are sparse.

<div>
    <img src="assets/camera-ar.png" width="60%">
</div>

#### 1.2.2. DCE Camera

The DCE camera leverages a series of advanced camera control features from DynamsoftCameraEnhancer library. It ensures that the device captures higher quality video frames during the scanning process, improving the accuracy of decoding results and the quality of `panoramic image` stitching. The following features are used in `BatchBarcodeScanner`:

- Auto-switching lenses for ensuring the camera's macro focus quality.
- Blurry video frame filtering.

### 1.3. Result Previewing & Editing

As mentioned above, in addition to the successfully decoded barcodes, the results of `BatchBarcodeScanner` also include a `panoramic image`. This `panoramic image` not only supports preview during the scanning process but also allows for editing of the recognized results.

#### 1.3.1 Previewable

The **decoded barcodes** and **localized but not decoded barcodes** are highlighted on the result `panoramic image`.

<div>
    <img src="assets/result-preview.png" width="60%">
</div>

#### 1.3.2 Editable

For unnecessary barcodes or mis-localized barcodes, you can remove them using the result editing feature. You can also modify the barcode value of an already recognized barcode.

<div>
    <img src="assets/result-edit.png" width="60%">
</div>

#### 1.3.3 Extensible

The scanning results of `BatchBarcodeScanner` support further expansion by the user. Expansion of the results can be achieved by adding new image sources to increase decoding results or by manually entering new barcode values.

When adding a new image source, images from the photo gallery, newly captured photos, video frames, or even saved historical results can be used as input. The way the new image source expands into the current results depends on the mode you select.

When manually entering a new barcode, you can specify the location, barcode type, and barcode value for the new barcode.

#### 1.3.4 Reusable

`BatchBarcodeScanner` supports using historical data as the image source for BatchScan. Since historical data stores both the images and their decoded barcode results, there is no need to re-recognize the images when using historical data. It significantly improves the scanning efficiency. Historical data can be merged with new images and existing `panoramic image`s to create a larger `panoramic image`, or it can be used as the BaseImage for the TTS Overlap mode to further complete the result. Multiple pieces of historical data can also be merged, allowing users to combine the results of multiple tasks saved earlier and export them all at once after the scan is completed.

### 1.4. Auxiliary Features

#### 1.1.2. Layout Analysis

During the scanning process, `BatchBarcodeScanner` can perform layout analysis on the results. Layout analysis can further improve the accuracy of the results and help users identify errors in item placement. It can also be used as one of the `auto-stop` conditions. Layout analysis supports the following modes:

- Matrix Analysis
- Line Analysis
- Auto

<div>
    <img src="assets/layout-example.png" width="80%">
</div>

Layout analysis can tells you here is a missing item:

<div>
    <img src="assets/layout-analysis.png" width="40%">
</div>

#### 1.1.5. Auto-Stop

When the recognition results reach a certain standard, `BatchBarcodeScanner` can automatically end the task. Users can configure the conditions for the `auto-Stop`. The currently supported stop conditions include:

1. Auto-Stops when the `layout analysis` confirms that all barcodes are decoded.
2. Auto-stops when the `MaxBarcodesCount` is reached.
3. Auto-stops when it has been a long time since the last new barcode is decoded.

The task is finished when any of the above conditions is met. You can define whether to enable the `auto-stop` and the details of each conditions.

#### 1.1.3. Multi-Section

`BatchBarcodeScanner` supports merging barcode results from different areas into a single output. The results from multiple areas are merged into one `panoramic image`, allowing users to preview all decoded results in a single image.

If the connection between several pieces of `historical data` is not strong enough, they will be merged into a `multi-section` result when using the `Panorama Mode`.
Layout analysis can tells you here is a missing item:

<div>
    <img src="assets/multi-section.png" width="40%">
</div>

## 2. Typical Use Cases

### 2.1 Multiple Barcodes on a Document

You can easily scan all barcodes on the document. If there are barcode you want to exclude from the scan result, you can add filter conditions or remove them after scanning.

<div>
    <img src="assets/scenario-document.png" width="20%">
</div>

### 2.2 Large number of barcodes in a container

BatchBarcodeScanner can scan all the barcodes in a container in several seconds and achieve nearly 100% read rate.

<div>
    <img src="assets/scenario-container.png" width="20%">
</div>

### 2.3 Inventory management by scanning the barcodes on the packaging boxes/cartons

#### 2.3.1 On the Same Plane

Scan barcodes on the boxes can be easily handled.

<div>
    <img src="assets/scenario-box.png" width="20%">
</div>

If the targets are on large cartons, you can swith to AR Camera - Plane projection to scan them.

<div>
    <img src="assets/scenario-carton.png" width="20%">
</div>

#### 2.3.2 On different Planes

// 类似镜片

### 2.4. Checkout Items

// TTL Overlap, 物品一个个拿到镜头下计数

## 3. Supported Platforms

### iOS

- iOS 12.0+
- iPhone x or later
- Xcode 14.0+

### Android

## 4. Try Our Demo

Please contact us to get the download link.
