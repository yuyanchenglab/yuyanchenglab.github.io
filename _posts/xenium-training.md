---
title: We Begin Our Journey Into Spatial Transcriptomics
author: jeffrey-maurer
image: images/news/2025-03-18-xenium-wide-1.jpg
---

# 130 Years
<p style="font-size:8pt;text-align:center;">Editted by Cass Poon, Dr. Gaby Rice and Dr. Cheng.</p>

The newest AI advances are coming at a record pace. Large language models this decade have modelled the patterns of human language to such an extent that it can follow basic commands or keep a decent conversation[^converseAI]. The first hurdle to get to this point was computing power--running and coordinating billions of calculations requires a machine with trillions of parts assembled correctly. The next set of advancements have been from developing specialized neural network architecture that can efficiently learn the motifs that human brains produce in communication[^attention]. It seems fitting that the machine learning model based on the neuron might mirror its inspiration. This cyclical study of digital and biological neurons is where the Cheng lab intends to explore.

The trillions of parts that make up the human nervous system can be disrupted in many ways. One such disorder is glaucoma and is one of the leading causes of permanent vision loss[^RGC_degen]. We know that neurons have some ability to self-repair in response to injury, but we do not know precisely what molecular mechanisms determine the threshold between a survivable insult and not. We know that chronically increased itraocular pressure (IOP) results in retinal ganglion cell (RGC) death and contributes to glaucoma, but the finer details escape observation and description.

That is why our lab has invested in a Xenium Analyzer from 10X Genomics. This device uses a precise application of chemical and photic prods to measure individual cellular expression in situ[^Xenium]. It is at this level of detail that we shall listen to hear the difference in rhetoric between RGC that survive and repair themselves and RGC that give up. And where *we* can't find the common motifs, we expect artificial ears to keep focus until they can explain it to us. These ears include deep learning tools such as treeArches[^treearches] and tangram[^tangram] that can process these rich datasets. Characterizing expression of cells has come a long way. Though the specific path the reader is imagining might trace through single cell and bulk RNA-seq, its journey goes even further back than the Human Genome Project in the **19**90's.

> "...it seems probable that most of the grand underlying principles have been firmly established... It is here that the **science of measurement** shows its importance — where quantitative work is more to be desired than qualitative work. An eminent physicist remarked that the future truths of physical science are to be looked for in the sixth place of decimals."
> 
> Dr. Albert Michelson, 1896[^kelvin]

This is a quote from University of Chicago's head of physics in 1896. It is often misattributed to Lord Kelvin and jeered for its lack of divination. In the decade after this statement, more than a couple paradigm shifting discoveries occured: the anatomy of the atom (Thomson, 1897[^thomson] & Rutherford, 1911[^rutherford]), the transistor (Forest, 1906[^forest]) and the photoelectric effect (Einstein, 1905[^photoelectric]). But the precision of scientific work is what lead to these discoveries becoming useful. The precise manipulation of fissile nuclei to create a bomb, the miniaturization of controllable semiconductor gates to perform high-throughput data processing, and measuring the excitation of millions of photosensors for digital photography.

So yes, the first part of his statement is wrong. But the latter part of his statement is one that my lab can confidently endorse. But the field of biology in Dr. Michelson's 1896 was, in a sense, averse to such a suggestion. At that time, it still seemed as if the mechanisms of life were fundamentally different than the physics and chemistry of non-living matter. If that's the case, why and how would using the model for researching the inert benefit biologists?

This belief that life and non-life are fundamentally different and should be separated is old and limped into the 20th century where its influence on biology research died[^vitalism]. One of its pole-bearers was Dr. Karl Pearson. In Dr. Michelson's 1896, Pearson was working on his eponymous correlations and publishing his 18 part series called "Mathematical Contributions to the Theory of Evolution[^mathevolution]." Here he endorsed the importance of Dr. Michelson's "quantitative work" in moving the field of biology forward. He went on to established Biometrika in 1902. It was a journal devoted to statistics as a tool for biology research. A mere century later, we embrace this philosophy to its limits in bioinformatics, where we collect large biological datasets to detect the most subtle of patterns to make meaningful insights.

