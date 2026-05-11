---
layout: default-layout
title: Three Scanning Modes
keywords: guide, first scan
breadcrumbText: Three Scanning Modes
description: This page introduces how to perform a basic batch barcode scan.
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Three Scanning Modes

The app provides three core scanning modes, each tailored for different workflows:

- **FOV (Field of View) Mode (Default)**

  Results are drawn on the final captured photo. The app highlights all successfully decoded barcodes directly on that image – perfect for post-scan verification.

- **Scan & Snap Mode**  

  An improved version where a reference photo is taken beforehand. During the scanning process, only barcodes that exist within the pre-captured image are highlighted. Any codes appearing outside the original frame are ignored – ideal for fixed‑area inventory tracking.

- **Panorama Mode**  

  A more advanced mode which stitches multiple photos into a single composite image. Best for codes extending beyond a single camera frame.

We've introduced the usage of the FOV Mode. Let's learn how to use the two extra modes.

## Scan & Snap

When using the Scan & Snap mode, you need to capture a photo of the all the barcodes first and there should be some barcodes recognized in this photo.

Then, it works just like the FOV mode, except barcodes outside the photo taken will not be highlighted.

![snap-and-scan](/assets/images/guide/snap-and-scan.jpg)

## Panorama

When using the Panorama mode, you can take photos continuously to stitch images so that you can get a whole image of all the barcodes, which the default field of view cannot contain.

![panorama](/assets/images/guide/panorama.jpg)

There are some requirements for the Panorama mode:

1. The barcodes have to be close with each other.
2. There should be some duplicate recognition results of each photo. Otherwise, it cannot stitch the photos accurately.

Read on to learn about more customization options: [Customization](/app/guide/customization.md).