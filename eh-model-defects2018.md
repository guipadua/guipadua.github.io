---
title: Studying the Relationship between Exception Handling Practices and Post-release Defects
authors: Guilherme B. de Pádua and Weiyi Shang
location: 15th IEEE/ACM International Conference on Mining Software Repositories (MSR '18).
layout: default
permalink: /eh-model-defects2018/
---

## Abstract
Modern programming languages, such as Java and C\#, typically provide features that handle exceptions. These features separate error-handling code from regular source code and aim to assist in the practice of software comprehension and maintenance. Nevertheless, their misuse can still cause reliability degradation or even catastrophic software failures. 
Prior studies on exception handling revealed the suboptimal practices of the exception handling flows and the prevalence of their anti-patterns. However, little is known about the relationship between exception handling practices and software quality. In this work, we investigate the relationship between software quality (measured by the chance of having post-release defects) and: (i) exception flow characteristics and (ii) 17 exception handling anti-patterns. We perform a case study on three Java and C\# open-source projects. By building statistical models of the chance of post-release defects using traditional software metrics and metrics that are associated with exception handling practice, we study whether exception flow characteristics and exception handling anti-patterns have a statistically significant relationship with post-release defects. We find that exception flow characteristics in Java projects have a significant relationship with post-release defects. In addition, although majority of the exception handing anti-patterns are not significant in the models, there exist anti-patterns that can provide significant explanatory power to the chance of post-release defects. Therefore, development teams should consider allocating more resources to improving their exception handling practices, and avoid the anti-patterns that are found to have a relationship with post-release defects. Our findings also highlight the need for techniques that assist in handling exceptions in the software development practice.

Read our paper: [Paper](/resources/eh-model-defects2018_cr.pdf)

<!-- *If you use our data or code, please cite our paper.* [BibTex](/resources/scam2017-revisiting-eh_cr.bib) -->

## Evaluated Subject Projects

The subject projects are 3 open-source softwares. To reproduce our study, the releases we analysed can be found in the links below.

|--- | --- | --- | 
| Project | Release | Latest Post-Release |
|---:|:---:|---:|
|C# Umbraco-CMS	    |[release-7.6.0	](	https://github.com/umbraco/Umbraco-CMS/releases/tag/release-7.6.0)  |[release-7.6.12	](	https://github.com/umbraco/Umbraco-CMS/releases/tag/release-7.6.12 ) |
|Java Hadoop        |[rel/release-2.6.0	](	https://github.com/apache/hadoop/releases/tag/release-2.6.0	)   |[rel/release-2.6.5	](	https://github.com/apache/hadoop/releases/tag/rel/release-2.6.5	)|
|Java Hibernate     |[5.0.0.Final ](https://github.com/hibernate/hibernate-orm/releases/tag/5.0.0.Final)    |[5.0.16](https://github.com/hibernate/hibernate-orm/releases/tag/5.0.16)|
|--- | --- | --- | 

## Exception Flow Analyzer

The source code and binary files of the two source-code analysis tools that we used are available below.

[Java Binary and Source](https://github.com/guipadua/JTratch/releases/tag/eh-model-defects2018) \\
[C# Binary and Source](https://github.com/guipadua/NTratch/releases/tag/eh-model-defects2018)

### Extracted metrics and aggregations

Before modeling, the metrics are not in the file level. This link is the list of all metrics, where they were extracted, and how they were aggregated to the next level.

[Metrics and aggregation rules](https://docs.google.com/spreadsheets/d/11fb_6FlbH9ws0Iue-2ANmPhzIG-TB3fJRD6j0cVvsX4/edit?usp=sharing)

<!-- <iframe src="https://public.tableau.com/views/PossibleExceptionsPublic/Quantity?:embed=y&:display_count=yes&publish=yes" width="960" height="960"></iframe>   -->

## Data Input at File Level, Scripts and Output

Refer to the paper for further explanation about what the script is doing.

The input data comes from five different sources(i.e., different metrics/columns). This file is all data sources merged without any observation that miss data on any column. \\
[Single CSV with merged data with no missing](/resources/eh-model-defects2018_data_without_missing.zip)

The input data comes from five different sources(i.e., different metrics/columns). This file is all separate data sources and all scripts required and used to obtain the results presented on the paper. This is a full replication package for modeling. \\
[Input, Scripts and Output](/resources/eh-model-defects2018_scripts_with_input_data.zip)

### Model construction and analysis steps

Based on the R Notebooks created (i.e., scripts above), we knitted the results in HTMLs below:

[Data processing and missing data analysis](/resources/eh-model-defects2018-0-DataSourcesAnalysis.html) \\
[Model construction and analysis](/resources/eh-model-defects2018-1-Model_Construction.html)

## More on R and Regression Modeling Strategies

To understand more about our modeling approach and the R packages we used.

[Dr. Frank Harrell's RMS package, course and book](http://biostat.mc.vanderbilt.edu/wiki/Main/RmS) \\
[Dr. Frank Harrell's Hmisc package](http://biostat.mc.vanderbilt.edu/wiki/Main/Hmisc) \\
[Dr. Max Kuhn's caret package](https://topepo.github.io/caret)
