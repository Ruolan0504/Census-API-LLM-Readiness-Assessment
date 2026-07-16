# Census API Readiness Assessment for LLM-Based Query Systems

A system-level assessment of U.S. Census API datasets for potential use in natural-language, text-to-data, and LLM-supported analytical workflows.

**[View the Population Estimates Analysis Demo](https://ruolan0504.github.io/Census-API-LLM-Readiness-Assessment/US-Population-Estimate-Analysis-and-Visualization.html)**

## Project Overview

This project examines whether major U.S. Census Bureau datasets can reliably support LLM-based query systems.

The main challenge is not simply accessing an API. A natural-language question must first be connected to the correct dataset, variable codes, year, geographic level, and output format. Differences across Census datasets can make this process difficult and may affect the accuracy of downstream analysis or LLM-generated responses.

Rather than presenting a complete production application, this project evaluates the underlying data environment and identifies the intermediary mapping and validation steps needed for a reliable text-to-Census-API workflow.

## Research Questions

This assessment focuses on four questions:

1. How accessible and usable are major Census datasets through the Census API?
2. How consistent are their data structures, variable definitions, geographic identifiers, and output formats?
3. How might missing coverage or inconsistent geographic granularity affect downstream analysis and LLM reliability?
4. What intermediary steps are needed to translate a natural-language request into a valid Census API query?

## Datasets Reviewed

The assessment covers five Census data products:

- American Community Survey (ACS)
- Economic Census
- Population Estimates
- Small Area Health Insurance Estimates (SAHIE)
- Postsecondary Employment Outcomes (PSEO)

These datasets represent different subject areas and data structures, allowing the project to compare practical integration challenges across Census products.

## Assessment Approach

The project included:

- Reviewing API accessibility and dataset documentation
- Comparing variable structures, geographic codes, time coverage, and output formats
- Cleaning and standardizing selected Census data
- Identifying missing coverage and inconsistent geographic granularity
- Examining how a user question could be mapped to Census variables and geographic identifiers
- Evaluating potential failure points in downstream analytics and LLM-generated answers
- Outlining validation requirements for a more reliable text-to-API system

## Proposed Text-to-API Workflow

A practical LLM-supported Census query system would require more than direct prompt-to-API generation.

```text
Natural-language question
        ↓
Intent and entity extraction
        ↓
Dataset selection
        ↓
Variable, year, and geography mapping
        ↓
Census API query construction
        ↓
Coverage and schema validation
        ↓
Structured analytical output
        ↓
LLM-generated explanation
```

The intermediary mapping layer is important because users generally describe concepts such as population, income, employment, education, or insurance coverage in everyday language, while the Census API requires dataset-specific variable codes and geographic parameters.

## Key Findings

The assessment suggests that:

- The Census API should not be treated as one fully standardized data source.
- Dataset structures and conventions vary across Census products.
- Natural-language requests can be ambiguous without explicit variable, year, and geography resolution.
- Missing observations or inconsistent geographic coverage may produce incomplete or misleading results if they are not checked.
- Query generation should be combined with schema validation, coverage checks, and interpretable metadata.
- A reusable mapping layer could improve the reliability of LLM-based Census data applications.

## Population Estimates Analysis Demo

A downstream analytical demo was created to test the practical usability of Census population data.

Using U.S. Census Bureau Population Estimates for 2020–2024, the demo:

- Loads and cleans the Census dataset in R
- Reshapes annual population estimates for analysis
- Visualizes the national population trend from 2020 to 2024
- Compares geographic units with the largest estimated populations
- Calculates population growth rates between 2020 and 2024
- Produces reproducible visualizations with `ggplot2`

The demo illustrates how Census data can support downstream analysis after the relevant dataset has been identified, cleaned, and interpreted.

**[Open the interactive HTML report](https://ruolan0504.github.io/Census-API-LLM-Readiness-Assessment/US-Population-Estimate-Analysis-and-Visualization.html)**

## Repository Structure

```text
.
├── README.md
├── report/
│   └── Research materials and assessment outputs
├── demo/
│   ├── README.md
│   ├── US Population Estimate Analysis and Visualization.Rmd
│   └── US-Population-Estimate-Analysis-and-Visualization.html
└── US-Population-Estimate-Analysis-and-Visualization.html
```

The HTML file in the repository root is used for the GitHub Pages deployment.

## Tools and Technologies

- R
- R Markdown
- Census API and Census data files
- `tidyverse`
- `readr`
- `dplyr`
- `ggplot2`
- Data cleaning and transformation
- Exploratory data analysis
- Data visualization
- API-readiness assessment

## Limitations

- This repository presents a readiness assessment rather than a complete deployed LLM application.
- The five reviewed datasets do not represent every Census API product.
- Dataset schemas, releases, and documentation may change over time.
- The population analysis is an illustrative downstream demo and does not establish causal explanations for demographic changes.

## Potential Next Steps

Future development could include:

- Building a searchable metadata dictionary for Census variables
- Developing a natural-language-to-Census-query prototype
- Adding automatic geographic and time-coverage validation
- Returning source metadata alongside every generated answer
- Testing the workflow against a benchmark set of demographic questions
- Expanding the assessment to additional Census datasets

## Author

**Ruolan Ren**