Where once we could feel only a flat surface, now we may read the braille that our cells are writing to us. In my career, I've experienced the progression from bulk RNA-seq to measure the average expression of cells in tissues to single cell RNA-seq to measure the expression of individual cells from a tissue. Now we take a step from the 5th to the 6th decimal place with our fully installed Xenium Analyzer. Its precise photography will allow us to measure individual transcripts within the cytoplasm of cells that are still attached to its neighbors in tissue. Whereas we before had to surmise what was happening inside a cell based on averages of disassociated cells, we are now able to pinpoint exactly what is happening in situ at a single moment in time.

In our lab, we aim to translate this braille and elucidate the relationship between IOP, the health of RGCs and the vision loss in glaucoma. While the direction of these correlations are clear, the mechanisms that translate one to the other are not. But the eye is just another physical system. It's a complex and subtle system, but the closer we look the clearer the answer shall become until we find the link(s) between these phenomena. And once we know that connection, all that's left is finding the best scissors for severing it.

## References

[^converseAI]: Biever, C. Jul 2023. "ChatGPT broke the Turing test - the race is on for new ways to assess AI". Nature News. https://www.nature.com/articles/d41586-023-02361-7 

[^attention]: Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, and Illia Polosukhin. 2017. "Attention is all you need". In Proceedings of the 31st International Conference on Neural Information Processing Systems (NIPS'17). Curran Associates Inc., Red Hook, NY, USA, 6000–6010.

[^RGC_degen]: Tian, F., **Cheng, Y.**, et al. Aug 2022. "Core transcription programs controlling injury-induced neurodegeneration of retinal ganglion cells." Neuron 110(16) 2607-2624.e8. https://doi.org/10.1016/j.neuron.2022.06.003. https://www.sciencedirect.com/science/article/pii/S0896627322005414

[^Xenium]: Janesick, A., Shelansky, R., Gottscho, A.D. et al. High resolution mapping of the tumor microenvironment using integrated single-cell, spatial and in situ analysis. Nat Commun 14, 8353 (2023). https://doi.org/10.1038/s41467-023-43458-x

[^tangram]: Biancalani, T., Scalia, G., Buffoni, L. et al. Deep learning and alignment of spatially resolved single-cell transcriptomes with Tangram. Nat Methods 18, 1352–1362 (2021). https://doi.org/10.1038/s41592-021-01264-7

[^treearches]:  Michielsen, L., et al. Single-cell reference mapping to construct and extend cell-type hierarchies, NAR Genomics and Bioinformatics, Volume 5, Issue 3, September 2023, lqad070, https://doi.org/10.1093/nargab/lqad070

[^kelvin]: Michelson, A. "Introduction to Chapter XIX. The Department of Physics." In  University of Chicago (1896), "Annual Register" (pp. 159-160). [Link](https://books.google.com/books?id=HysXAAAAYAAJ&pg=PA159#v=onepage&q&f=false)

[^thomson]: J. J. Thomson M.A.F.R.S. (1897): XL. "Cathode Rays", Magazine Series 5, 44:269, 293-316

[^rutherford]: Rutherford, E. (1911) 'LXXIX. The scattering of α and β particles by matter and the structure of the atom', Philosophical Magazine Series 6, 21: 125, 669 — 688

[^forest]: L. De Forest, "The Audion: A new receiver for wireless telegraphy," in Proceedings of the American Institute of Electrical Engineers, vol. 25, no. 10, pp. 719-747, Oct. 1906, doi: 10.1109/PAIEE.1906.6741775.

[^photelectric]: Einstein, A. (1905) On a Heuristic Viewpoint Concerning the Production and Transformation of Light. Annalen der Physik, 17, 132-148. 

[^vitalism]: Ernst Mayr "What is the meaning of life". In Mark A. Bedau & Carol E. Cleland (2010), "The Nature of Life: Classical and Contemporary Perspectives from Philosophy" (Chapt 6).

[^mathevolution]: Pearson Karl (1896) "VII. Mathematical contributions to the theory of evolution.—III. Regression, heredity, and panmixia". Philosophical Transactions of the Royal Society of London. Series A, Containing Papers of a Mathematical or Physical Character 187: 253–318 http://doi.org/10.1098/rsta.1896.0007