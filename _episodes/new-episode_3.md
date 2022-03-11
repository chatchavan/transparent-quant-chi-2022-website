---
title: Introduction to Transparency-oriented Visualizations
teaching: null
exercises: null
duration: 75
summary: null
questions:
  - How does transparency relate to data visualization?
  - How to design (transparent) visualizations?
  - How to make choices that increase the transparency and usability in visualizations? 
objectives: null
keypoints: null
is-break: false
ukrn_wb_rules: []
day: 3
order: 100000

---

Continuing from our session on statistical methods, we will equip participants with mindsets and tools to create transparency-oriented visualizations during their analysis as well as for their papers. 
Such visualizations for analysis results can make a paper more transparent in multiple ways, including improving faithfulness, robustness, process transparency, and clarity (which are transparent statistics principles). 

We will first introduce the idea that visualizing uncertainty information is staying faithful to their statistical analysis. 
Without proper uncertainty representation, we risk exaggerating the certainty of our findings. 
We will show different uncertainty visualizations designs and the concepts behind the variations. 
Notably, there are no one-size-fits-all solutions for uncertainty communication. 
Thus, we will teach the practice of selecting the most ethical and transparent option at each decision point within the data visualization pipeline. 


More practically, we will identify the visualization opportunities in the two versions of statistical analysis introduced in the last section. 
To improve process transparency, we will show examples of visualizations used throughout the analysis, advocating for visualizations as a reflex during analysis. 
These visualizations include plots for the raw data, summary plots, plots for confidence distributions (frequentist) or posterior distributions (Bayesian), and other model diagnostic plots. 
For demonstration, we will use R packages including `tidyverse`, `ggplot2`, `tidybayes`, and `ggdist`. 
The focus of this part is on how the properties of these visualization techniques lend themselves to transparency. 
Therefore, all participants will benefit from this part regardless of their preference and skills in R. 
In addition, we will offer practical guidelines for making visualizations clear and simple as possible, especially for publication in  research manuscripts. 
