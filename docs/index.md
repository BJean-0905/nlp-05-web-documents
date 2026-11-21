# Web Mining and Applied NLP Project Report

Web Mining and Applied NLP | Project 05 | Example Report

## Overview

This project introduces web document acquisition
and structured information extraction from HTML.

The objective is to retrieve an HTML document,
validate its structure,
extract meaningful text and metadata,
and persist the results for analysis.

The project extends the EVTL architecture
introduced in Module 4
from structured JSON API responses
to semi-structured HTML documents.

## Tools and Methods

The project uses:

- Python for pipeline orchestration and processing.
- Requests for retrieving HTML documents.
- BeautifulSoup for parsing and inspecting HTML.
- HTML selectors for locating document content.
- Validation checks for confirming required elements.
- Pandas for structured data transformation.
- Textblob for Sentiment Analysis
- CSV for persistent output.
- Logging for execution records.
- Ruff, ty, and pytest for code verification.
- Zensical and GitHub Pages for published documentation.

The example retrieves an academic paper's
abstract page from arXiv.

The pipeline implements four stages:

- **Extract** - retrieve HTML and preserve the source document.
- **Validate** - verify that required document elements exist.
- **Transform** - extract metadata and calculate derived fields.
- **Load** - save the structured results to a CSV file.

The Transform stage extracts fields including
the paper title, authors, abstract,
subject categories, and submission information.

It also calculates abstract word count
and author count.

## Verification

A successful execution displays:

    Pipeline executed successfully!

The pipeline records execution details in a project log.

The following artifacts are created:

- `data/raw/case_raw.html` - original HTML document.
- `data/processed/case_processed.csv` - extracted and transformed data.

These results demonstrate that the pipeline can
acquire, validate, extract, and persist
information from an HTML document.

Automated tests provide additional verification
of the pipeline's expected behavior.

## Technical Modification

Add Textblob to imports. Update pyproject.toml. Update
Stage 03-transform to reflect sentiment score and
label. Initial predication based off research suggests
that academic work may result in neutral labels. Interested
in applying this technique in the custom project to news site.
Sentiment score and label ran successfully in the example
project and resulted in a neutral label.
![Sentiment Score and Label](image.png)

## Custom Project

Using HTML from this site, https://arxiv.org/abs/2611.26092,
the EVTL pipeline was updated and applied using the technical modification
sentiment analysis. Files, pipeline_web_html and config were copied and updated
to reflect the new URL and project. Assumption was that the label would still
result in neutral as the site is academic in nature. The assumption was confirmed.

Powershell command:
uv run python -m nlp.pipeline_web_html_goucher

![Custom Project Sentiment Analysis](image-1.png)

The following files are created:
  -[Processed Data](data/processed/goucher_processed.csv)
  -[Raw Data](data/raw/goucher_raw.html)

## Interpretation

HTML documents are primarily designed
for presentation in web browsers.

Extracting structured information requires
understanding the document's elements,
attributes, and organization.

Changes in page structure can affect
validation and extraction results.

Explicit validation and transformation stages
help identify these problems
and make web mining workflows more reproducible.

The resulting structured text and metadata
provide inputs for subsequent NLP analysis.

## Documentation Index

- **Home** - this landing page
- [**Project Instructions**](project-instructions.md)
- [**Glossary**](glossary.md)

## Project Links

- [GitHub Repository](https://github.com/BJean-0905/nlp-05-web-documents)
- [Example Pipeline](https://github.com/BJean-0905/nlp-05-web-documents/blob/main/src/nlp/pipeline_web_html.py)
- [Example Configuration](https://github.com/BJean-0905/nlp-05-web-documents/blob/main/src/nlp/config.py)
- [Pipeline Stages](https://github.com/BJean-0905/nlp-05-web-documents/tree/main/src/nlp)

## Project Resources

- [Project Instructions](project-instructions.md)
- [Professional Python Guide](https://denisecase.github.io/pro-analytics-02/)
- [Professional Python Project Explainer](https://pup-pack.github.io/professional-python-project-explainer/)
