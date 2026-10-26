# voai - image converter

A private, browser-based image converter for turning HEIC and HEIF photos into JPEG or PNG files.

## Why I built this

I built this project after running into a simple problem while studying for my board exam. I use a Samsung Galaxy phone and needed to capture pictures from a book I bought so I could use them in a study page on my Windows laptop. The phone saved the pictures as HEIC files, but Windows could not display them without the HEVC Video Extensions. When I tried to download the extension, I found that it required payment.

Before building this, I tried several websites and software tools. One service limited me to 10 conversion credits per day. Another produced a downloaded HEIC viewer that did not meet my expectations. I also found a site that required me to approve sharing my files before it would convert them. I wanted something simple, private, and reliable, so I decided to build my own converter instead.

This project is the result. I plan to continue adding features as I use it and discover new ways to make image conversion easier.

## Features

- Convert up to 100 images in one batch
- Export to JPEG or PNG
- Download one image at a time
- Download all images individually
- Download all converted images as a ZIP file
- Conversion progress bar for large batches
- Before and after image previews
- Drag and drop file reordering
- Clear all files with one click
- Resize images while preserving aspect ratio
- JPEG compression quality control
- Metadata removal or preservation when supported
- Light and dark modes
- Local browser processing for privacy
- Offline support with bundled conversion libraries

## Supported formats

Input formats:

- HEIC
- HEIF
- JPEG
- PNG

Output formats:

- JPEG
- PNG

## Usage

Open `index.html` in a browser, then choose files or drag them into the upload area.

1. Select an output format.
2. Choose compression quality and an optional maximum image size.
3. Choose whether metadata should be removed or preserved when supported.
4. Select **Convert photos**.
5. Download files individually, download all files separately, or download a ZIP archive.

The app can also be served from any static web server. For example:

```text
npx serve .
```

## Privacy

Images are processed in the browser and are not uploaded to a server. The converter libraries are bundled in `vendor/`, so the app does not need a CDN or an internet connection to convert files or create ZIP downloads.

## Metadata behavior

Metadata removal is enabled by default for privacy. Same-format JPEG and PNG files can retain their original metadata when preservation is selected. HEIC conversions remove EXIF data in the browser because the bundled HEIC conversion library does not reliably preserve it.

## Project files

- `index.html`: application UI, styles, and browser logic
- `vendor/heic2any.min.js`: local HEIC and HEIF conversion library
- `vendor/jszip.min.js`: local ZIP creation library
