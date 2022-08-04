---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

My research is in data science and AI for scientific applications.
It is by nature interdisciplinary.
It focuses on developping computer vision, machine learning, and deep learning methods for analysing data from other sciences.
The application domains that I consider fit into two broad categories: physical sciences, and human sciences.
There is a special focus on the astrophysics and medical fields.
My research is both applied and theoretical. It aims to develop new tools to support research in the (physics and human science) application domains.
It also aims to further develop AI methods, motivated by new challenges from the scientific data.
One strong challenge, that is common to all considered application domains, is the need for interpretable methods and results.
This is currently being addressed by the development of domain informed models, where domain knowledge is integrated into the design of learning methods.

Research themes
======
* Computer vision, machine learning, deep learning
* Physics & astrophysics applications
* Human sciences & medical applications
* Domain informed learning: interpretable AI through the integration of domain knowledge into the design of learning methods

# Ongoing projects

## Physics applications

### Solar Physics

{% include base_path %}
{% for post in site.research_solar reversed %}
  <ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  <ul>
    <li>{{ post.funding }}</li>
    <li>{{ post.collab }}</li>
  </ul>
  </ul>
{% endfor %}

* Detection and characterisation of type II solar radio bursts
    * ERUPTION: dEtection de suRsaUts radio solaires par deeP learning avec inTegratION de principes physiques, CNRS-INS2I “Volet Emergence” 2020
    * MRes supervision, Joseph Jenkins, 2018-2019
    * Collaboration with Observatoire de Paris and Space Environment Laboratory at Tokyo

### Planetology

* Analysis of Martian terrains’ topography and composition from multispectral orbital images
    * PhD supervision, Kévin Kheng, 2018-2022
    * Collaboration with Institut de Planétologie et d’Astrophysique de Grenoble (IPAG)

### Galaxy evolution

* Characterisation of galaxy morphology
    * SIDEREAL: phySics-Informed Deep nEuRal nEtwork for characterising gALaxy morphology, CNRS-MITI “Sciences pour l’IA, l’IA pour les sciences” 2022
    * PhD supervision, Felix Richards, 2017-2022
    * Collaboration with Observatoire de Strasbourg and [MATLAS](http://obas-matlas.u-strasbg.fr/WP/)

### Oceanography

* Prediction of Lagrangian drift at sea
    * PhD co-supervision, Joseph Jenkins, since 2020
    * Collaboration with MIO laboratory, OceanNext, Datlas
* Mapping of ocean dynamics from satellite images
    * PhD co-supervision, Laura Gibbs, since 2018
    * Collaboration with Department of Oceanography at University of Bristol

## Human sciences applications

### Medical

{% include base_path %}
{% for post in site.research_medical reversed %}
  <ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  <ul>
    <li>{{ post.funding }}</li>
    <li>{{ post.collab }}</li>
  </ul>
  </ul>
{% endfor %}

### Linguistic

{% include base_path %}
{% for post in site.research_linguistic reversed %}
  <ul>
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  <ul>
    <li>{{ post.funding }}</li>
    <li>{{ post.collab }}</li>
  </ul>
  </ul>
{% endfor %}

# Past projects

## Physics applications

### Chemistry

*	Prediction of chemical properties and discovery of new crystal structures using deep learning on graphs
    * PhD supervision, Jay Morgan, 2018-2021
    * Collaboration with the Departments of Chemistry at Swansea University (UK) and at University of Rostock (Germany)

## Human sciences applications

### Medical

* Postdoc on project [SPHERE](https://research-information.bris.ac.uk/en/projects/sphere-epsrc-irc), computer vision workpackage (2013-2016)
    * Main activity: development of computer vision and machine learning methods for assessing the quality of movements in orthopaedic patients from depth images.
* PhD on medical image analysis
    * Development of computer vision methods for integrated registration, segmentation, and interpolation for 3D/4D modelling from spaced tomographic images. Main application to cardiac cine MRI.
