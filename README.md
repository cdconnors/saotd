Sentiment Analysis of Twitter Data (SAoTD)
================

<!-- don't edit the .md file, instead edit the .Rmd -->

[![DOI](https://zenodo.org/badge/117839390.svg)](https://zenodo.org/badge/latestdoi/117839390)
[![Build
Status](https://travis-ci.org/evan-l-munson/SAoTD.svg?branch=master)](https://travis-ci.org/evan-l-munson/SAoTD)
[![AppVeyor Build
Status](https://ci.appveyor.com/api/projects/status/github/evan-l-munson/SAoTD?branch=master&svg=true)](https://ci.appveyor.com/project/evan-l-munson/SAoTD)
[![codecov](https://codecov.io/gh/evan-l-munson/SAoTD/branch/master/graph/badge.svg)](https://codecov.io/gh/evan-l-munson/SAoTD)
[![minimal R
version](https://img.shields.io/badge/R%3E%3D-3.3.0-6666ff.svg)](https://cran.r-project.org/)
[![packageversion](https://img.shields.io/badge/Package%20version-1.0.0-orange.svg?style=flat-square)](https://github.com/evan-l-munson/SAoTD)

`SAoTD` is an R interface to the Twitter API and can be used to acquire
tweets based on user selected \#hashtags. The package will clean and
tidy the Twitter data, determine the latent topics within the tweets
utilizing Latent Dirichlet Allocation (LDA), determine a sentiment score
using the Bing lexicon dictionary and output visualizations.

## Installation

You can install the development version from GitHub with:

``` r
install.packages("devtools")
devtools::install_github('evan-l-munson/SAoTD')
```

## Using SAoTD

The functions that are provided by `SAoTD` are broken down into five
different categories: Acquire, Explore, Topic Analysis, Sentiment
Calculation, and Visualizations.

  - Acquire
    
      - `Acquire` allows a user to acquire tweets of their choosing by
        accessing the Twitter API. In order to do this the user needs to
        have a [Twitter](https://twitter.com) account. Additionally once
        the user has an account they will then need to sign up for a
        [Twitter Developers](https://dev.twitter.com/) account. Once a
        user has a twitter developers account and has received their
        individual consumer key, consumer secret key, access token, and
        access secret key, they can acquire tweets based on a list of
        hashtags and a requested number of entries per hashtag.

  - Explore
    
      - `Tidy` removes all emoticons, punctuation, weblinks, etc and
        converts converts the data to a tidy structure.
      - `Merge.Terms` merges terms within a dataframe and prevents
        redundancy in the analysis.
      - `Unigram` displays the text Uni-Grams within the Twitter data in
        sequence from the most used to the least used. A Uni-Gram is a
        single word.
      - `Bigram` displays the text Bi-Grams within the Twitter data in
        sequence from the most used to the least used. A Bi-Gram is a
        combination of two consecutive words.
      - `Trigram` displays the text Tri-Grams within the Twitter data in
        sequence from the most used to the least used. A Tri-Gram is a
        combination of three consecutive words.
      - `Bigram.Network` Bi-Gram networks builds on computed Bi-Grams.
        Bi-Gram networks serve as a visualization tool that displays the
        relationships between the words simultaneously as opposed to a
        tabular display of Bi-Gram words.
      - `Word.Corr` displays the word correlation between words.
      - `Word.Corr.Plot` displays the mutual relationship between words.
        The correlation network shows higher correlations with a thicker
        and darker edge color.

  - Topic Analysis
    
      - `Number.Topics` determines the optimal number of Latent topics
        within a dataframe by tuning the Latent Dirichlet Allocation
        (LDA) model parameters. Uses the `ldatuning` package and outputs
        an ldatuning plot. **This process can be a time consuming
        depending on the size of the dataframe.**
      - `Tweet.Topics` determines the Latent topics within a dataframe
        by using Latent Dirichlet Allocation (LDA) model parameters.
        Uses the `ldatuning` package and outputs an ldatuning plot.
        Prepares tweet text, creates DTM, conducts LDA, display data
        terms associated with each topic.

  - Sentiment Calculation
    
      - `Scores` calculates the Sentiment Scores using the [Bing Lexicon
        Dictionary](https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html)
        that will account for sentiment by hashtag or topic.
      - `PosNeg.Words` determines and displays the most positive and
        negative words within the twitter data.
      - `Min.Scores` determines the minimum scores for either the entire
        dataset or the minimum scores associated with a hashtag or topic
        analysis.
      - `Max.Scores` determines the maximum scores for either the entire
        dataset or the maximum scores associated with a hashtag or topic
        analysis.

  - Visualizations
    
      - `Corpus.Distribution` determines the scores distribution for the
        entire Twitter data corpus.
      - `Distribution` determines the scores distribution by hashtag or
        topic for Twitter data.
      - `Boxplot` displays the distribution scores of either hashtag or
        topic Twitter data.
      - `ViolinPlot` displays the distribution scores of either hashtag
        or topic Twitter data.
      - `TimeScale` displays how the Twitter data sentiment scores
        through time.  
      - `WorldMap` displays the location of a tweet across the globe by
        hashtag or topic.

## Example

For an example of how to use this package, find the vignette at:

``` r
library(SAoTD)
utils::vignette("SAoTD")
```

## Meta

  - Licence:
    
      - All code is licensed GL.
      - All data is from public data sources.

  - Get citation information for `SAoTD` in R by running:

<!-- end list -->

``` r
citation("SAoTD")
```

## References

  - [AFIT Data Science Lab](https://github.com/AFIT-R)
  - [Tidyverse](https://www.tidyverse.org/)
  - [Text Mining with
    R](https://www.tidytextmining.com/)
  - [ldatuning](https://github.com/nikita-moor/ldatuning)
  - [topicmodels](https://cran.r-project.org/web/packages/topicmodels/index.html)
