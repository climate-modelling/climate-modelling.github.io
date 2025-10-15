---
layout: splash
permalink: /
hidden: true
header:
#   overlay_color: "#5e616c"
  overlay_image: /assets/images/header.jpg
#   actions:
    # - label: "<i class='fas fa-download'></i> Install now"
    #   url: "/docs/quick-start-guide/"
excerpt: 
    "at the University of Oxford"
intro: 
  - excerpt: <cite>The Climate Modelling research group at Oxford combines climate and computer science to build better models of the climate on Earth and other planets. We do research on numerical modelling, machine learning and high-performance computing for efficient predictions of future climates; data compression and information theory; and software engineering to build next-generation climate models. </cite>

#   A flexible two-column Jekyll theme. Perfect for building personal sites, blogs, and portfolios.<br />
#   <small><a href="https://github.com/mmistakes/minimal-mistakes/releases/tag/4.24.0">Latest release v4.24.0</a></small>
feature_row:
  - image_path: /assets/images/climatebench.png
    alt: "Global temperature map"
    title: "ClimateBench"
    excerpt: "A benchmark dataset for the emulation of full-complexity climate models."
    url: "/projects/climatebench_app/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/shiptracks_small.jpg
    alt: "Shiptracks"
    title: "Detecting ship tracks"
    excerpt: "Using machine learning to automatically detect the brightening effect that shipping can have on clouds."
    url: "/projects/shiptracks"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /assets/images/emulator_schematic.svg
    alt: "Emulator schematic"
    title: "Model Emulation for Calibration"
    excerpt: "Developing climate model emulators for better parameter estimation and calibration."
    url: "/projects/emulation/"
    btn_class: "btn--primary"
    btn_label: "Learn more"    
---

{% include feature_row id="intro" type="center" %}

## Project Highlights

{% include feature_row %}

## News

{% assign sorted = site.news | sort: 'date' | reverse %}

<div id='short_news' style="display: block;">
  <ul>
  {% for news in sorted limit:5 %}
    <li><b> {{ news.date | date: "%y/%m" }} </b> - {{ news.content | markdownify  | remove: "<p>" | remove: "</p>"}} </li>
  {% endfor %}
  </ul>
  <a href="#" onclick="hideBlock('short_news'); showBlock('long_news'); return false;" class="btn btn--primary">Show more</a>
</div>

<div id='long_news' style="display: none;">
  <ul>
  {% assign sorted = site.news | sort: 'date' | reverse %}
  {% for news in sorted %}
    <li><b> {{ news.date | date: "%y/%m" }} </b> - {{ news.content | markdownify  | remove: "<p>" | remove: "</p>"}} </li>
  {% endfor %}
  </ul>
  <a href="#" onclick="hideBlock('long_news'); showBlock('short_news'); return false;" class="btn btn--primary">Show less</a>
</div>
