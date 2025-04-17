---
title: "Variability Mechanisms"
author: "Daniel Gotthardt, Christoph Naefgen & Anne Reinarz"
date: "`r Sys.Date()`"
output: bookdown::html_document2
citation_package: biblatex
bibliography: variability.bib
biblio-style: apa
link-citations: yes
---

```{r setup, include=FALSE}

# Clean up workspace -------------------------------------
rm(list=ls(all.names = TRUE))
gc()

library(here)

```

# Attractors and repulsors: Homogenization and polarization

Any process operating on $Y$ that induces an ideal point or particularly attractive range of values can lead to concentration around that value, that is homogenization [@ostroff.fulmer_2014]. Depending on the starting position, the induced change in $Y$ can be positive or negative and stronger the further away the starting value is from the attractor (Figure \@ref(fig:visual-attract-repulse)a). An attractor can be an optimal value in $Y$ under some condition $X$ or it can only be perceived or processed as optimal if $X$ is increasing. Depending on where the ideal is positioned relative to the starting distribution, the process can take different shapes, and the specific expected form of a conditional decrease in variability within the group might vary, for example an attractor at the border of the starting range of values will cause strong changes on the lower quantiles of a distribution but nearly none on higher quantiles (Figure \@ref(fig:visual-attract-repulse)b).

```{r visual-attract-repulse, fig.cap ="Changes in variability through attractors and repulsors", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA1.png"))
```
*Note*. Theorized individual change trajectories given (a) an attractor at the center of the distribution, (b) an attractor at the higher end of the distribution, (c) a repulsor at the center of the distribution, or (d) a repulsor at the lower end of a distribution with a floor.

Many group processes, be they explicitly coercive or directly influenced by other group members, or the normative pressure of average or authoritative perspectives, can lead to homogenization within the group due to attractors [@lang.etal_2018] Similarly, the creation of an identity and activating that identity can lead to pressure to react, think, believe, and behave similarly to others in the group or the group ideal. Also, it might matter whether (1) the ideal norm is static, (2) its change is not observed, or (3) the normative value follows additional dynamic processes [@baurne.etal_2022].

Nonetheless, we can descriptively expect a conditional decrease in variability: The more people are embedded in the group or the more strongly the identity is activated, the less variability there is. For example, an individual’s perception of the degree of their own religiousness could correspond to the strength with which the individual is pushed to conform to group norms, with more religiousness corresponding to more pressure.

While this can be a kind of conscious optimization process, this can also be more a functional theory of systemic behavior, even if the underlying mechanisms might be based on social or neural networks (either literal neurons or cognitive processes with a neural network structure) diffusion processes. If we have concrete mechanical models of the homogenization process, we might be able to derive clearer predictions of the changes in variability.

The opposite of an attractor is a repulsor, a point or range of values in $Y$ that is particularly unattractive. If people are incentivized to avoid a specific kind of behavior, they might not change their own behavior at all if they perceive it to be very dissimilar from the disincentivized one, and react strongly if they perceive it to be similar. If changes can only go in one direction, this might lead to a reduction in variability due to asymmetric changes in the distribution (Figure \@ref(fig:visual-attract-repulse)d). This is sometimes nearly indistinguishable from the effect of an attractor on the other side of the starting distribution (Figure \@ref(fig:visual-attract-repulse)b). Suppose the repulsor is close to the median of the starting distribution of values. In that case, we can expect an increase in variability and polarization, if changes in a positive and a negative direction are possible (Figure \@ref(fig:visual-attract-repulse)c). Polarization in this form would not only imply an increased variability but also a tendency towards bimodality. This is especially the case in combination with hardening dynamics, as @baumgaertner.etal_2016 show. This can be understood as a combination of a global repulsor and multiple local attractors.
Figure \@ref(fig:dens-attract-repulse) shows which differences in distributions these four processes would induce in contrast to a control group. A simple simulation allows us to add some additional measurement errors.

```{r dens-attract-repulse, fig.cap ="Simulated densities for the four attraction (a, b) and repulsion (c,d) mechanisms", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA2.jpeg"))
```
*Note*. Based on 5000 simulation runs. QR estimates are based on the difference in regression coefficients for the second and third quartiles. Extreme outliers for the two-step estimator are excluded from the plot.

Specifying and implementing the mechanisms and simulating the data generation processes makes it easy to derive the hypotheses to be tested: 

(a) $V(Y|X=1) < V(Y|X = 0) \text{ & } E(Y|X=1) = E(Y|X = 0)$

