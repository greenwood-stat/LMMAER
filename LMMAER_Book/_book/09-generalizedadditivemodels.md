---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Generalized Additive Models (GAMs) {#chapter9}






## Situation {#section9-1}

In Chapter \@ref(chapter1), the linearity of the relationship between each quantitative predictor and the response was discussed. Here, a new method is discussed for accounting for violations of the linearity assumption - using splines and penalized estimation to develop smooth curves to relate each predictor to the response. This is a direct competitor for the polynomial treatment to handle simple curving predictor relationships to the response, one that can handle more complex relationships that include linear sections of the relationship or multiple inflection points. This flexibility makes these methods particularly attractive for long-term trend estimation, where the mean of the response might have a cyclic component. I have used these models to estimate trends in paleo-climate data ([cite Santibanez]) over many thousands of years and in river water temperature data over decades ([cite sturgeon paper]).

Generalized additive models (GAMs) also are called semi-parametric models because they mix parametric aspects (other predictors and normality of the response and residuals to start with). These also have extensions to incorporate aspects of mixed models, such as non-constant variance and/or random effects, leading to generalized additive mixed models (GAMMs) or semi-parametric mixed models.




<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section9-2}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

