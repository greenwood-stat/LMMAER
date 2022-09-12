---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Non-constant variance models {#chapter6}






## Situation {#section6-1}

There are situations where we have continuous responses but the raw or transformed responses still have diagnostic issues, especially non-constant variance in the residuals. While there is not always a solution to these problems, there are models that allow for the variance of the residuals to change based on a variety of different options. 

In your path to this material, you have likely encountered one statistical test that allows for variances in different groups to be different - Welch's Two-Sample t-test. In Greenwood [CITE], I made a choice to focus on the equal variance version of that test that can be equivalently performed using 'lm', mainly to open the door to using linear models and their extensions. In general, we recommend the Welch's version of the t-test over the version that assumes equal variances because of the relaxed assumption on the variances and similar performance to the equal variance version when the variances are close to equal. Welch [cite] also developed a differing variance allowed version of the F-test in the One-Way ANOVA sitution that is also intriguing. In each of these cases, the main modification is to allow for each group to have its own variance. But this doesn't directly extend to regression situations with more than one predictor or where the variance might change based on something other than a categorical predictor variable. This chapter will delve into what can be called "extended regression models" that change from $\epsilon_i \sim N(0, \sigma^2)$ to something like $\epsilon_i \sim N(0, \sigma_i^2)$. It may be that different observations share a common estimated variance (like in Welch's procedures), or that each observation gets a unique variance estimate for its residual. These models open up options for three things: (1) avoiding transformations just to attain more constant variance of residuals (sometimes) simplifying model interpretations, (2) obtaining models that more closely match the reality of the residuals in a given situation so the overall model has more valid inferences, or (3) opening up new research questions that relate to changing variability of responses after adjusting for the changes in the mean. (1) and (2) are more mechanistic reasons to explore these methods, with (3) opening up new ways of thinking about statistical models that are possibly too often focused on differences in the mean. For example, consider a designed experiment in a educational setting with two groups. Perhaps one treatment is designed to help students that struggle the most but has little impact on the higher performing students - and the other group is a placebo. It is possible that the differences in the mean could be minor but possibly the impacts on a reduced variability of student performance could be more easy to see and is worth at least trying to assess (along with changes in the mean).




## Extended regression models {#section6-2}

These models have been developed and named in a few different places and are available in different R packages. These are developed as "marginal" models but the inferences (where both model being fit and inference techniques are 1-1) match results from conditional models for fixed effects. Because of differences in inference techniques and sometimes model assumptions, results for the non-fixed effect part of the model may be very different between conditional and marginal approaches. 

Here the extension to regular linear models involves modifying the assumption of equal variance.



## Specific non-constant variance models {#section6-3}


## Weighted regression models {#section6-4}


<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section6-5}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

