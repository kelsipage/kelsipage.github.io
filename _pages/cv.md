---
layout: page
permalink: /cv/
title: cv
nav: true
nav_order: 2
description: Take a look at my past professional work and volunteer experience.
---

<!-- PDF Download Link -->
<div class="text-center mb-4">
  <a href="{{ '/assets/pdf/CV.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
    <i class="fa-solid fa-download"></i> Download CV (PDF)
  </a>
</div>

<!-- Embedded PDF Viewer -->
<div class="pdf-container" style="width: 100%; height: 80vh; border: 1px solid #ddd; border-radius: 8px;">
  <iframe 
    src="{{ '/assets/pdf/CV.pdf' | relative_url }}" 
    width="100%" 
    height="100%" 
    style="border: none; border-radius: 8px;">
    <p>Your browser does not support PDFs. 
    <a href="{{ '/assets/pdf/CV.pdf' | relative_url }}" target="_blank" rel="noopener noreferrer">Download the PDF</a>.</p>
  </iframe>
</div>
