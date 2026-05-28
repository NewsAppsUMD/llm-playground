# llm-playground

An introduction to using large language models in R for journalism, using the [ellmer](https://ellmer.tidyverse.org/) and [tidyllm](https://edubruell.github.io/tidyllm/) packages.

## Getting Started

Using the green "Use this template" button on the top right, create a copy of this repository under your GitHub account, giving it the same name. Open that repository in a codespace.

### Install Packages

In the codespace terminal, run:

```bash
Rscript setup.R
```

This installs `ellmer` and `tidyllm`, two R packages for interacting with different LLMs, along with some helper packages. We use `ellmer` for interactive chat and structured data extraction, and `tidyllm` for batch processing many prompts at once.

### API Keys

We'll use two LLM providers. Both have free tiers.

**Groq** (for text models): Generate an API key at https://console.groq.com/keys. Copy the key, then in the terminal run:

```bash
echo 'GROQ_API_KEY=your_key_here' >> ~/.Renviron
```

Replace `your_key_here` with the key you copied.

**Google Gemini** (for vision models): Generate an API key at https://aistudio.google.com/apikey. Copy the key, then run:

```bash
echo 'GOOGLE_API_KEY=your_key_here' >> ~/.Renviron
```

After adding both keys, restart R (type `q()` then start R again, or restart the codespace) so the keys take effect.

### Verify Setup

Open R in the terminal (type `R`) and run:

```r
library(ellmer)
chat <- chat_groq(model = "meta-llama/llama-4-scout-17b-16e-instruct")
chat$chat("20 names for a pet turtle")
```

You should see a list of creative turtle names. If you get an error about the API key, double-check the steps above.

## Exercises

Open `exercises.Rmd` and work through the tutorial. Run each code chunk, fill in your answers, then commit and push your work when finished.
