---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Linear Mixed Models (More than two levels) {#chapter8}






## Situation {#section8-1}

Now the flood gates get opened on the mixed models. All of these models use random intercepts as moving to add random slopes with more than two random effects, especially nested random effects, is difficult at best, especially to interpret. Perhaps in situations with the observation-level being measurements over time, that level could get a random slope



## Nested random effects {#section8-2}

Hierarchical designs are modeled with nested random effects. 

split-split plot

randomized complete block with repeated measures... Gundale

Notation in lme, lmer



## Non-nested (crossed) random effects {#section8-3}

Notation in lme, lmer


This also includes situations where a hierarchical design was attempted but the realities of the situation 

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section8-4}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

