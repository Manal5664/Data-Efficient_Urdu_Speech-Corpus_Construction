# Thesis Work – Part 1 
## (Literature Review & Methodology)

This repository contains **Part 1** of the thesis work.

At this stage, the work is **preliminary** and focuses on building the research foundation rather than implementation or experimentation.

---

## Work Completed So Far

The following tasks have been completed in this phase:

- Relevant research papers related to **data-efficient TTS/ASR and text subset selection** have been identified and collected.
- A structured **literature review** has been prepared to understand existing approaches.
- Core **algorithms and methods** (e.g., greedy selection, KL-divergence–based and deficit-based approaches) have been studied and outlined.
- Evaluation ideas and commonly used metrics have been reviewed at a conceptual level.

---

## Methods, Dataset, and Evaluation Metrics

### Methods

In this work, **distribution-aware greedy subset selection methods** are implemented to construct a compact yet representative subset from a large Urdu text corpus. The primary objective is to retain maximum linguistic and statistical diversity while significantly reducing the overall data size.

The following methods are used:

- **Greedy KL-Divergence–Based Selection**  
  This method incrementally selects sentences that minimize the Kullback–Leibler (KL) divergence between the probability distribution of the selected subset and that of the full corpus. At each iteration, the sentence that results in the maximum reduction in KL divergence is added to the subset.

- **Greedy Deficit-Based Selection**  
  This approach maintains deficit scores for words based on their under-representation in the current subset. Sentences containing words with higher cumulative deficits are prioritized, ensuring improved vocabulary coverage and probability mass preservation.

Both methods aim to produce a subset that closely matches the statistical distribution of the original corpus, making them suitable for low-resource ASR and TTS data preparation.

---

### Dataset

A general-purpose Urdu text corpus is used for this study.

- **Dataset Name:** Urdu Plain Text Corpus  
- **Source:** Charles University, Prague  
- **Reference:** LREC 2014  
- **Type:** Open-domain Urdu text corpus  

The dataset contains diverse Urdu text sources and is not limited to a specific application domain. This diversity makes it appropriate for constructing speech corpora for open-domain Urdu ASR and TTS systems.

---

### Evaluation Metrics

The selected subsets are evaluated by comparing their statistical distributions with that of the full corpus using the following metrics:

- **Type Coverage:** Measures the proportion of unique words from the full corpus that appear in the selected subset.
- **Token Probability Coverage:** Measures the cumulative probability mass of the full corpus covered by the subset vocabulary.
- **KL Divergence:** Measures the divergence between word probability distributions of the full corpus and the selected subset. Lower values indicate higher similarity.

Additionally, **unigram and bigram-based evaluations** are performed to assess both lexical diversity and contextual coverage.

No separate evaluation dataset is used; evaluation is conducted by directly comparing the selected subset with the full corpus distribution.
