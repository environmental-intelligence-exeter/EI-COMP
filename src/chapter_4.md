# R tips
This chapter covers a number of R tips to help you in your data science. 
## Beginner
(1) How to install packages or load multiple packages?

Most often you will find yourself needing to download and load multiple packages in order to run your script(s). To avoid sticking `library()` calls at the top of scripts, you can simnply create a new file named something like `libs.r`, where you can list all of the packages used for your script.
```r
# Set pkgs
pkgs = c(
  "tidyverse",
  "tm",
  "tidytext",
  "sentimentr",
  "treemap",
  "quanteda",
  "SentimentAnalysis",
  "RTextTools",
  "e1071",
  "spacyr",
  "academictwitteR",
  "topicmodels",
  "Matrix",
  "textmineR",
  "ldatuning",
  "corrplot",
  "knitr",
  "kableExtra",
  "DT",
  "tidytext",
  "gplots",
  "RColorBrewer",
  "quanteda.textplots"
)

# Install pkgs not yet installed
installed_packages = pkgs %in% rownames(installed.packages())
if (any(installed_packages == FALSE)) {
  install.packages(pkgs[!installed_packages])
}

# Load pkgs
invisible(lapply(pkgs, library, character.only = TRUE))
```

You can then run the command `source("libs.r")` to install and load all of the packages required for your project.