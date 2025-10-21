# BatchBarcodeScanner introduction

Dynamsoft Batch Barcode Scanner is a solution for you to quickly set up an app for scanning a batch of barcodes. BatchBarcodeScanner通过视频流扫描一个或几个区域的大量Barcode，将这一过程中获得的Barcode结果统一输出。一张全景图会作为结果的一部分和解码结果一起输出。这张全景图会包含并且高亮全部解出的Barcode以便使用者预览，校验。BatchBarcodeScanner预置了3种扫描模式，用户可以结合场景选择一个最适合的模式，也可以在一个扫描任务中使用多种模式来协作完成。

Comparing with traditional barcode scanning apps:

BatchBarcodeScanner can scan a bulk of barcodes and output all the results at once. The traditional barcode scanning apps have to scan one by one.
BatchBarcodeScanner can output a panoramic image of all the barcodes scanned in a batch.
BatchBarcodeScanner拥有更加准确的计数能力。BatchBarcodeScanner聚焦于整个Batch，Batch中的每个Barcode只会被统计一次，而传统BarcodeScanner中，同一个Barcode只要被相机重复采集就会被重复统计

Comparing with decode from a photo:

BatchBarcodeScanner has higher barcode read rate. Idealy, the read rate of BatchBarcodeScanner can be close to 100%, which is much higher than decoding from a photo.

## 1. Key Features

### 1.1. Scan Modes

BatchBarcodeScanner 提供了3种可自由切换的扫描模式

- 结合实际场景选择最适合的模式
- 结合不同模式的特点，交替使用不同模式来完成一个扫描任务

[image: Panorama切换至TTS-Overlap]

#### 1.1.1. Panorama Mode

在此模式下你可以不断的移动镜头去寻找还未识别的Barcode，识别过程中用到的视频帧会被拼接成一张全景图

#### 1.1.2. To-the-Start Overlapping Mode

此模式要求使用者先拍摄一张包含全部Barcode的远景图，此后用户可以靠近码区，对远景图没有识别到的码进行补充，最终全部识别到的Barcode和初次拍摄的远景图会一起作为扫描结果输出。

#### 1.1.3 To-the-latest Overlapping Mode

此模式在前后帧的目标物无巨大差异时，会把最新几帧的有效结果持续叠加到最新一帧上进行输出，从而提高解码成功率以及结果的稳定性。

### 1.2. Camera Technologies

BatchBarcodeScanner应用了多种相机技术。这些相机技术的差异不仅体现在图像采集的不同上，针对不同的场景，选择合适的相机模式，会带来更好的扫描体验

#### 1.2.1. AR Camera

AR Camera的优势在于对识别到的Barcode有更好的跟踪效果。

We got 2 sub-modes under AR Camera:

1. `Frame Trace`: Fluently tracing the previously scanned video frames with decoded barcode information on it.
2. `Plane Projection`: Project the decoded barcode result on a detected plane and continuously tracing the barcode result. Highly recommended when the barcodes are sparse.

#### 1.2.2. DCE Camera

DCE camera的特点是它能够采集到更高质量的视频帧以确保BatchScan的结果质量，在BatchBarcodeScanner中应用了DCE相机的以下功能

- Auto-switch between Wide-Angle and Ultra-Wide-Angle. Support micro-distance focus.
- Blurry video frame filtering

### 1.3. Result Previewing & Editing

除了解码成功的Barcode之外，BatchBarcodeScanner的结果中还会附带一张把高亮显示了全部Barcodes的PanoramicImage。

实时预览，快速发现问题，提前处理。

[image: Localized result]

BatchBarcodeScanner的结果支持编辑，拓展，删除等操作

[image: Edit]

Manual Input

History reuse

### 1.4. Auxiliary Features

#### 1.1.2. Layout Analysis

BatchBarcodeScanner在扫描过程中可以对结果进行布局分析，布局分析可以进一步提高结果的准确性，也可以帮助使用者找出物品摆放中的错误

- Matrix Analysis
- Line Analysis
- Auto  // Default
- Skip

#### 1.1.5. Auto-Stop

当识别结果达到一定标准时BatchBarcodeScanner可以做到自动结束任务。用户可以对Auto-Stop的条件进行配置。目前支持的结束条件包括:

- Auto-Stops when the layout analysis confirms that all barcodes are decoded.
- Auto-stops when the MaxBarcodesCount is reached.
- Auto-stops when it has been a long time since the last new barcode is decoded.

The task is finished when any of the above conditions is met.

#### 1.1.3. Multi-Section

BatchBarcodeScanner支持把分布于不同区域的Barcodes结果合并输出到一个结果中。多个区域的结果会被合并到一张PanoramicImage里，因此用户可以从一张图中预览全部的解码结果。

## 2. Typical Use Cases

Matrix

