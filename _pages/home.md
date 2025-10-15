---
layout: splash
permalink: /
hidden: true
header:
#   overlay_color: "#5e616c"
  overlay_image: /assets/images/header.jpg
excerpt: 
    "at the University of Oxford"
intro: 
  - excerpt: <cite>The Climate Modelling research group at Oxford combines climate and computer science to build better models of the climate on Earth and other planets. We do research on numerical modelling, machine learning and high-performance computing for efficient predictions of future climates; data compression and information theory; and software engineering to build next-generation climate models. </cite>

feature_row:
  - image_path: https://github.com/user-attachments/assets/5e614339-820d-4c9a-a545-318863ff8b35
    alt: "SpeedyWeather simulation"
    title: "SpeedyWeather.jl"
    excerpt: "An interactive, flexible atmospheric model built to accelerate climate research."
    url: "/projects/speedyweather/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: https://github.com/user-attachments/assets/65bb61b7-ce6f-48d7-b08d-d9fdc08c56fa
    alt: "Bitinformation"
    title: "Data compression and BitInformation"
    excerpt: "Compressing atmospheric data into its real information content"
    url: "/projects/datacompression"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: https://github.com/user-attachments/assets/c6e8a307-072b-4022-a56d-2af486fc46fd
    alt: "Testing MLWP"
    title: "Testing generalisation of Machine Learning-based models"
    excerpt: "Machine learning has to respect the physics to generalise to future climates"
    url: "/projects/spatialgeneralisation/"
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
