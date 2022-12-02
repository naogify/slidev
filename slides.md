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
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
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

---
layout: image-right
image: /japan.png
---

# I live in Kushimoto
. . .

- Kushimoto town, Wakayama Prefecture, Japan
- Northern part of main island of Japan
- World Tsunami Awareness Day (November 5) is based on historical tsunami in 1854 at Wakayama Prefecture. (Inamura-no-hi)

---

# What I built and why I built it ?
. . .

I created Tsunami Visualization Interactive 3D Map for Nankai Trough Mega Earthquake.

I live in Kushimoto, Wakayama Prefecture, Japan, where a major earthquake called the Nankai Trough Earthquake is said to be possible.

If it happens, it is expected to cause extensive damage.

The government has published static disaster prevention maps,  and this time I created a 3d interactive tsunami simulation map based on the tsunami prediction data published by the government.

Compared to ordinary disaster prevention maps, this map allows you to zoom in on any location you like and see the height of the waves in 3D. 

Also, there are the blue pin markers indicating evacuation centers, so you can check in advance which evacuation centers are safe.

This will lead to a higher survival rate in the event of an earthquake.

---
layout: center
class: text-center
---

# DEMO

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

---

# Attribution
. . .

Tsunami Simulation Data
- 内閣府 南海トラフの巨大地震モデル検討会」（津波断層モデル(11)津波浸水深データ（ケース1）ケース02_堤防破堤）（https://www.geospatial.jp/ckan/dataset/1211）

Map Data
- Geolonia
- OpenStreetMap
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