---
layout: page
title: Press Kit
include_in_header: true
---

# Press Kit

## Summary

**Price:** $4.99, No In-App Purchases or Subscriptions<br/>
**Platforms:** iOS 16+, iPadOS 16+, macOS 11+ (Apple Silicon required)<br/>
**Languages:** English<br/>
**Privacy Label:** No Data Collected<br/>
**Age Rating:** 17+<br/>
**App Store:** [Download]{{ site.appstore_link }}

## Press Access

To access a free review unit of the app, please get in [contact]({{ site.external_contact_link }}).

## Features

- Feature 1
- Feature 2
- Feature 3

## About

Lorem ipsum dolor sit amet.

## Screenshots

<a id="downloadBtn" href="javascript:void()">Download All Images (.zip)</a>

### iPhone 

<div class="screenshot-gallery">
  <img class="download-image" src="/assets/press/iphone1.png" alt="iPhone Screenshot 1" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone2.png" alt="iPhone Screenshot 2" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone3.png" alt="iPhone Screenshot 3" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone4.png" alt="iPhone Screenshot 4" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone5.png" alt="iPhone Screenshot 5" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone6.png" alt="iPhone Screenshot 6" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone7.png" alt="iPhone Screenshot 7" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone8.png" alt="iPhone Screenshot 8" loading="lazy" />
  <img class="download-image" src="/assets/press/iphone9.png" alt="iPhone Screenshot 9" loading="lazy" />
</div>

### iPad

<div class="screenshot-gallery">
  <img class="download-image" src="/assets/press/ipad1.png" alt="iPad Screenshot 1" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad2.png" alt="iPad Screenshot 2" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad3.png" alt="iPad Screenshot 3" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad4.png" alt="iPad Screenshot 4" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad5.png" alt="iPad Screenshot 5" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad6.png" alt="iPad Screenshot 6" loading="lazy" />
  <img class="download-image" src="/assets/press/ipad7.png" alt="iPad Screenshot 7" loading="lazy" />
</div>

### Mac

<div class="screenshot-gallery">
  <img class="download-image" src="/assets/press/mac1.png" alt="Mac Screenshot 1" loading="lazy" />
  <img class="download-image" src="/assets/press/mac2.png" alt="Mac Screenshot 2" loading="lazy" />
  <img class="download-image" src="/assets/press/mac3.png" alt="Mac Screenshot 3" loading="lazy" />
  <img class="download-image" src="/assets/press/mac4.png" alt="Mac Screenshot 4" loading="lazy" />
  <img class="download-image" src="/assets/press/mac5.png" alt="Mac Screenshot 5" loading="lazy" />
  <img class="download-image" src="/assets/press/mac6.png" alt="Mac Screenshot 6" loading="lazy" />
</div>

### Apple Vision

<div class="screenshot-gallery">
  <img class="download-image" src="/assets/press/vision1.png" alt="Apple Vision Screenshot 1" loading="lazy" />
  <img class="download-image" src="/assets/press/vision2.png" alt="Apple Vision Screenshot 2" loading="lazy" />
  <img class="download-image" src="/assets/press/vision3.png" alt="Apple Vision Screenshot 3" loading="lazy" />
  <img class="download-image" src="/assets/press/vision4.png" alt="Apple Vision Screenshot 4" loading="lazy" />
  <img class="download-image" src="/assets/press/vision5.png" alt="Apple Vision Screenshot 5" loading="lazy" />
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/FileSaver.js/2.0.5/FileSaver.min.js"></script>

<script>
document.getElementById('downloadBtn').addEventListener('click', function() {
    // Get all images with the class name 'download-image'
    const images = document.querySelectorAll('.screenshot-gallery .download-image');
    const zip = new JSZip();
    const promises = [];

    images.forEach((img, index) => {
        const imgSrc = img.src;

        // Fetch the image as a Blob
        const promise = fetch(imgSrc)
            .then(response => response.blob())
            .then(blob => {
                // Add the image to the zip file with a unique name
                zip.file(`image${index + 1}.jpg`, blob);
            })
            .catch(err => console.error('Error fetching the image:', err));

        promises.push(promise);
    });

    // Wait for all images to be processed
    Promise.all(promises)
        .then(() => {
            // Generate the zip file
            return zip.generateAsync({ type: 'blob' });
        })
        .then(content => {
            // Use FileSaver.js to save the zip file
            saveAs(content, 'images.zip');
        })
        .catch(err => console.error('Error generating zip:', err));
});
</script>
