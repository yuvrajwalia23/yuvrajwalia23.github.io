# Yuvraj Singh Walia's Quarto Website

This repository contains my personal Quarto website for DSCI 521 in the
UBC Master of Data Science program.

The website includes my earlier course material as well as two computational
posts created for Milestone 3:

- A Python analysis of the Palmer Penguins dataset.
- An R analysis of the Palmer Penguins dataset.

Both computational posts contain visible code and output generated when the
website is rendered.

## Requirements

The website was developed and tested with the following software:

- Quarto 1.10.18
- uv 0.12.7
- Python 3.14
- R 4.6.1
- Git

Python dependencies are managed using `uv` and are recorded in:

- `.python-version`
- `pyproject.toml`
- `uv.lock`

R dependencies are managed using `renv` and are recorded in:

- `.Rprofile`
- `renv.lock`
- `renv/activate.R`

## Build instructions

Clone the repository:

```bash
git clone git@github.com:yuvrajwalia23/yuvrajwalia23.github.io.git
```

Move into the repository:

```bash
cd yuvrajwalia23.github.io
```

Restore the Python environment:

```bash
uv sync
```

Restore the R environment:

```bash
Rscript -e "renv::restore(prompt = FALSE)"
```

Render the complete Quarto website:

```bash
uv run quarto render
```

The rendered website will be created in the `docs/` directory.

To view the website locally, open:

```text
docs/index.html
```

in a web browser.

## Data

Both computational posts use the
[Palmer Penguins dataset](https://allisonhorst.github.io/palmerpenguins/),
which contains measurements of penguins observed in the Palmer Archipelago,
Antarctica.

The data were collected by Dr. Kristen Gorman and the Palmer Station Long Term
Ecological Research program and are available under the CC0 licence.

The dataset is provided through the `palmerpenguins` packages used by the
Python and R environments, so no separate data file needs to be downloaded or
committed to this repository.

Internet access is required when first running `uv sync` and
`renv::restore()` so that the required packages can be downloaded. Once the
environments have been restored, the computational posts use the dataset
included with the installed packages.

## Website output

Quarto is configured to write the rendered website to:

```text
docs/
```

The GitHub Pages site is published from this directory.