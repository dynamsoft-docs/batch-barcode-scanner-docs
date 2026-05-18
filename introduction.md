---
layout: default-layout
title: Introduction
keywords: Dynamsoft Batch Barcode Scanner, introduction
breadcrumbText: Introduction
description: Introduction of Dynamsoft Batch Barcode Scanner
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Introduction

Dynamsoft Batch Barcode Scanner is a cross-platform (Android & iOS) batch barcode scanning application designed for efficiency and accuracy in high-volume scanning scenarios. Unlike traditional scanners that scan barcodes one at a time or using only one camera frame, our app continuously scan barcodes across multiple frames or photos to progressively build a complete picture of all codes in a scene with a great interactive experience.

It is suitable for scanning densely placed items like lab tubes or inventory boxes. Using Batch Barcode Scanner, you can improve your barcode scanning workflow in the following aspects:

* Boost worker productivity with high scanning efficiency
* Reduce human errors with visual feedback
* Handle challenging conditions with 100% read rate

Demo video:

<video src="https://github.com/dynamsoft-docs/batch-barcode-scanner-docs/releases/download/assets/FOV-mode-demo.mp4" controls style="height: 360px; width: 100%;"></video>


## How it Works

* **Multi-frame recognition fusion**: Read barcodes from multiple photos taken and live camera frames until all the barcodes are recognized.
* **Visual feedback**: Highlight barcodes in different colors to help the user know which barcodes are left for scanning:
   
   * recognized barcodes
   * newly recognized barcodes
   * unrecognized barcodes
   * wanted barcodes 
   
   Batch Barcode Scanner uses a special algorithm based on recognized barcodes and augmented reality (AR) to map previously scanned results to the latest frame.

* **Result image for verification**: Draw recognition results on an image with the scanned objects for post-verification. Image stitching is supported if the camera cannot take one picture to cover all the objects.

**Example:** In the following screenshots, the tubes are in bad lighting condition, many of them cannot be recognized in one shot (unrecognized are in blue while recognized are in green).

![Photo of tubes in bad lighting condition](/assets/images/introduction/photo-taken.jpg){:width="215"} ![Decoding result of one photo](/assets/images/introduction/one-time-decoding.jpg){:width="215"}

You can move the phone closer to read more barcodes (newly recognized are in light blue).

![Barcodes in colors](/assets/images/introduction/barcodes-in-colors.jpg){:width="215"}

If all the barcodes are recognized, you can finish scanning and export the result.

![Completed](/assets/images/introduction/completed.jpg){:width="215"}

## Scanning Modes

The app provides three core scanning modes, each tailored for different workflows:

- **Field of View (FOV) Scan Mode (Default)**

  Results are drawn on the final captured photo. The app highlights all successfully decoded barcodes directly on that image – perfect for post-scan verification.

- **Snap & Scan Mode**  

  An improved version where a reference photo is taken beforehand. During the scanning process, only barcodes that exist within the pre-captured image are highlighted. Any codes appearing outside the original frame are ignored – ideal for fixed‑area inventory tracking.

- **Panorama Scan Mode**  

  A more advanced mode which stitches multiple photos into a single composite image. Best for codes extending beyond a single camera frame.

## Extra Features

- **Wanted Barcode** – Highlight specific barcode values you are looking for, making target identification instant.
- **Export Results** – Save scan data as CSV files, share via email, messaging apps, or cloud storage.
- **Customizable Settings** – Adjust image processing parameters, camera settings, desired barcode formats, colors of barcodes, and more.

## System Requirements

The app works for the following systems:

* iOS or iPadOS 15.0 or newer
* Android 5.0 or newer (arm64-v8a)

## Try Our Demo

You can download the app on app store:

* [Apple Store](https://apps.apple.com/us/app/dynamsoftbatchbarcodescanner/id6751793075)
* Google Play link is coming soon.

You can also get a custom demo based on your specific use case: [request a demo](https://www.dynamsoft.com/use-cases/batch-barcode-scanning/#request-demo-form).

## Next

Continue to read the [guide](/app/guide/first-scan.md) to learn more about its usage.
