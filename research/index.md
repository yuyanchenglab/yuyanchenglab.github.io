---
title: Research
nav:
  order: 10
  tooltip: Software, datasets, and more
---

<h1 style="text-align: left; font-weight:bold;"> {{ page.title }} </h1>

Neurons, among the longest living cells in the human body, undergo various stresses from normal aging to disease states. The central vision of our lab is to understand how neurons age, respond to degenerative insult and injury, and, critically, how they fail to self-repair. By dissecting the molecular and cellular events shaping neuronal functions after acute or chronic damage, we aim to inform potential therapeutics for neurodegenerative diseases and, more broadly, vision repair.

Our primary approach integrates single-cell genomics and spatial transcriptomics with CRISPR-based genetic tools to profile and perturb neurons, including their cell-cell interactions with the environment during health and disease. Focusing on retinal and optic nerve degenerative disorders, our ultimate goal is to translate genomic findings to gene and cell therapies that can restore lost visual functions in human patients.

{% include section.html %}

{% capture text %}

The visual signal processing in the retina relies on the precise organization of diverse neuronal types working coordinately. We are applying single-cell and spatial genomics approaches to dissect the complex molecular and cellular events that underlie retinal responses during aging, injury, and neurodegenerative conditions.

{% endcapture %}

{%
  include feature.html
  image="images/single-cell-and-spatial.png"
  link="research"
  title="Dissecting cell-type specific changes in the retina during normal aging and neurodegenerative conditions"
  text=text
%}

{% capture text %}

A cell's behavior is essentially the readout of gene programs expressed at the time, driven by transcriptional regulators. We couple CRISPR screens with single-cell technology to dissect the gene-regulatory networks determining each cell’s transcriptional state in response to damage, and to identify key upstream transcriptional regulators that can reverse retinal degeneration.
{% endcapture %}

{%
  include feature.html
  image="images/model-validation.png"
  link="research"
  title="Rewiring the transcriptional state of degenerative retina"
  text=text
%}

{% capture text %}

Through computational analysis of multi-omics data, we uncover crucial genes and cell types implicated in neurodegeneration and regenerative failure. Our efforts extend to the development of drugs, gene therapies, and cell therapies aimed at preventing neuronal loss and reinstating physiological functions in animal models of glaucoma and other optic nerve neuropathies.

{% endcapture %}

{%
  include feature.html
  image="images/ultimate-goals.png"
  link="research"
  title="Transforming genomics findings to therapeutic strategies for neuroprotection and neural repair"
  text=text
%}
