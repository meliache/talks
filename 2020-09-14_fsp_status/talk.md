---
aspectration: 169
fontsize: 16pt
lang: en
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
    - \newcommand{\bdslnu}{\HepProcess{\PB \to \PDmstar \ell \nu}}
    - \newcommand{\BR}{{\ensuremath{\cal B}}}
    - \newcommand{\resBF}{\ensuremath{\BR(\bdslnu) = \left(4.51 \pm 0.41_{\mathrm{stat}}\pm0.27_{\mathrm{syst}} \pm 0.45_{\pi_s}\right) \%}\xspace}
author: Kyle Amirie, Florian Bernlochner, Racha Cheaib, [Michael Eliachevitch](mailto:meliache@uni-bonn.de), Max Graf, William Sutcliffe, Hannah Wakeling

title: Status of tagged \bdslnu
subtitle: Belle II Germany Meeting (FSP) 2020
date: \today
institute: Physikalisches Institut --- Rheinische Friedrich-Wilhelms-Universität Bonn
---

# Why study  \bdslnu ? #

\center
![](figures/b_to_q_diagram_bernlochner.pdf){width=50%}
<!-- First order $b\rightarrow q$ diagram. Taken from Floran Bernlochner -->

- semi-leptonic tree level decays → clean theory prediction
- high branching fraction of $\HepProcess{b \to c}$  
  → we can sacrificy some efficiency for purity
- probe *new physics* couplings heavy flavour: \Pbottom, $\tau$

- famous observable:
  $\rdstar = \frac{
  \BR\left(\HepProcess{\PB \to \PDmstar \tau \nu_{\tau}}\right)
  }{
  \BR\left(\HepProcess{\PB \to \PDmstar \ell \nu_{\ell}}\right)
  }
  \quad ,\ \ell \in \{\Pelectron, \mu\}$


# Current world average –- the anomaly #

\center
![](figures/hflav_rdrds_spring2019_cut.pdf){width=80%}

- 3--4 $\sigma$ tension between SM prediction and world average
- Moriond 2019 results closer to SM prediction
- current results inconclusive → need new LHCb and Belle II results!

# Analysis Strategy: Hadronic Tagging with Full Event Interpretation#

\center
![](figures/tag_efficiency_vs_purity.pdf){width=25%}
![](figures/hadronic_tag_bdslnu_decay_sketch.pdf ){width=35%}

- fully reconstruct tag side with *Full Event Interpretation* (FEI)
- exclusive signal-side reconstruction of \PDmstar
- knowledge of tag-side four-momentum (no tag-side neutrinos)  
  $\Rightarrow p_{\Upsilon(4S)} = p_{B_{\rm tag}} + p_{B_{\rm sig}} + p_{\rm miss}$
- Allows to separate signal and background with fit to
  $$m_{\rm miss}^2 = \left(p_{\Upsilon(4S)} - p_{B_{\rm tag}} - p_{\PDmstar} - p_{\tau,\ell}\right)^2$$
  - $= m_\nu^2 \approx 0$ for normalization channel
  - $> 0$ for signal side because of invariant mass of three neutrinos
  
# ICHEP 2020 results#

    
- What can we do with ICHEP2020 dataset of \text{\SI{30.6}{\per\femto\barn}}?

::: block
## ICHEP analysis idea:
First Belle II branching fraction measurement of the hadronically tagged \bdslnu mode.
:::

- Result is not expected to be competitive, but more a validation of the overall Belle II data, the software
reconstruction and the analysis strategy.
- important stepping stone
- in the following I present the ICHEP results from: 
    - [BELLE2-CONF-PH-2020-023](https://docs.belle2.org/record/2002?),
      [arXiv:2008.07198](https://arxiv.org/abs/2008.07198)  (conference note)
    - [BELLE2-NOTE-PH-2020-009](https://docs.belle2.org/record/1928) (internal support note)

# Data used#

- **Measured data:** $\int \mathcal{L} \mathrm{d}t = \SI{36.6}{\per\femto\barn}$  
  full ICHEP2020 dataset of Proc~11 and Buckets~9--11  

- **Simulated MC data:** $\int \mathcal{L} \mathrm{d}t = \SI{100}{\per\femto\barn}$
    - 40 million events of generic **run-independent MC13a**
    - including ${\PBzero}{\APBzero}$, ${\PBplus}{\PBminus}$, and continuum MC 
    - further generated \bdslnu signal MC to for reconstructrion efficiency calculation

::: block
## MC-matching signal definition

- generator-level requirement that event was \bdslnu
- require that signal lepton is correctly matched and daughter of the signal B
  (currently identified via PDG code comparison)
- allow wrong reconstruction of \PDmstar 

:::



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

# Branching fraction extraction #

$$
\BR(\bdslnu)=  \frac{
    N_s \times \epsilon^{-1}_{\mathrm{tag+sel}}
    } {
    4 \times N_{\PB\APB} \times \left( 1 + f_{+0}\right)^{-1} }
$$

# Resulting branching fraction #

## Measured branching fraction ##

\resBF

# Other results #

- data-based training of a BDT to suppress ECL background clusters

::: {.columns .onlytextwidth}
:::: {.column width="50%" align=center}
\center
before BDT
![](figures/ROE_neextraBefore.pdf)
::::
:::: {.column width="50%" align=center}
\center
after cut on BDT output
![](figures/ROE_neextraAfter.pdf)
::::
:::


# Outlook #




<!-- Compile with: pandoc talk.md --pdf-engine xelatex --to beamer -o talk.pdf -->
