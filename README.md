<div align="center">
  <table>
    <tr>
      <td width="110" align="center">
        <img src="logo.png" alt="RD Triage logo" width="80">
      </td>
      <td align="left">
        <h1>Large language models for specialty triage in rare diseases: a retrospective study</h1>
      </td>
    </tr>
  </table>
</div>


## Overview

**Background:** Specialty triage at first contact is an overlooked step in early diagnostic pathways for rare diseases. Patients often present with overlapping, multisystem, and atypical manifestations, making first-visit specialty selection challenging and potentially prolonging diagnostic pathways. We aimed to evaluate large language models (LLMs) for initial-visit specialty triage in rare diseases.

**Methods:** In this retrospective benchmarking study, we used five rare disease datasets: a publication-derived case set, three RareBench-derived datasets, and a Facial phenotype-Gene-Disease Dataset-derived set. Fourteen LLMs were evaluated over five independent runs per case. Performance was assessed using accuracy, response time, and consistency, with subgroup analyses by model accessibility, reasoning mode, parameter scale, and phenotype count. Human comparison was conducted on the publication-derived case set using registered nurses and non-medical participants.

**Findings:** Across datasets, accuracy varied from 0.4378 to 0.7141. Claude-opus-4-5 achieved the highest accuracy (0.7141) and consistency (0.9653), averaging 10.79 s per case. GPT-5.1 had the shortest response time (3.39 s per case) and high accuracy (0.6948). Proprietary models achieved higher average accuracy than open-weight models (0.6973 vs 0.6365). Standard models achieved higher average accuracy than thinking models (0.6789 vs 0.5826) and had shorter response times. Accuracy varied by phenotype count, with higher performance in cases with 1-2 or more than 14 phenotypes. On the publication-derived case set, LLMs achieved higher average accuracy than registered nurses and non-medical participants (0.5978 vs 0.4914 and 0.4573).

**Interpretation:** LLMs showed potential as assistive tools for initial-visit specialty triage in rare diseases. Model choice, reasoning mode, and phenotype information density substantially influenced performance, suggesting that deployment should prioritize validated models with strong accuracy-efficiency balance. Future work should evaluate LLM-based specialty triage in prospective clinical settings and develop clinician-supervised workflows with traceable evidence support.


## Dataset Summary

The study includes **629 cases** from five sources:

| Dataset | File | Cases | Diseases | Description |
| --- | --- | ---: | ---: | --- |
| Publication set | `publication_set_questions.xlsx` | 78 | 77 | Rare disease case reports converted into first-visit clinical summaries. |
| RareBench HMS | `Rarebench_HMS.xlsx` | 83 | 24 | RareBench-derived phenotype cases adapted for specialty triage. |
| RareBench LIRICAL | `Rarebench_LIRICAL.xlsx` | 330 | 221 | RareBench-derived phenotype cases adapted for specialty triage. |
| RareBench MME | `Rarebench_MME.xlsx` | 38 | 16 | RareBench-derived phenotype cases adapted for specialty triage. |
| FGDD | `FGDD_triage.xlsx` | 100 | 100 | Facial phenotype-associated rare disease cases from FGDD. |


## Data Format

Each spreadsheet contains one case per row. The key fields are:

| Field | Meaning |
| --- | --- |
| `Question` | Prompt-ready triage question containing patient or phenotype information and the fixed department list. |
| `Department of Visit` | Reference specialty label. Some cases include multiple acceptable specialties separated by the Chinese delimiter `、`. |
| `Phenotype_id` | HPO phenotype identifiers, where available. |
| `Phenotype_text` | Natural-language phenotype descriptions, where available. |
| `PMID` or `pmid` | Source publication identifier, where available. |
| `RareDisease_OMIM`, `RareDisease_ORPHA`, `Disease_id` | Disease identifiers, depending on the source dataset. |
| `Report` | Structured clinical summary for publication-derived cases. |

For evaluation, a prediction is considered correct if the selected specialty matches any acceptable label in `Department of Visit`.


## Clinical Use Notice

This repository is intended for research and benchmarking. The data and prompts should not be used as a standalone medical triage system. Any clinical deployment should include prospective validation, clinician supervision, privacy safeguards, and traceable evidence support.

## Citation
The manuscript is currently under review. 


