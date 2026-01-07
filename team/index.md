---
title: Team
nav:
  order: 20
  tooltip: About our team
---

<h1 style="text-align: left; font-weight:bold;"> {{ page.title }} </h1>

{% include section.html %}

{% include list.html data="members" component="portrait" filters="role: pi" %}
{% include list.html data="members" component="portrait" filters="role: postdoc" %}
{% include list.html data="members" component="portrait" filters="role: bioinformatics" %}
{% include list.html data="members" component="portrait" filters="role: wet-tech" %}
{% include list.html data="members" component="portrait" filters="role: phd" %}
<!-- {% include list.html data="members" component="portrait" filters="role: ^(?!pi$|undergrad)" %} -->
{% include list.html data="members" component="portrait" filters="role: undergrad" %}

{% include section.html %}

<h2 style="text-align: left; font-weight:bold;"> Former Members </h2>

{% include list.html data="members" component="portrait" filters="role: former" %}