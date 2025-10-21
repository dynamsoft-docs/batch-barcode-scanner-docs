# Instructions

## Table of content

- [Instructions](#instructions)
  - [Table of content](#table-of-content)
  - [Preparations](#preparations)
  - [Scanning](#scanning)
    - [Panorama Scanning](#panorama-scanning)
    - [To-the-Start (TTS) Overlapping Scanning](#to-the-start-tts-overlapping-scanning)
    - [To-the-Latest (TTL) Overlapping Scanning](#to-the-latest-ttl-overlapping-scanning)
  - [Scan finished](#scan-finished)
  - [For Polydeck](#for-polydeck)
  - [For Kingston](#for-kingston)
  - [For Lens](#for-lens)

## Preparations

1. **Mode Selection**

   - Panorama mode is selected by Default.
   - You can select the mode via the **Mode Selection** button. Please select the mode base on your requirement
     - Panorama: Moving and scanning from the start to the end. A **PanoramicImage** is generated from the participated images (video frames) during the scanning.
     - TTS overlapping: Firstly, set a **BaseImage** by taking a photo. Then start scanning and overlap the decoded barcode results to the **BaseImage**. Generally, the **BaseImage** requires a read-rate at 50%.
     - TTL overlapping: Start scanning directly and overlap the previously recognized barcode decoding results to the latest video frame.

2. **Template Selection**

   > You may have to import a online template for the first time. You can skip the step 1-4 after you have import the template.

   1. Contact us for a customized template.
   2. Click the settings button on the top-right, select **More settings**.
   3. Under the **Use Preset Template**, click **Import Template** button.
   4. Input the URL of the template, click "OK". After that your template will be added to the list of **Preset Templates**.
   5. Select the template your imported under **Preset Templates**.

3. **Camera Settings**

   1. Resolution: 3840\*2160 recommended. (Generally, 1920\*1080 is not recommended for batch scanning. However, it might improve the processing speed for some simple scenarios.)
   2. AR Camera:
      1. Frame trace: Fluently tracing the previously scanned barcodes. (Short distance focusing is not supported in this camera mode.)
      2. Plane projection: Currently not supported.
   3. DCE Camera: Support Wide-Angle camera, Ultra-Wide-Angle camera and an auto-swith camera (between Wide-Angle & Ultra-Wide-Angle camera)

## Scanning

### Panorama Scanning

1. Please keep at least 5 scanned barcodes on your screen when scanning.
2. Please don't move too fast.
3. It is recommended to keep the phone (camera) parallel to the target items (barcodes). Perspective might cause the error count of the barcodes or the mis-stitching of the panorama image.

### To-the-Start (TTS) Overlapping Scanning

Explanation of the concept(s)：

**BaseImage**: Each time when starting the TTS Overlapping Scanning, you have to set a base image. Generally, it asks you to take a photo from the camera. The photo will be set as the **BaseImage**. The TTS Overlap mode requires the **BaseImage** to have about 50% read-rate. Otherwise, the scanning process might get errors.

1. If no barcode is decoded from the **BaseImage**, the **BaseImage** set will fail.
2. If the read-rate of the **BaseImage** is less than 50%, the batch barcode scanning might fail. (Looks like not working on the App. The algorithm don't know how many barcode are there in the BaseImage, you have to evaluate the read-rate manually.)

### To-the-Latest (TTL) Overlapping Scanning

1. Barcode decoding result are discarded if they no longer exist in the latest video frame.
2. The following facts may cause a failure:
   1. Moving to fast
   2. Perspective is too high.

> Currently, we didn't get any customer using this mode. As a result, we didn't spend much time on testing it.

## Scan finished

> **BatchBarcodeScanResult**: It is an objetc includes a **PanoramicImage** and all recognized **BarcodeResultItem** on the **PanoramicImage**.

1. Result Highlights:
   1. Decoded Barcode Result
   2. Localized Barcode Result (Not decoded)
   3. Not a target: A barcode (or a area) that manually excluded.
2. **Start** button: Click the start button again to continue working on the current **BatchBarcodeScanResult**. You can use any mode to continue working on the **BatchBarcodeScanResult**. You can reference to **Mode Selection**.
3. **Reset**: Start a new task
4. Add Result(s):
   1. **Add Image**. Support Adding:
      1. A image in the album.
      2. A **BatchBarcodeScanResult** in the history.
      3. Open the camera and take a new photo.
   2. **Maunal Input**
5. Edit Result(s):
   1. Click the highlighted barcode result on the view, you will see editor toolbar on the bottom of the screen.
6. History:
   1. Use **Save** button to save the currently displayed **BatchBarcodeScanResult**. The unsaved **BatchBarcodeScanResult** will be removed after **Reset**.
   2. Use **View History** button to view all saved historys. You can:
      1. Click **Preview** to open the **BatchBarcodeScanResult** in the history. You can continue working on it.
      2. You can export the history **BatchBarcodeScanResult** to a .csv file or image file.
      3. You can remove the selected history item.

## For Polydeck

1. Mode Selection: Panorama Mode
2. Camera: DCE Auto, 3840*2160 Resolution
3. Template:
   1. [code128-multi-column-02072025.json](https://tst.dynamsoft.com/temp/code128-multi-column-02072025.json)

## For Kingston

1. Mode Selection: Panorama Mode
2. Camera: DCE Auto, 3840*2160 Resolution // You can try AR Frame trace.
3. Template:
   1. [datamatrix-pdf417-02072025-02.json](https://tst.dynamsoft.com/temp/datamatrix-pdf417-02072025-02.json)

## For Lens

1. Mode Selection: Panorama Mode
2. Camera: DCE Wide-Angle, 3840*2160 Resolution
3. ScanRegion：Top 0.4, Bottom 0.6, Left 0, Right 1
4. Template:
   1. [3x18-inverted-datamatrix-02072025.json](https://tst.dynamsoft.com/temp/3x18-inverted-datamatrix-02072025.json)
   2. [6x25-inverted-datamatrix-02072025.json](https://tst.dynamsoft.com/temp/6x25-inverted-datamatrix-02072025.json)
