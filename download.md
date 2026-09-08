---
layout: page
title: File Download
permalink: /download/
---

Your download should begin automatically. 

If the download
does not start, use this <a id="dl_link">direct link.</a>

<!-- Embed Liquid data into a JS object -->
<script>
  const DOWNLOADS = {{ site.data.downloads | jsonify }};
  document.addEventListener("DOMContentLoaded", function () {
    const urlParams = new URLSearchParams(window.location.search);
    const fileKey = urlParams.get("file");

    if (fileKey && DOWNLOADS[fileKey]) {
      const item = DOWNLOADS[fileKey];

      const link = document.getElementById("dl_link");
      link.href = item.url;

      // Optional: Auto-trigger download after 2 seconds
      setTimeout(() => { window.location.href = item.url; }, 2000);
    } 
  });
</script>