(b) $V(Y|X=1) < V(Y|X = 0) \text{ & } E(Y|X=1) > E(Y|X = 0)$

(c) $V(Y|X=1) > V(Y|X = 0) \text{ & } E(Y|X=1) = E(Y|X = 0)$

(d) $V(Y|X=1) < V(Y|X = 0) \text{ & } E(Y|X=1) > E(Y|X = 0)$


In fact, we can make additional predictions: We expect a higher degree of bimodality if we have a repulsor at the center of the distribution (c) and we expect a strong increase in the lower quantiles while the upper quantiles only slightly increase if we have a repulsor at the lower end of a truncated distribution (d) as the cause of the decreased overall variance.

Of course, if these processes are observable, e.g., if we believe the increased interaction in a cohesive group induces similarity, the theorized influence process can also be tested directly. We could also design an experiment where at least the starting distribution is observed and test how the change in $Y$ depends on the starting values in $Y$. Still, analyzing the within-treatment variability can be a test of the plausibility of these assumptions before more expensive data collection is considered necessary.

# Enabling and constraining: Conditions that are necessary, sufficient, or both

This section is about the influence of a dichotomous factor on some other variable. As such, it is especially easy to apply this logic to experimental contexts, but its scope is, in principle, broader than that. If we assume that some factor is (1) involved in a process that leads to a change in a variable and (2) that this factor can be either present or absent, then the relationship can be specified in several ways that we may recognize from introductory research logic courses. The factor’s presence can be a condition for change that is necessary, sufficient, both, or neither. 

If it is necessary, we know that the change process will not happen in the absence of the factor. If it is sufficient, we know that the change process will happen in the presence of the factor. If it is both, we know that the change process will always happen in the presence of the factor and never in its absence. If it is neither, the change process may happen regardless of the factor’s presence or absence. 

At its simplest and most direct, this means that the variability of the factor’s effect on the variable is dependent on the type of relationship (Figure \@ref(fig:visual-constrain-enable)). Of course, these rather strict categorizations rarely apply directly and simply to psychological mechanisms, so circumspection should be applied when using it. Overall, if these categories apply to the factor in question somewhere along the conceptual pathway and if there are no confounding factors, the claims about relative variance should apply.

```{r visual-constrain-enable, fig.cap ="Illustration of how the type of relationship (necessary, sufficient, both, or neither) corresponds to different variances", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA3.png"))
```
*Note*. Red crosses indicate that the factor A or changes in B do not occur. Each panel shows the potential combinations if the relationship is necessary, sufficient, both or neither.

A helpful alternative to theorizing directly about sufficient conditions is thinking about constraining factors that limit the range of potential expressions. If only one value is possible when a factor is present, then that factor is a sufficient condition. Conversely, more values are possible if the factor is absent. Because of this, variability will often be lower when the factor is present. An example of necessary conditions are resources that are needed to process social cues. These resources can be cognitive or social, but if they are necessary to change $Y$, their absence constrains $Y$. Conversely, their presence enables and thus potentially increases $Y$.

When we think of probabilistic extensions of necessary and sufficient conditions, it also becomes more obvious how they can be translated to mechanisms with continuous treatments (like dose-response relationships). The simulated data sets in Figure \@ref(fig:scatter-constrain-enable) include (small) random measurement noise, but most changes in the conditional variability are due to the asymmetric influence of $X$. If a higher $X$ enables changes in $Y$, $\Delta(Y)$ can become larger as $X$ increases, but it does not always increase as much as possible (Figure \@ref(fig:scatter-constrain-enable)a). Complementarily, a positively restricting continuous treatment will lower the minimum value of $\Delta(Y)$ (Figure \@ref(fig:scatter-constrain-enable)b). Only a restricting and enabling treatment will produce the homoscedastic relationship often assumed in standard statistical models (Figure \@ref(fig:scatter-constrain-enable)c).


```{r scatter-constrain-enable, fig.cap ="Simulated change in Y for continuous treatments (X) that are (a) enabling, (b) constraining, (c) enabling and constraining, or (d) ineffective", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA4.jpeg"))

```

