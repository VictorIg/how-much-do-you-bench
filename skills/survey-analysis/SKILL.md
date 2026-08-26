---
name: survey-analysis
description: MUST use for survey, questionnaire, codebook, respondent, quant*.csv, challenges, initiatives, segmentation, or survey-normalization tasks. Read the local survey docs completely before coding; never head/cat a wide survey CSV; apply documented respondent-quality and methodology rules before aggregation.
---

# Survey workflow

Local survey documentation is authoritative.

Before implementation:

1. List docs/.
2. Read docs/README.md first when present.
3. Identify all documents governing:
   - export/header structure
   - question encoding
   - respondent inclusion/exclusion
   - data-quality exclusions
   - weighting
   - missing values
4. If the docs directory is small, read all relevant rule documents before coding.

Do not infer survey methodology from column names.

## Inspecting wide exports

Never use:
- head quant*.csv
- tail quant*.csv
- cat quant*.csv
- cut -d',' on CSV

CSV fields may be quoted and survey rows can be extremely wide.

Use Python's csv module, Polars, or pandas to inspect only:
- number of columns;
- question-code/header rows;
- columns matching the needed question;
- a few selected fields from 2-3 respondents.

## Analysis

Apply globally documented respondent exclusions before aggregation.

For multi-select questions:
- identify option columns from metadata/codebook;
- do not treat free-text OTHER fields as ordinary options unless requested;
- count respondents, not raw non-empty cells blindly.

For segmentation:
- verify the segment definition from local docs/code;
- apply exclusions before grouping;
- confirm denominators.

Do not use Context7 for survey semantics.

## Verify

Report intermediate respondent counts after filters.
Manually cross-check at least one group/category using an independent calculation.
