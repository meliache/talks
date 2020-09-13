---
aspectration: 169
fontsize: 16pt
include-after:
header-includes:
    - \let\mathup\relax
    - \let\mathsfup\relax
    - \let\mathsfit\relax
    - \usepackage[utf8]{inputenc}
    - \usepackage[italic]{hepnames, hepparticles}
    - \usepackage{templates/metropolisbonn}
    - \hypersetup{colorlinks, urlcolor=bonnblue}
    - \lstset{keywordstyle=\bfseries\color{bonnblue}, commentstyle=\itshape\color{bonnunigrau}, identifierstyle=\color{bonntextgrau}, stringstyle=\color{bonnyellow}}
    - \newcommand{\PDmstar}{\HepParticle{D}{}{\left(*\right)}}
    - \newcommand{\rdstar}{R\left(\PDmstar\right)}
    - \newcommand{\dstardec}{\HepProcess{\PB \to \PDmstar \ell \nu}}
    - \newcommand{\Br}{\mathcal{B}}
author: Michael Eliachevitch ([meliache@uni-bonn.de](mailto:meliache@uni-bonn.de))
title: Status of tagged \dstardec 
subtitle: Belle II Germany Meeting (FSP) 2020
date: \today
institute: Physikalisches Institut --- Rheinische Friedrich-Wilhelms-Universität Bonn
---

# Why study  \dstardec ? #

- semi-leptonic tree level decays → clean theory prediction 
- high branching fraction of $\HepProcess{b \to c}$  
  → we can sacrificy some efficiency for purity
- probe *new physics* couplings heavy flavour: \Pbottom, $\tau$

- famous observable:  
  $\rdstar = \frac{
  \Br\left(\HepProcess{\PB \to \PDmstar \tau \nu_{\tau}}\right)
  }{
  \Br\left(\HepProcess{\PB \to \PDmstar \ell \nu_{\ell}}\right)
  }
  \quad ,\ \ell \in \{\Pelectron, \mu\}$ 
  
  <!-- image of decay -->

# Current results –- the anomaly

\center
![](figures/hflav_rdrds_spring2019_cut.pdf){width=80%}

- 3--4 $\sigma$ tension between SM prediction and world average
- Moriond 2019 results closer to SM prediction
- current results inconclusive → need new LHCb and Belle II results!

# Analysis Strategy #

- use hadronic tagging with *Full Event Interpretation* (FEI) 
- knowledge of tag-side four-momentum:
  $p_{\Upsilon(4S)} = p_{B_{\rm tag}} + p_{B_{\rm sig}} + p_{\rm miss}$
- $\Rightarrow m_{\rm miss}^2 = p_{\rm miss}^2 =
  \left(p_{\Upsilon(4S)} - p_{B_{\rm tag}} - p_{\PDmstar} - p_{\tau,\ell}\right)^2$
- fit: separates signal ($\PDmstar\tau\nu_{\tau}$) from normalization ($\PDmstar\ell\nu_{\ell}$) 
 

# ICHEP results: Use available data for BF measurement #
   
# Reconstruction #

# Signal selection #

# Decay channels #

# Fit #

::: {.columns .onlytextwidth}  
:::: {.column width="50%" align=center}  
\center
Pre-fit
![](figures/Prefit_MM2.pdf)
::::  
:::: {.column width="50%" align=center}  
\center
Post-fit
![](figures/Postfit_MM2.pdf)
::::  
:::

# BF result #

# Plans #

Backup
======

```{=latex}
\appendix
```


<!-- Compile with: pandoc talk.md --pdf-engine xelatex --to beamer -o talk.pdf -->
