# PRETRAINING

There are multiple stage to build an LLM like ChatGPT. The first stage is called Pre-training stage, and the first step is download and process the internet

## Step1: Download and process the internet

- Here Andrej gives an example of fineweb (https://huggingface.co/spaces/HuggingFaceFW/blogpost-fineweb-v1).

### Fineweb:
From the page:
> 🍷 FineWeb, a new, large-scale (15-trillion tokens, 44TB disk space) dataset for LLM pretraining. FineWeb is derived from 96 CommonCrawl snapshots and produces better-performing LLMs than other open pretraining datasets. 

- They have also documented their all the design choices (including in-depth investigations of deduplication and filtering strategies).

[FineWeb Recipe](images/fineweb-recipe.png)

#### Steps in detail:
- 1. URL filtering: Applied filtering using a blocklist (https://dsi.ut-capitole.fr/blacklists/) to remove adult content (Site under maintainance when assessed on Nov 23, 2026)

- 2. Text extraction: Because when we do web-crawling, the output is HTML text, they applied text extraction to extract text.
- 3. Language filtering: Beacuse internet websites can have different languages, they used a language classifier (fastText language classifier) to keep only Engligh text with a score>=0.65.
  4. Gopher filtering: They applied quality and repetition filters from MassiveText paper (https://arxiv.org/abs/2112.11446)
  5. 