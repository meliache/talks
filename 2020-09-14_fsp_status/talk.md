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
    - \newcommand{\appendixworkaround}{\end{frame} \appendix \begin{frame}<0| handout:0>}
    - \DeclareSIUnit\clight{c}
    - \DeclareSIUnit\GeVperc{\GeV\per\clight}
    - \DeclareSIUnit\GeVpercc{\GeV\per\clight\squared}
 
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

# Analysis Strategy: Hadronic Tagging with Full Event Interpretation #

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

# We're on our way #

\center
![](figures/luminosity_2020-09-14.png){width=80%}

What can we do with ICHEP2020 dataset of \text{\SI{30.6}{\per\femto\barn}}?

# ICHEP 2020 results #

::: block
## ICHEP analysis idea: ##
First Belle II branching fraction measurement of the hadronically tagged \bdslnu mode.
:::

- Result is not expected to be competitive, but more a validation of the overall Belle II data, the software
reconstruction and the analysis strategy.
- important stepping stone
- in the following I present the ICHEP results from:
    - [BELLE2-CONF-PH-2020-023](https://docs.belle2.org/record/2002?),
      [arXiv:2008.07198](https://arxiv.org/abs/2008.07198)  (conference note)
    - [BELLE2-NOTE-PH-2020-009](https://docs.belle2.org/record/1928) (internal support note)

# Data used #

- **Measured data:** $\int \mathcal{L} \mathrm{d}t = \SI{36.6}{\per\femto\barn}$  
  full ICHEP2020 dataset of Proc~11 and Buckets~9--11  

- **Simulated MC data:** $\int \mathcal{L} \mathrm{d}t = \SI{100}{\per\femto\barn}$
    - 40 million events of generic **run-independent MC13a**
    - including ${\PBzero}{\APBzero}$, ${\PBplus}{\PBminus}$, and continuum MC
    - further generated \bdslnu signal MC to for reconstructrion efficiency calculation

::: block
## MC-matching signal definition ##

- generator-level requirement that event was \bdslnu
- require that signal lepton is correctly matched and daughter of the signal B
  (currently identified via PDG code comparison)
- allow wrong reconstruction of \PDmstar
:::

# Decay modes #

::: {.columns .onlytextwidth}
:::: {.column width="65%" align=center}
\center
- Reconstructed decay modes:

    Decay Mode                      Branching ration (%)
    ------------                  ----------------------
    $K^+\pi^-$                        \num{3.950+-0.031}
    $K^-\pi^+\pi^0$                     \num{14.4+-0.5}
    $K^-\pi^+\pi^-\pi^+$                \num{8.23+-0.14}

- saw MC-data descrepancies in $K^-\pi^+\pi^0$ and $K^-\pi^+\pi^-\pi^+$:

- for the ICHEP results thus **only used $K^+\pi^-$**
::::
:::: {.column width="35%" align=center}
\center
![](figures/decay_mode_descrepancies.png){width=100%}
::::
:::


# FEI Skims #

- used FEI $\PBzero_{\rm tag}$ skims with training
  `FEIv4_2020_MC13_release_04_01_01` with `release-04-02-08` with recommendations from physics performance group
  - at least one FEI candidate
  - $M_{\rm bc} > 5.27$
  - $\Delta E \in [-0.15, 0.1]\,\si{\GeV}$
  - $\mathrm{FEI\ signal\ probability} > 0.001$

# Reconstruction #

## D reconstruction ##

- standard track cuts: $|d_0| < \SI{0.5}{\cm}$ and $z_0 < \SI{2}{\cm}$
- $N_{\rm CDC\ Hits} > 0$ for all except slow $\pi$'s
- $M_{\PD} := M_{\PK\pi} \in [1.858, 1.878]\,\si{\GeVpercc}$
- $p^*_{\PD} < \SI{3}{\GeVperc}$
- $\left(M_{\PDstar} - M_{\PD}\right) / \in [0.143, 0.148]\,\si{\GeVpercc}\quad (\sim 3 \sigma)$

::: block
## Lepton reconstruction ##
- standard track cuts: $|d_0| < 0.5$ cm  and $z_0 < 2$ cm
- $\mathrm{lepton\ PID} > 0.9$
- $p^*_\ell > \SI{1}{\GeVperc}$
:::

- $E_{\rm miss} > \SI{0.3}{\GeV}$


# Fit results #

- binned extended maximum likelihood fit with two components (\PDstar signal, backgrounds)
- fit incorporates the shape uncertainty from the limited size of the used MC templates (~ negligible)

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

# Branching fraction#

::: {.columns .onlytextwidth}
:::: {.column width="50%" align=center}

\center
- $N_{B\bar{B}} = (37.73 \pm 0.05) \times 10^6$
- $f_{+0} = 1.058$
- $N_{\rm sig} = 133 \pm 12$
- $\epsilon = 0.403 \times 10^{-4}$

::::
:::: {.column width="50%" align=center}
\center
![](figures/bf_uncertainties.png){width=100%}
::::
:::

$$
\BR(\bdslnu)=  \frac{
    N_s \times \epsilon^{-1}_{\mathrm{tag+sel}}
    } {
    4 \times N_{\PB\APB} \times \left( 1 + f_{+0}\right)^{-1} }
$$

## Result
\resBF

# Other results: BDT for ECL beam backround suppression #

- data-based training via low multiplicity  $e^+e^- \rightarrow \mu^+\mu^-$
- train BDT against beam backgrounds based on cluster shape variables: `clusterTheta`, `clusterPhi`, `E1E9`, `clusterLAT`, `clusterZernikeMVA`, `clusterSecondMoment`

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

- understand channels and include both again
- study other cuts (e.g. $p_\ell$)
- measure more than just branching fraction
- validate and understand what we are doing

\appendixworkaround




<!-- Compile with: pandoc talk.md --pdf-engine xelatex --to beamer -o talk.pdf -->
