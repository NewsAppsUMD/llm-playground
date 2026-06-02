# llm-playground

An introduction to using large language models in R for journalism, using the [ellmer](https://ellmer.tidyverse.org/) and [tidyllm](https://edubruell.github.io/tidyllm/) packages.

## Getting Started

Using the green "Use this template" button on the top right, create a copy of this repository under your GitHub account, giving it the same name. Clone that repository to your computer and open it in RStudio.

### Install Packages

In the RStudio terminal, run:

```bash
Rscript setup.R
```

This installs `ellmer` and `tidyllm`, two R packages for interacting with different LLMs, along with some helper packages. We use `ellmer` for interactive chat and structured data extraction, and `tidyllm` for batch processing many prompts at once.

**if you get this error**: 

```
Error in contrib.url(repos, "source") : 
  trying to use CRAN without setting a mirror
Calls: install.packages -> contrib.url
```

Do these steps:

1. In the console, type `file.edit("~/.Rprofile")`
2. In the file, add these lines:

```
# Add this line to ~/.Rprofile so it applies every session
options(repos = c(CRAN = "https://cran.r-project.org"))
```

3. Save the file and restart R: Session -> Restart R.
4. Run the Rscript command again.




### API Keys

We'll use two LLM providers. Both have free tiers.

**Groq** (for text models): Generate an API key at https://console.groq.com/keys.

**Google Gemini** (for vision models): Get the API key from here: https://www.yellkey.com/wonder

Once you have both keys, open your `.Renviron` file in RStudio by running this in the console:

```r
usethis::edit_r_environ()
```

Add these two lines, replacing the placeholder values with your actual keys (no quotemarks:

```
GROQ_API_KEY=your_key_here
GOOGLE_API_KEY=your_key_here
```

Save the file, then restart R (Session menu in RStudio) so the keys take effect.

### Verify Setup

In the console, do this:

```r
library(ellmer)
chat <- chat_groq(model = "meta-llama/llama-4-scout-17b-16e-instruct")
chat$chat("20 names for a pet turtle")
```

You should see a list of creative turtle names. If you get an error about the API key, double-check the steps above.

## Exercises

Open `exercises.Rmd` and work through the tutorial.
