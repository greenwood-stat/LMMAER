---
output:
  html_document: default
  pdf_document:
    keep_tex: yes
---

# Data visualization and data wrangling for hierarchical data {#chapter5}






## Situation {#section5-1}

In Chapter \@ref(chapter4), a suite of different models and types of responses are defined, along with some potential models for those responses. Here, some specific data visualization tools and data wrangling techniques are discussed. 

Data visualization provides ways to ask questions of our data that relate to model choice and develop expectations for results from models, to understand likely complications or limitations in the modeling process, and even to suggest new models. I do not suggest "mining" your data for research questions - these should be developed _a priori_, but if your research question is about the relationship between two variables, the RQ might need to change if that relationship seems to be different across levels of another variable (like in ANCOVA settings). Data visualization can also help to suggest model modifications for the response (transformations or changing the proposed response distribution as in zero-inflated or zero-truncated counts) and systematic components (transformations or polynomials or splines for curving relationships) or to target certain unusual observations for further investigation prior to fitting a model (remember the Chapter \@ref(Chapter1) discussion about non-influential outliers that can impact the distribution of residuals and influential observations that can impact and distort the fit of the models).  

In order to facilitate our modeling and data visualization, there are three possibly new data wrangling skills that are needed. There are related tasks that are needed with hierarchical and especially repeated measures data. In "simple"^[These really are not simple and often this is used in more complex designs too.] two-level designs where repeated measures are taken on a subject, the observations are often organized in a wide fashion, with one row per subject and repeated time points on the same variable placed in different columns. This is great for data entry simplicity but often not compatible with our models (all the responses need to be in a single column with an additional column indicating which time point they came from). Also to utilize the full power of ggplot2 [cite] for data visualization, we need the same sort of "responses in a column" format. The 'pivot_longer' function and its related 'pivot_wider' functions from `dplyr` [cite] provide ways of pivoting into the "long format" data that we need and then back to "wide format". Sometimes data are collected in two or more different locations, the wide format longitudinal data, for example, and a second spreadsheet of demographics for each subject that are not changing over time (**static**). The 'left_join' function from 'dplyr' provides a way to link the long format longitudinal information to repeatedly looking up and copying the static demographic data based on a linking subject identifier in both spreadsheets (think "subject ID"). Finally, sometimes there is a need to take information and aggregate it to a higher level of the measurement hierarchy to create a new version of a predictor variable, which can be done with `ave` function when means are needed or more generally using 'dplyr' and its 'group\_by' function. Section [5-2] explores each of the functions and demonstrates them with two examples.


## Data wrangling for longitudinal data {#section5-2}


* Student test data - maybe find another example from base R?


* Simulated IQ and beers example?


## Data visualizations and summaries for missing data {#section5-3}

Missing data are a reality of many real studies, sometimes systematically and sometimes by accident (also known as demonic intrusion). One can think of the missingness often as being driven by a random process, but that random process could be related to ...



## Data vizualizations for non-normal responses {#section5-4}

For non-normal responses (binary, multi-category, and counts), there are some specific plots that allow exploration of the responses that extend beyond scatterplots and boxplots. Specifically, conditional density plots ('cdplot' or 'geom_density' from 'ggplot2') allow visualization of categorical response versus a quantitative predictor, displaying estimated probabilities of each category across the range of the observed predictor variable. The base R 'plot' function provides a 'spineplot' when used to explore a categorical response versus a categorical predictor - although we can find a similar plot using [????] from 'ggplot2'. There is also the 'mosaicplot' that is discussed in detail in https://greenwood-stat.github.io/GreenwoodBookHTML/chapter5.html#section5-3 for visualizing two categorical variables and results from the related Chi-squared tests. Both the spineplots and mosaicplots display proportions related to different categories, although the mosaicplot is more the proportion of the total and the spine plot is the proportion in a response category at each level of the categorical explanatory variable. By making the conditional density plots, spineplots, or mosaicplots conditional on levels of a third variable, hints of interactions, and other more complex multivariable relationships. The conditional density types of plots allow for visualizing a categorical response versus each predictor and that is especially useful for setting expectations for models in terms of directions of relationships and likely important predictors - they also can resemble plots that are be used to understand model-based predicted probabilities of categories. 