Researchers should be aware that analyzing necessary conditions in this way only works if a sufficient condition is sometimes present. Or, as @braumoeller_2006 puts it, there must be enough reasons to warrant any changes in $Y$ for us to expect differences in variability under the necessary condition. The cause of changing impulses can be random, evolutionary dynamics, optimization strategies, or any of the attractors or repulsors discussed in the previous section. This could be seen as an indicator that an interactive model of necessary and sufficient conditions for the expectation would be a sensible solution [@clark.etal_2006]. However, @rosenberg.etal_2017 argue convincingly that this would not demonstrate enabling or constraining, as they predict changes in the range of potential values and not (just) of the expected averages under multiple conditions, and that we need models that can test the difference in limits like quantile regression.

# Truncating distributions

There are different measurement units commonly used in psychological theorizing and they can have different implications for predictions. If, for example, the unit of a mechanical influence is the strength of an association between two abstract representations of a concept, the value of that strength can range almost arbitrarily between the positive and the negative. If, however, the basic unit in a mechanism is a number of memory episodes in which multiple percepts are bound together [@logan_1988] and which can potentially be retrieved, then the range of values is constrained in two meaningful ways. First, the number needs to be a whole number, because, in this conceptualization, the association on the episode level would be represented by a binary value. Second, the number must be positive, because there cannot be less than zero memory episodes. To illustrate the usefulness of this, consider a scenario in which we want to test traits of some memory-related mechanisms underlying group-based prejudice (Figure \@ref(fig:visual-trunc)). 

```{r visual-trunc, fig.cap ="Illustration of two possible mechanisms of learning and retrieval of group-based prejudice.", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA5.png"))
```
*Note*. Both mechanisms describe a plausible causal path from encountering situations in which the social group is perceived in a negative context (e.g., direct encounters, opinions expressed by others, news reporting) to the perception of the social group leads to a negative reaction. Left column: A running tally of how positive or negative the social group is evaluated is updated when a relevant situation is encountered. The value of the tally is retrieved when group cues are encountered. Right column: Memory episodes in which both the negative context and the social group are bound together are formed and saved for each encounter. Each episode has a chance to be retrieved when group cues are encountered.

The theories we consider are centered around (1) mechanisms of abstract association or (2) mechanisms based on the retrieval of memory episodes where the number of potentially retrieved episodes matters. Both differentiate between the acquisition phase, in which the association is formed and the retrieval phase, in which the association is accessed and influences behavior. 

In the acquisition phase, each time the mental representation of the group identity is activated (e.g., by encounters with group members directly, via media representation, or through reactions modeled by others), learning happens. In (1), the strength of the association between the group and a positive evaluation is adjusted up- or downwards each time, resulting in a running value that ranges from the positive to the negative. In (2), for each activation of the group representation, a memory episode containing information about the event is formed and stored in memory.

In the retrieval phase, both theories assume that the activation of the representation of the group identity co-activates the learned memory contents in some way. In (1), there is a direct association between the abstracted representations of the group identity and a positive evaluation, with the group identity directly increasing or decreasing the amount of positive evaluation according to the previously acquired association. This means that perceiving the group identity can lead to any amount of positivity, including negative amounts. Effects that depend on this positivity, such as the cognitive processing efficiency of stimuli that feature traits that are congruent or incongruent to the association, should be able to take the same range of numerical values. In (2), on the other hand, the retrieval cue starts a process in which the retrieval of a memory episode is initiated. All memory episodes that share traits with the cue are potentially retrieved here, leading to a faster retrieval the more memory episodes there are (similar to the process of automatization as described in @logan_1988). This speeds up the cognitive processing to a degree dependent on the number of stored episodes. Because there cannot be fewer than zero episodes, this assumed mechanism on its own could not lead to a slowing down of cognitive processing due to learned negative associations. This, in turn, means that there cannot be a numerically negative effect on cognitive processing.

In this way, it is possible and even likely that two theories would lead to the same predictions regarding the expected value of effects based on the association. This is likely because such theories usually have the goal of explaining the same phenomena. When only looking at mean differences, it might not be possible to test these theories against each other, whereas considering the variability of the effects offers a straightforward test: If the effect extends into the negative, then a theoretical model that requires it to always be positive seems less plausible (see Figure \@ref(fig:hist-trunc)). Note that there are other traits of the resulting distributions that could differentiate them (e.g., the variance), but depending on the specifics of how the mechanisms are conceptualized, these tests might be less powerful.

```{r hist-trunc, fig.cap ="Histograms of simulated distributions for association mechanisms", fig.topcaption = TRUE, echo=FALSE, results='asis', warning = FALSE, fig.align='center'}
knitr::include_graphics(here("images/FigA6.jpeg"))
```

# References


