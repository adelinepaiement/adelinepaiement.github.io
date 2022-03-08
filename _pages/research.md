---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

My research is in data science and AI for scientific applications.
It is by nature interdisciplinary.
It focuses on developping computer vision, machine learning, and deep learning methods for analysing data from other sciences.
The application domains that I consider are from two broad categories: sciences of the environment, and human sciences.
There is a special focus on the (astro)physics and medical fields.
My research is both applied and theoretical. It aims to develop new tools to support research in its application domains.
It also aims to further developments in AI, motivated by new challenges from the scientific data.
One strong challenge, that is common to all considered application domains, is the need for interpretable methods and results.

Research themes
======
* Computer vision, machine learning, deep learning
* Human sciences & medical applications
* Physics & astrophysics applications
* Interpretable AI through the integration of domain knowledge into the design of AI methods

Ongoing projects -- Physics applications
======
{% include base_path %}
{% for post in site.research_physics reversed %}
  {% include archive-single.html %}
{% endfor %}

Ongoing projects -- Human sciences applications
======
{% include base_path %}
{% for post in site.research_human reversed %}
  {% include archive-single.html %}
{% endfor %}

Past research -- Human sciences applications
======
* Postdoc on project [SPHERE](https://research-information.bris.ac.uk/en/projects/sphere-epsrc-irc), computer vision workpackage (2013-2016)
    * Main activity: development of computer vision and machine learning methods for assessing the quality of movements in orthopaedic patients
* PhD on medical image analysis
    * Main activity: development of computer vision methods for integrated registration, segmentation, and interpolation for 3D/4D modelling from spaced tomographic images
