---
layout: default-layout
title: Customization - Dynamsoft Batch Barcode Scanner iOS Documents
keywords: Customization
breadcrumbText: Customization
description: This demostrates how to get your scanner customized.
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Get Your Scanner Customized

The scanning experience in **Dynamsoft Batch Barcode Scanner** is fully customizable. Below are common customization options and instructions on how to provide the necessary materials.

## 1. Device and Camera

Choosing the right device and camera configuration delivers a better scanning experience.

- **AR Camera**  
  - **Strengths**
    - Delivers superior real-time **tracking** of decoded barcodes.
    - Maintains high accuracy even when many **duplicate** barcodes are present.
    - Produces high-quality panoramic images even in **sparse** barcode layouts.
    - Achieves even greater accuracy when **LiDAR** is available.
  - **Limitations**
    - Restricted to the wide-angle lens, which may not focus at very close range.
    - Does not support manual zoom or focus control.

- **DCE Camera**  
  - **Strengths**
    - Supports close-up scanning of **small barcodes** using the ultra-wide camera.
    - Allows flexible **focusing** on different points of interest.
    - Use **zoom-in** to approach instead of reducing the scan distance.
  - **Limitations**
    - Provides less stable tracking compared to the AR Camera.
    - Less accurate when counting duplicate barcodes.
    - May produce segmented panoramic images when barcodes are sparse.

| Device Type / Features | iPad Pro | iPhone Pro (Max) | iPhone 13 and newer | iPhone 11, 12 | iPhone SE (16E) |
| ----------- | -------- | ---------------- | ------------------- | ------------- | --------------- |
| **AR Close-Distance Focus** | ✓ | ✕ | ✕ | ✓ | ✓ |
| **AR 3840 × 2160 Resolution** | ✓ | ✓ | ✓ | ✓ | ✕ |
| **LiDAR Support** | ✓ | ✓ | ✕ | ✕ | ✕ |
| **Auto-Switch to Ultra-Wide Camera** | ✕ | ✓ | ✕ | ✕ | ✕ |
| **High-Quality Ultra-Wide Camera** | ✓ | ✓ | ✕ | ✕ | ✕ |

> **Feature Details**
>
> **AR Close-Distance Focus**  
> Enables the AR camera to focus sharply at short range, enhancing detection of small or densely packed barcodes.  
> Below is a reference table of the **minimum focus distance** (approximate) for supported devices:
>
> | Device Model                     | Min Focus Distance |
> |-----------------------------------|---------------------|
> | iPhone 11                         | ~12cm |
> | iPhone 11 Pro / Pro Max            | ~12cm |
> | iPhone 12 / 12 Mini                | ~8 – 12cm |
> | iPhone 12 Pro / 12 Pro Max         | ~8cm |
> | iPhone 13 / 13 Mini                | ~15cm |
> | iPhone 13 Pro / Pro Max            | ~15cm |
> | iPhone 14 / 14 Plus                | ~20cm |
> | iPhone 14 Pro / Pro Max            | ~20cm |
> | iPhone 15 / 15 Plus                | ~20cm |
> | iPhone 15 Pro / Pro Max            | ~20cm |
> | iPhone 16e                         | ~12cm |
> | iPhone 16 / 16 Plus                | ~20cm |
> | iPhone 16 Pro                       | ~24cm |
> | iPad Pro (2021 / 2022 / 2024)       | ~5cm |
>
> *Tip:* Actual focusing distance can vary slightly depending on lighting conditions and individual device calibration.
>
> **AR 3840 × 2160 Resolution**  
> Enables high-resolution scanning, which captures finer barcode details and increases decoding accuracy—especially for tiny codes.
>
> **LiDAR Support**  
> Devices with a built-in LiDAR sensor provide depth information, giving the AR camera more reliable tracking and higher stitching accuracy.
>
> **Auto-Switch to Ultra-Wide Camera**  
> Automatically switches from the standard wide-angle lens to the ultra-wide lens when the main camera cannot focus at close range, helping maintain focus without manual intervention.
>
> **High-Quality Ultra-Wide Camera**  
> Some devices include an ultra-wide lens with superior optics. Using this lens improves clarity and barcode recognition when you need an extra-wide field of view or close-up focus.

## 2. Barcode Reading Performance

Provide **original images** from your own scenarios so we can optimize decoding performance.

**How to capture original images**

1. Go to **Settings → More Settings → Debug Mode Settings** and enable **`Save Original Images`**.  
2. Return to the scan page and scan as usual.  
3. After scanning, the original images are stored in your photo album. Copy them to your desktop.  
4. Zip the images and share the file with Dynamsoft.

<div align="left">
    <img src="assets/save-original-image.png" width="30%">
</div>

By default, the app captures images at **4K resolution (3840 × 2160)**.  
If your barcodes are large enough and you want faster processing, you may capture **1080p** images instead.

**(Optional) Capture 1080p images**

1. Go to **Settings → More Settings → Resolution** and select **1080p**.  
2. Repeat the above steps to collect a new set of images.

> [!NOTE]  
> After collecting 1080p samples, remember to switch back to **4K** for normal scanning.

## 3. Auto-Stop Conditions

The scanner can stop automatically once specified conditions are met.  
Available options include:

- **Maximum barcode count reached**  
- **No more results detected**  
- **Layout analysis approved**

> [!NOTE]  
> Contact Dynamsoft if you need different or additional stop conditions.

## 4. Result Output

You can customize how scan results are presented:

- Sort decoded barcodes with custom filter conditions.  
- Adjust the highlight style in the panoramic image.  
- Define the data fields included in the exported CSV file.

## 5. Scanner UI

Interface elements can also be tailored, such as:

- Toolbar layout and appearance.  
- Barcode highlight style on the camera view and the result-preview screen.
