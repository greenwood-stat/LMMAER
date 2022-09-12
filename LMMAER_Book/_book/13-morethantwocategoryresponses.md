---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# More than two category responses {#chapter13}






## Situation {#section13-1}

In Chapter \@ref(chapter4), situations that build on the binary (two-category) response were introduced. There are two roads to follow in this situation, where the three or more categories are unordered but mutually exclusively categories and where the categories contain a natural ordering. The ordered version of the variables contains an assumption both about the ordering but in terms of the models, and both situations essentially use a common likelihood for defining the model for the responses. The ordinal response version of the models can be quite a bit simpler to interpret than in the un-ordered situation, but has a strong assumption about how the probabilities of change transition across the ordered categories that can be difficult to assess. Extensions of mixed models (discussed in Chapter 14 [cite]) to these models are simpler for the ordinal response than in the unordered situation, giving one more reason to try to use these methods, if reasonable to consider.




<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section13-2}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

