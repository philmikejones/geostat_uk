+++
title = "GIS software"
date = 2018-01-13
weight = 20
chapter = true
+++

# GIS software

For most GIS and thematic mapping uses we recommend QGIS. We strongly recommend the Long Term Release (LTR) version.

{{% notice info %}}
https://www.qgis.org/en/site/
{{% /notice %}}

We like QGIS because it's:

- professional quality software
- actively maintained by a large number of contributors
- supported by a number of sponsors
- open source (GPL)
- not restricted by licensing requirements (\*cough\*ArcGIS\*cough\*)
- stable
- what we used for our PhDs!


## Alternatives

In recent years R has become a very capable GIS programme in its own right. If you already use R it's an ideal environment and is what I (Phil) use for most of my GIS work.

Make sure you use the <code>[sf](https://r-spatial.github.io/sf/)</code> package as this is replacing older GIS packages. Install and load with:

<pre><code>
install.packages("sf")
library("sf")
</code></pre>