There are also plots that can be used to directly explore multi-variable relationships, some that work best for just quantitative or binary variables and others that can incorporate a mix. Of interest here are the tableplots ('tabplot' package discussed in Chapter [1]) that can sort observations based on any variable - here we might consider sorting on a predictor of interest or on the response variable of interest to see if patterns in the other or in other predictors emerge. Missing data can also be visualized with this display, and is always a good starting point for working with a data set. See https://greenwood-stat.github.io/GreenwoodBookHTML/chapter4.html#section4-6 and https://greenwood-stat.github.io/GreenwoodBookHTML/chapter5.html for more discussions of tableplots and examples with missing observations. 

Another plot that can help to elicit connections among a response and a suite of predictors is an alluvial diagram. This plot requires all quantitative predictors to be binned into categories, but can be an impactful way to show how values on the response might relate to combinations of the predictor space. [could this elicit interactions? need to explore]. The simplest way to make alluvial diagrams is with the `alluvial_wide`.... It explicitly works from the version of the data set you will model with - the "wide" here means that you don't have to do additional work to make the tables of combinations that end up driving the alluvia (flows) in the plot. For more on this see [?].

Finally, when the variables are all quantitative or binary^[You could facet on variables with more than two categories, but including them within the plot is problematic.] the parallel coordinate or spaghetti plots are an option. These are particularly useful for plotting repeated measures on the same variable over time in the spaghetti plots, but exploring connections among variables that are on different scale in parallel coordinate plots (PCP) can also be useful. The main difference in these plots is that spaghetti plots are not scaled to be between 0 and 1 for each x-axis tick mark whereas PCPs must have this scaling. We can use the same function for making these sorts of plots ('gg_parcoord" from GGally [CITE]), but change the scaling options to switch between different types of plots. Specifically the option ... makes a PCP and the option ... does not rescale the variables. These functions assume that data are in a wide format (each column is a time point, each row is a subject for longitudinal data). If the data are in long format already, then we can use ggplot to make the spaghetti plots (PCPs are not easily made in this fashion).

Before you jump into plotting, or sometimes after you jumped in too quickly, you should carefully consider the order of, and text used for, the levels of any categorical variables. Generally^[There are exceptions to this rule based on prior wrangling or sometimes the data format of the original observations (SPSS' ".sav" files for example.)], R uses whatever was in the spreadsheet and makes the levels alphabetically. But just because R made a default choice does not mean you will like that choice or need to use it. I tend to favor making my variables and then re-coding levels, often into a new "factor" variable. If you ever just want to change the baseline of a factor, the 'relevel' function is particularly effective. More complex re-ordering or factor level modifications are best handled using 'forcats' functions like...











Sometimes making more one plot can help to identify different aspects of a data set, so don't feel like you must make all plots or must report every type of plot in each case.

ordering categories prior to plotting, changing baseline


* cdplot

* tableplot

* alluvial diagrams

* pirateplot/violins

* with log1p



<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->

## Multiple (pair-wise) comparisons using Tukey's HSD and the compact letter display {#section5-5}

<!-- \sectionmark{Multiple (pair-wise) comparisons using Tukey's HSD and CLD} -->


\indent There is a method that many researchers use to more efficiently generate and 
report these sorts of results that is called a ***compact letter display*** \index{compact letter display}
(CLD, @Piepho2004)^[Note that this method is implemented slightly differently than explained here in some software packages so if you see this in a journal article, read the discussion carefully.]. The ``cld`` function can be applied to the results from 

<!-- \newpage -->

