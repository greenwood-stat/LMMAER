---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Spatial correlation {#chapter11}






## Situation {#section11-1}

For observations taken over space, observations that are closer together in space might be assumed to be more similar than ones that are far apart. The strength and pattern of the spatial correlation can also be informative in describing patterns in the observations. This not intended as a comprehensive coverage of modeling spatial data but as a way to adjust for correlation among neighboring responses in data that are collected spatially to continue to ask questions about the fixed effects in linear mixed models. To do this, a suite of new correlation structures are needed to be defined. These methods can also be extended to spatial-temporal models ([CITE Greenwood book chapter and R package]), although this is not the most computationally efficient way to approach these sorts of data. Along with modeling spatial data, some diagnostic plots for spatial data are defined to help with identifying types of issues with models for spatially collected data.




<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section11-2}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

