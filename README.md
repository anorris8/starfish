<img
  src="/assets/STARFISH_LOGO.png"
  align = "center"
  style="margin: 20 auto; width: 567px; height: 210px">

<img
  src="/assets/element_logo_color.png"
  align = "right"
  style="margin: 0 auto; width: 182px; height: 200px">

TESTING

[![DOI](https://zenodo.org/badge/581059656.svg)](https://zenodo.org/badge/latestdoi/581059656) [![Anaconda_version](https://anaconda.org/egluckthaler/starfish/badges/version.svg
)](https://anaconda.org/egluckthaler/starfish) [![Anaconda_downloads](https://anaconda.org/egluckthaler/starfish/badges/downloads.svg)](https://anaconda.org/egluckthaler/starfish) [![Anaconda_platforms](https://anaconda.org/egluckthaler/starfish/badges/platforms.svg
)](https://anaconda.org/egluckthaler/starfish) [![Anaconda-Server Badge](https://anaconda.org/egluckthaler/starfish/badges/latest_release_date.svg)](https://anaconda.org/egluckthaler/starfish)


```starfish``` is a modular toolkit for giant mobile element annotation. Built primarily for annotating [*Starship* elements](https://academic.oup.com/mbe/article/39/5/msac109/6588634) in fungal genomes, it can be easily adapted to find any large mobile element (≥6kb) that shares the same basic architecture as a fungal *Starship* or a bacterial integrative and conjugative element: a "captain" gene with zero or more "cargo" genes downstream of its 3' end. It is particularly well suited for annotating low-copy number elements in a content independent manner.

## Overview

The ```starfish``` workflow is organized into three main modules: Gene Finder, Element Finder, and Region Finder. Each has dedicated commands that are typically run sequentially. Auxiliary commands that provide additional utilities and generate visualizations are also available through the commandline. Several useful stand-alone scripts are located in the `/scripts` directory. 

<img
  src="/assets/starfishWorkflow.png"
  style="display: center; margin: 0 auto; max-width: 400px">

## Quick install with conda

```
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --set channel_priority strict
conda create -c egluckthaler -n starfish python=3.8 starfish
conda activate starfish
```

## Documentation

Head to our [GitHub Wiki](https://github.com/egluckthaler/starfish/wiki) for more [installation options](https://github.com/egluckthaler/starfish/wiki/Installation), a [manual](https://github.com/egluckthaler/starfish/wiki/Manual) with important details and considerations for each command, and a [step-by-step tutorial](https://github.com/egluckthaler/starfish/wiki/Step-by-step-tutorial). If you run into difficulties, please open an issue on [GitHub](https://github.com/egluckthaler/starfish/issues)

## Citation and license

Please cite our work if you use ```starfish``` in your research:

[*Gluck-Thaler, E., & Vogan, A. A. (2024). Systematic identification of cargo-carrying genetic elements reveals new dimensions of eukaryotic diversity. Nucleic Acids Research, 2024-06.*](https://academic.oup.com/nar/article/52/10/5496/7660083)

Many ```starfish``` commands have dependencies that are stand-alone programs in their own right. Please cite both the ```starfish``` manuscript in addition to any dependencies you may have used (see Table below for a guide). For example:
> We used starfish v1.0.0 (Gluck-Thaler and Vogan 2024) in conjunction with metaeuk (Karin et al. 2020), mummer4 (Marcais et al 2018), and blastn (Camacho et al. 2009) to annotate and visualize *Starship* elements.

| Command | Dependency | Citation |
|:---:|:---:|:---|
|`annotate`, `augment`| `metaeuk`, `hmmer`, `bedtools` | [Karin et al. 2020](https://pubmed.ncbi.nlm.nih.gov/32245390/), [Eddy 2011](https://pubmed.ncbi.nlm.nih.gov/22039361/), [Quinlan and Hall 2010](https://pubmed.ncbi.nlm.nih.gov/20110278/) |
|`insert`, `extend`| `blastn`, `mummer4` | [Camacho et al. 2009](https://pubmed.ncbi.nlm.nih.gov/20003500/), [Marcais et al 2018](https://pubmed.ncbi.nlm.nih.gov/29373581/) |
|`flank`| `cnef` | [Ayad et al. 2018](https://pubmed.ncbi.nlm.nih.gov/30423090/) |
|`sim`| `sourmash` | [Pierce et al 2019](https://pubmed.ncbi.nlm.nih.gov/31508216/) |
|`group`| `mcl` | [Enright et al. 2002](https://pubmed.ncbi.nlm.nih.gov/11917018/) |
|`*-viz`|`circos`, `gggenomes`, `mummer4`, <br />`mafft`, `minimap2`| [Krzywinski et al. 2009](https://pubmed.ncbi.nlm.nih.gov/19541911/), [Hackl and Ankenbrand 2022](https://thackl.github.io/gggenomes/authors.html), [Marcais et al 2018](https://pubmed.ncbi.nlm.nih.gov/29373581/), <br />[Katoh and Standley](https://pubmed.ncbi.nlm.nih.gov/23329690/), [Li 2018](https://pubmed.ncbi.nlm.nih.gov/29750242/)|

```starfish``` is an open source tool available under the GNU Affero General Public License version 3.0 or greater. This work was supported by funding from the European Union’s Horizon 2020 research and innovation programme under the Marie Skłodowska-Curie grant agreement (grant number 890630).
