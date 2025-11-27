# Data Cleaning Projects

Repository: ITM-AIR-Lab/Data-Cleaning-Projects

Short description
-----------------
A collection of reproducible data cleaning projects, patterns, utilities, and example pipelines maintained by the ITM-AIR Lab. This repository gathers typical data cleaning lessons, reusable functions, and demonstrative notebooks to help standardize and accelerate the process of preparing raw data for analysis and machine learning.

Goals
-----
- Provide reusable, well-documented examples of data cleaning workflows.
- Share robust utilities and patterns for common cleaning tasks (type coercion, missing data handling, deduplication, normalization, validation).
- Host reproducible notebooks that illustrate how to go from raw dataset to analysis-ready datasets.
- Serve as a reference and teaching resource for students and collaborators.


Important notes about data
--------------------------
- For reproducibility and to reduce repository size, large or sensitive raw datasets should NOT be checked in. Use `data/raw/` as a placeholder and provide instructions (in notebooks or docs) on how to obtain or generate data.
- Processed datasets in `data/processed/` should be deterministic outputs of the scripts/notebooks so other users can reproduce them from raw inputs.

Getting started
---------------
1. Clone the repository
   git clone https://github.com/ITM-AIR-Lab/Data-Cleaning-Projects.git
   cd Data-Cleaning-Projects

2. Create and activate a Python virtual environment (recommended)
   python3 -m venv .venv
   source .venv/bin/activate  # macOS / Linux
   .venv\Scripts\activate     # Windows (PowerShell)

3. Install dependencies
   - If the project uses Python:
     pip install -r requirements.txt
   - If the project uses R:
     See `docs/R-setup.md` (if present) or use `renv`/`packrat` instructions in project docs.

4. Reproduce an example notebook
   - Open a Jupyter environment:
     jupyter lab
   - Navigate to `notebooks/` and run `01-example-cleaning.ipynb` (or the first notebook listed).

Utilities and recommended patterns
---------------------------------
- Keep transformations small and well-tested: prefer many small functions that do one job.
- Separate data validation from transformation steps:
  - Validation should raise clear, actionable errors.
  - Transformation functions should be deterministic and idempotent where possible.
- Use column-level typing maps and a canonical schema file (e.g., `schema/` or YAML/JSON) to maintain consistent data types across datasets.
- Favor compact, efficient on-disk formats like Parquet for processed data.
- Always log provenance metadata: source filename, script version/commit hash, parameters, timestamp.

Testing and CI
--------------
- Tests for cleaning utilities live in `tests/`. Run tests with:
  pytest
- CI workflows (in `.github/workflows/`) should run tests and optionally validate notebooks with `nbconvert` or `papermill`.

Contributing
------------
Contributions are welcome. Please follow this recommended workflow:
1. Fork the repository and create a feature branch.
2. Add/fix code in `src/`, notebooks in `notebooks/`, or examples in `examples/`.
3. Add tests for new utilities or changes.
4. Update docs where applicable.
5. Submit a pull request describing the change and linking any relevant issues.

See CONTRIBUTING.md for detailed contributor guidelines, code style, and branch naming conventions.

Code style
----------
- Python: follow PEP 8 (use black/isort/flake8 as configured).
- R: follow tidyverse style (if R code is present).
- Document functions and modules with docstrings and examples where helpful.

License
-------
This repository includes a LICENSE file. If none exists yet, consider applying an open-source license such as MIT, BSD-3-Clause, or Apache-2.0. Add a LICENSE file at the repository root and update this section accordingly.

Security and data sensitivity
-----------------------------
- Do NOT commit sensitive data (secrets, credentials, personal data).
- If you need to share datasets that include sensitive information, anonymize or use synthetic examples.

Contact and maintainers
-----------------------
Maintained by the ITM-AIR Lab contributors. For questions, open an issue or contact the maintainers listed in the repository.

Acknowledgements
----------------
This repository was created to collect teaching examples, patterns, and utilities around data cleaning at the ITM-AIR Lab. Contributions from students, researchers, and collaborators are appreciated.

Template placeholders
---------------------
This README is intentionally general. Please update:
- The repository description at the top,
- Any example script names to match actual files,
- Dependency and Python/R setup instructions to reflect the project's real configuration,
- License and maintainer contact information.

Happy cleaning!
