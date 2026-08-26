---
name: survey-analysis
description: Use for survey exports, questionnaire/codebook data, respondent segmentation, multi-select questions, survey normalization, and survey reporting.
---

# Survey analysis

For survey tasks, local documentation is authoritative.

Before implementing:

1. Inspect the task instruction.
2. Inspect the docs directory or codebook.
3. Identify:
   - header structure;
   - respondent inclusion/exclusion rules;
   - data-quality exclusions;
   - single-select versus multi-select encoding;
   - weighting rules;
   - treatment of missing values;
   - exact question codes needed by the task.
4. Inspect representative raw rows before coding.

Do not assume the first CSV row is the only header.

For multi-select questions:
- determine the option columns from the codebook/question metadata;
- exclude free-text OTHER/_TEXT fields unless explicitly requested;
- preserve the documented option labels;
- count respondents, not non-empty cells blindly.

Apply respondent-quality filters before aggregation when documentation
says they apply globally.

Do not apply survey weights unless the requested metric explicitly requires
weighted results.

For segmentation:
- establish the denominator/group population explicitly;
- apply respondent exclusions before grouping;
- verify totals and a few groups manually.

Before finishing:
- calculate at least one small result independently;
- check row/respondent counts after each filtering stage;
- verify the output shape and ordering against the requested contract.

Do not use external documentation for survey semantics.
The local codebook/methodology/data-quality documents override model knowledge.
