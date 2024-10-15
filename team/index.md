---
title: Team
nav:
  order: 20
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

Yuyan received her PhD from the University of Miami in Biochemistry and Molecular Biology (mentor Dr. Richard Jope). She then went on to the University of California, Los Angeles for her postdoctoral training in the laboratory of Dr. Dan Geschwind. Her work leverages functional genomics, computational biology, and experimental animal models to understand the biology of neurodegeneration and to discover potential therapeutic for neural repair.  Yuyan started her lab at Penn in January 2024 studying retinal degenerative disorders using single-cell and spatial genomics approaches. Outside of the lab, Yuyan looks for ways to stay active and creative. She plays a mix of sports, including swimming, skiing, and tennis.

{% include section.html %}

{% include list.html data="members" component="portrait" filters="role: pi" %}
{% include list.html data="members" component="portrait" filters="role: ^(?!pi$)" %}

{% include section.html background="images/background.jpg" dark=true %}

{% include section.html %}

# Collaborators

{% capture content %}

{% include figure.html image="images/photo.jpg" %}
{% include figure.html image="images/photo.jpg" %}
{% include figure.html image="images/photo.jpg" %}

{% endcapture %}

{% include grid.html style="square" content=content %}
