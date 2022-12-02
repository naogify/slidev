---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://user-images.githubusercontent.com/8760841/199149866-a43ad2fd-a184-4eef-ba09-023a507fcd88.png
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# Tsunami Visualization 3D Map

<!-- For OSS4SDG Sustainable Cities & Communities Hackathon -->

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    For OSS4SDG Sustainable Cities & Communities Hackathon<br/>
    Challenge # 4 – Disaster risk manager<br/>
    Naoki Ohashi
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>



<!--

Hello I'm Naoki Ohashi.
I'm glad to join, and selected to the finalist of OSS4SDG Sustainable Cities & Communities Hackathon.

I took the challenge 4 "Disaster risk manager". I
-->
---
layout: image-right
image: https://avatars.githubusercontent.com/u/8760841
---

# Hello
. . .

- I'm Naoki Ohashi.
- IT engineer at Geolonia, Inc (GIS company in Japan).
- Contributor of Charites (The United Nations Vector Tile Toolkit's project).

- GitHub: https://github.com/naogify
- Twitter: https://twitter.com/naogify

<!--

I'm IT engineer at Geolonia, Inc that is GIS company in Japan, and also contributor of Charites (The United Nations Vector Tile Toolkit's project).

My GitHub account is here, and my Twitter account is also here.
-->
---
layout: image-right
image: /japan.png
---

# I live in Kushimoto
. . .

- Kushimoto town, Wakayama Prefecture, Japan
- Southernmost town of main island of Japan
- World Tsunami Awareness Day (November 5) is based on historical tsunami in 1854 at Wakayama Prefecture. (Inamura-no-hi)
<div 
  style="
    font-size: 10px;
    color: gray;
    position: absolute;
    bottom: 10px;
    right: 10px;
    color: #ffffff;
  "
>
  <p style="margin: 0; line-height: 15px;">OpenStreetMap(https://www.openstreetmap.org/copyright)</p>
  <p style="margin: 0; line-height: 15px;">GSI Japan(https://www.gsi.go.jp/)</p>
  <p style="margin: 0; line-height: 15px;">Geolonia,Inc.(https://geolonia.com/)</p>
</div>

<!--
I live in Kushimoto town, Wakayama Prefecture, Japan.
I'm IT engineer at Geolonia, Inc that is GIS company in Japan, and also contributor of Charites (The United Nations Vector Tile Toolkit's project).

My GitHub account is here, and my Twitter account is also here.
-->

---

# What I built and why I built it ?
. . .

I created Tsunami Visualization Interactive 3D Map for Nankai Trough Mega Earthquake.

I live in Kushimoto, Wakayama Prefecture where Nankai Trough earthquakes are expected to occur.

If it happens, it is expected to cause extensive damage.

The Japanese government has published static disaster prevention maps,  and this time I created a 3d interactive tsunami simulation map based on the tsunami prediction data published by the government.

Compared to ordinary disaster prevention maps, this map allows you to zoom in on any location you like and see the height of the waves in 3D. 

Also, there are the blue pin markers indicating evacuation places, so you can check in advance which evacuation places are close by.

This will lead to a higher survival rate in the event of an earthquake.

---
layout: center
class: text-center
---

# DEMO


<!--
This is the demo of the map.
You can choose the location and the time of the tsunami.
You can move the map by dragging the mouse.
You can choose the time of the tsunami by dragging the slider.This slider has the time of the tsunami from 0 to 60 minutes.

and here is the legend for tsunami height.

For example around 7 minutes after the earthquake, the tsunami height is about 1 meters on the beach.

And after 40 minutes, the main part of kushimoto town is flooded by tsunami.

And this blue pin is the evacuation places.
-->

---

# How I built it ?
. . .

I got the tsunami simulation point data published by the Japanese government in CSV format.

Since the data was in point format, I created 10m square polygons and converted them to GeoJSON format.
Then I created a **vector tile** from the GeoJSON using tippecanoe.

<div style="display: flex; justify-content: space-between;">
  <img src="/point.png" width="400">
  <div style="font-weight: 900; font-size: 24px; margin: auto;">→</div>
  <img src="/grid.png" width="400">
</div>
<p style="font-size: 10px; color: gray; line-height: 13px;">内閣府 南海トラフの巨大地震モデル検討会」（津波断層モデル(11)津波浸水深データ（ケース1）ケース02_堤防破堤）（https://www.geospatial.jp/ckan/dataset/1211）, OpenStreetMap(https://www.openstreetmap.org/copyright), GSI Japan(https://www.gsi.go.jp/), Geolonia,Inc.(https://geolonia.com/)</p>
---

# Attribution
. . .

Tsunami Simulation Data
- 内閣府 南海トラフの巨大地震モデル検討会」（津波断層モデル(11)津波浸水深データ（ケース1）ケース02_堤防破堤）（https://www.geospatial.jp/ckan/dataset/1211）

Map Data
- Geolonia,Inc. (https://geolonia.com/)
- OpenStreetMap(https://www.openstreetmap.org/copyright)
- GSI Japan
 - DEM（https://maps.gsi.go.jp/development/ichiran.html#dem）
 - gsimaps-vector-experiment（https://github.com/gsi-cyberjapan/gsimaps-vector-experiment）

Style
- Geolonia GSI （https://github.com/geoloniamaps/gsi）

---
layout: center
class: text-center
---

# Thank you