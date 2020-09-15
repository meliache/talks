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

What can we do with ICHEP 2020 dataset of \text{\SI{30.6}{\per\femto\barn}}?

# ICHEP 2020 results #

::: block
## ICHEP analysis idea: ##
First Belle II branching fraction measurement of the hadronically tagged \bdslnu mode.
:::

- Result is not expected to be competitive, but more a validation of the overall Belle II data, the software
reconstruction and the analysis strategy.
- important stepping stone
- in the following I'll show someresults from:
    - [BELLE2-CONF-PH-2020-023](https://docs.belle2.org/record/2002?),
      [arXiv:2008.07198](https://arxiv.org/abs/2008.07198)  (conference note)
    - [BELLE2-NOTE-PH-2020-009](https://docs.belle2.org/record/1928) (internal support note)
    
    (Tip: If you have missed it, check out Florians [summer
    results](https://indico.belle2.org/event/2751/contributions/13084/attachments/7169/11117/Talk.pdf))
    overview)
    
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
:::: {.column width="62%" align=center}
\center
- Reconstructed decay modes:

    $D^0$ decay mode                 Branching ratio (%)
    ------------                  ----------------------
    $K^+\pi^-$                        \num{3.950+-0.031}
    $K^-\pi^+\pi^0$                     \num{14.4+-0.5}
    $K^-\pi^+\pi^-\pi^+$                \num{8.23+-0.14}

- saw MC-data descrepancies in $K^-\pi^+\pi^0$ and $K^-\pi^+\pi^-\pi^+$:

- for the ICHEP results thus **used only Kπ mode**
::::
:::: {.column width="38%" align=center}
\center
![](figures/decay_mode_descrepancies.png){width=100%}
::::
:::


# FEI Skims #
::: {.columns .onlytextwidth}
:::: {.column width="50%" align=center}
- used FEI $\PBzero_{\rm tag}$ skims 
  <!-- with training `FEIv4_2020_MC13_release_04_01_01` with `release-04-02-08` -->
  with recommendations from physics performance group
  - at least one FEI candidate
  - $M_{\rm bc} > 5.27$
  - $\Delta E \in [-0.15, 0.1]\,\si{\GeV}$
  - $\mathrm{FEI\ signal\ prob.} > 0.001$
::::
:::: {.column width="50%" align=center}
\center
![](Btag_Mbc.png) 
::::
:::

  
- Applied FEI tagging efficiency and PID corrections to all following plots

# D reconstruction #


- standard track cuts: $|d_0| < \SI{0.5}{\cm}$ and $z_0 < \SI{2}{\cm}$
- $N_{\rm CDC\ Hits} > 0$ for all except slow $\pi$'s
- $p^*_{\PD} < \SI{3}{\GeVperc}$
- invariant mass cuts
    - $M_{\PD} := M_{\PK\pi} \in [1.858, 1.878]\,\si{\GeVpercc}$
    - $\Delta M := M_{\PDstar} - M_{\PD} / \in [0.143, 0.148]\,\si{\GeVpercc}\quad (\sim 3 \sigma)$
\center
![](D_reconstruction.png){width=80%}


# Lepton reconstruction #

::: {.columns .onlytextwidth}
:::: {.column width="40%" align=center}
- standard track cuts:  
  $|d_0| < \SI{0.5}{\cm}$ and $|z_0| < \SI{2}{\cm}$
- $\mathrm{lepton\ PID} > 0.9$
- $p^*_\ell > \SI{1}{\GeVperc}$
::::
:::: {.column width="60%" align=center}
\center
![](lep_p_cms.png)
::::
:::



# $\Upsilon(4S)$ Reconstruction
::: {.columns .onlytextwidth}
:::: {.column width="40%" align=center}
- combine reconstructed $\PB_{\rm sig}$ with $\PB_{\rm tag}$
- further cuts:
    - $N_{\rm ROE\ tracks} = 0$
    - $E_{\rm miss} > \SI{0.3}{\GeV}$
::::
:::: {.column width="60%" align=center}
\center
![](figures/Postfit_MM2.pdf)
::::
:::

# Fitting procedure #

- binned extended maximum likelihood fit:  
  approximate PDF of different processes with MC "histograms"
- Likelihood is product of \textcolor{blue}{poissons} with expectation $\nu_i$:

  $$\mathcal{L} =  \prod_i^{\rm bins} \, \textcolor{blue}{\mathcal{P}\left( n_i ; \nu_i \right)}
  \times
  \prod^{\rm processes}_k \, \textcolor{green}{\mathcal{G}_k}\, ,
  \quad
  \nu_i = \sum_k^{\mathrm{processes}} f_{ik}\eta_k$$
  
  with $\eta_k$ the total number of events in process $k$ and $f_{ik}$ its fraction of events in bin $i$,
  given by:
  $f_{ik} = \frac{ \eta_{ik}^{\rm MC} \left( 1 + \textcolor{red}{\theta_{ik}} \right) }{ \sum_j \eta_{jk}^{\rm MC} \left( 1 +
  \textcolor{red}{\theta_{jk}} \right)  }$
- incorporate shape uncertainty from MC statistics via \textcolor{green}{constrained} \textcolor{red}{nuisance parameters}
- fit two components: (\PDstar signal, combined background)
- use [`binfit`](https://stash.desy.de/users/sutclw/repos/binfit/), a fork by W. Sutcliff of Max Welsch's [`TemplateFitter`](https://github.com/welschma/TemplateFitter)



# $m_{\rm miss}^2$ fit result #

\center
![](figures/Postfit_MM2.pdf){width=60%}

::: {.columns .onlytextwidth}
:::: {.column width="35%" align=center}
\center
- $N_{\rm sig} = \num{133+-12}$
- $N_{\rm bkg} = \num{12+-5}$
::::
:::: {.column width="65%" align=center}
\center
![](figures/MM2_nuisance_pulls_lep=all.pdf){width=94%}
::::
:::


# Branching fraction extraction#

::: {.columns .onlytextwidth}
:::: {.column width="50%" align=center}

\center
- $N_{B\bar{B}} = (37.73 \pm 0.05) \times 10^6$
- $f_{+0} = 1.058$
<!-- - $N_{\rm sig} = 133 \pm 12$ -->
- $\epsilon = 0.403 \times 10^{-4}$  
  (from signal and generic MC)

::::
:::: {.column width="50%" align=center}
\center
Sources of uncertainty
\tiny
\begin{tabular}{l|c}\toprule
  Source & Relative uncertainty (\%) \\
  \midrule
  Tracking of $\pi$s & 10\%  \\
  MC modeling & 5\%\\
  FEI Calibration & 3\% \\
  Tracking of $K$, $\pi$, $\ell$ & 3\%  \\
  $N_{B^0}$ & 2\% \\
  $f_{+0}$ & 1\% \\
  Charm branching fractions & 1\% \\
  Lepton ID & 1\%\\
  \hline
  Total & 12\% \\
  \bottomrule
\end{tabular}
::::
:::

$$
\BR(\bdslnu)=  \frac{
    N_{\rm sig} \times \epsilon^{-1}_{\mathrm{tag+sel}}
    } {
    4 \times N_{\PB\APB} \times \left( 1 + f_{+0}\right)^{-1} }
$$

# Braching fraction result

## Branching fraction
\resBF

- lower than world average but in agreement



# Other results: BDT for ECL beam backround suppression #

- data-based training via low-multiplicity  $e^+e^- \rightarrow \mu^+\mu^-$
- train BDT against beam background clusters based on shape and location of clusters  
  <!-- (`clusterTheta`, `clusterPhi`, `E1E9`, `clusterLAT`, `clusterZernikeMVA`, `clusterSecondMoment`) -->
- improved $E_{\rm ECL}$ distribution allows better signal/background separation

::: {.columns .onlytextwidth}
:::: {.column width="50%" align=center}
\center
before BDT
![](figures/ROE_neextraBefore.pdf){width=90%}
::::
:::: {.column width="50%" align=center}
\center
after cut on BDT output
![](figures/ROE_neextraAfter.pdf){width=90%}
::::
:::


# Next steps #

<!-- TODO work on this -->
- improved slow pion systematics
- understand data and discrepancies in other \PDzero and fix them
- cross-checks
- kinematic distributions
- go differential


# Thanks {.standout}

\huge Thanks for listening!


# Backup #

\appendixworkaround

# Pre- and post-fit plots side by side #
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
<!-- Compile with: pandoc talk.md --pdf-engine xelatex --to beamer -o talk.pdf -->
