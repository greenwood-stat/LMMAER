---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Linear Mixed Models (Two-levels) {#chapter7}







Two-level situations arise from repeated measures on the same subject or from a group of subjects and present our first chance to fit a fully mixed model where we can incorporate random effects to account for the systematic subject-to-subject or group-to-group variation. This model contains an assumption about a random sample of the levels of the random effect for the inferences about that part of the model.

<!-- \newpage -->

## Situation {#section7-1}

<!-- \newpage -->

\indent Two-level situations arise from repeated measures on the same subject or from a group of subjects and present our first chance to fit a fully mixed model where we can incorporate random effects to account for the systematic subject-to-subject or group-to-group variation. This model contains an assumption about a random sample of the levels of the random effect for the inferences about that part of the model.



In Chapter \@ref(chapter1)


### Sub-sub section? {section7-1-1}


testing

<!-- \newpage -->

## Random intercept {#section7-2}


caterpillar plots

lme vs lmer vs ???


## Comparing fixed to random effect grouping variable {#section7-3}


[under construction]

## Design effect, variation explained, and intra-class correlation {#section7-4}

With the first "fully" mixed model that accounts for repeated measures with a random intercept, there are some new summaries and considerations that all relate to the amount of variation of the total in $Y$ that is accounted for by the random effect and fixed effect(s). There is a need work with $Var(Y)$ which is $Var(Y) = Var(X_i\beta + b_i + \epsilon_i)$. We need to make an assumption to move forward to the next step, that the fixed effects, random effect, and random errors are all independent^[If they were not independent, then we would have to incorporate covariance among each component and this would get complicated - as in the similar exploration of the random intercept and slope model.]. Think of this as "conditional on the other two, there is no related information from those two in the other one". We estimate them all simultaneously, so they can have some interplay, but after being estimated, each does not share information. [find reference for more exploration of this] Then $Var(Y) = Var(X_i\beta + b_i + \epsilon_i) = Var(X_i\beta) + Var(b_i) + Var(\epsilon_i) = Var(X_i\beta) + \sigma^2_b + \sigma^2_\epsilon$. This defines the total variation in the responses as being attributed to the sum of three different sources, fixed effects, random effects, and random errors. 

Assuming that estimators for each of those components can be found in some way or another, then two quantities of interest can be defined that relate to our regular R-squared from linear models: (1) the total variation in the response explained by the fixed effects, (2) the total variation in the response explained by the fixed and random effects, and (3) taking one minus the total variation explained by the fixed and random effects for the total unexplained variance. For an implementation of this that works with our current linear mixed models and has related extensions into GLMs and GLMMs, we use MuMIn's 'rsquared.glmm' which provides the "marginal" and ... 


## Random intercept and random slope {#section7-5}

plots versus time

like an interaction of time and subject (sort of)



The ICC can also be defined here, but it varies as a function of values of the predictor variable used to drive the random intercept and slope, so is quite complex. Zuur et al. [cite] provide a framework for this (page XXX). 


predictions vs observed


The curious case of a random slope and a categorical predictor

Choosing the variable for the random slope when more than one predictor is present and - can you have more than one random slope in lmer?


## Inference for fixed and random effects {#section7-6}

For fixed effects, we...


## Decomposing fixed effects: aggregating and centering {#section7-7}

The previous discussion of inference and degrees of freedom for fixed effects provides a focus on the level of variation of the predictors. As noted in Chapter [XXXX], it is up to the researcher to decide on the level variation for predictors in multi-level models. In particular for repeated measures on subjects over time, the predictors can be decomposed into variation among subjects and variation for each subject over time.

To illustrate this, I will revisit my fictitious IQ test and beer consumption simulated data set. But I used a similar approach to generate key findings in a educational setting and help us resolve some mysterious results before we took this approach (the response was ordinal, so did not fit here).


## Diagnostics for linear mixed models {#section7-8}


[write a function for making LMM diagnostics from either lme or lme4 using ggplot2]

## Curvature and random slopes {#section7-9}

\indent Sometimes the linearity assumption is problematic and polynomials^[See Chapter [] for more on this.] are needed to better model quantitative predictors in terms of their relationships with the response. While it is possible to raise the predictor to power or (better) center and then raise them to a power, the 'poly' function provides a way to generate the powers of the variable in a way that 

Random intercept around curve

Random intercept and linear components with higher order poly()

Random intercept, linear, and quadratic with quadratic poly




## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section7-10}


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

