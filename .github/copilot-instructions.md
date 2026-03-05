# Copilot Instructions — analise-tesouro-direto

## Project Overview

This project is an academic data analysis work for the *Análise de Dados e Boas Práticas* specialisation at PUC. It uses the **Taxas dos Títulos Ofertados pelo Tesouro Direto** dataset to demonstrate the full data-science pipeline from problem definition through exploratory analysis and pre-processing.

## Repository Layout

```
analise-tesouro-direto/
├── analise_tesouro_direto.ipynb   # Main Google Colab notebook (report)
├── .github/
│   └── copilot-instructions.md   # This file
├── README.md
├── LICENSE
└── .gitignore
```

## Language & Runtime

- **Language:** Python 3.x
- **Primary runtime:** Google Colab (Jupyter-compatible)
- **Key libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

## Coding Conventions

- Follow **PEP 8** style guide throughout all code cells.
- Use **snake_case** for variables and function names.
- Prefer **f-strings** over `%` or `.format()` for string interpolation.
- Each logical step lives in its own code cell.
- Every code cell is preceded by a **Markdown cell** that explains in Portuguese what the cell does and why.
- Do **not** hard-code local file paths; load data directly from the public URL:
  ```
  https://www.tesourotransparente.gov.br/ckan/dataset/df56aa42-484a-4a59-8184-7676580c81e3/resource/796d2059-14e9-44e3-80c9-2d9e30b405c1/download/precotaxatesourodireto.csv
  ```
- Separate display-only imports from functional imports.
- Import all libraries at the top of the notebook in a single dedicated cell.

## Notebook Structure

1. **Capa / Título** — Title, author, institution, date.
2. **Definição do Problema** — Context, objectives, hypotheses, attribute definitions.
3. **Carregamento dos Dados** — Load CSV from URL, first inspection.
4. **Análise Exploratória**
   - Descriptive statistics (shape, dtypes, `describe()`, missing values)
   - Visualisations with analysis paragraphs after each chart
5. **Pré-processamento**
   - Type conversions, missing-value treatment, normalisation, standardisation, discretisation, one-hot encoding
6. **Conclusão** — Summary of findings and next steps.

## Chart Style

- Use `matplotlib` and `seaborn` for all charts.
- Set `seaborn` style to `"whitegrid"` and the `"muted"` palette globally at the start.
- Always label axes and set a descriptive `title`.
- After every chart, write a Markdown analysis paragraph (in Portuguese) summarising the key findings.

## Documentation Language

All Markdown/text cells must be written in **Brazilian Portuguese**. Code comments may be in English or Portuguese — remain consistent within a file.

## Data Notes

- The CSV uses semicolons (`;`) as separators and commas (`,`) as decimal separators.
- Date columns (`Data Vencimento`, `Data Base`) must be parsed as `datetime` objects.
- Numeric columns (`Taxa Compra Manha`, etc.) must be cast to `float` after replacing `,` with `.`.
- The dataset contains bonds of multiple types (`Tipo Titulo`) spanning many years; always filter or group by bond type before time-series analysis.
