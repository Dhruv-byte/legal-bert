# Status

## 2026-04-06
- Removed the hardcoded Hugging Face token from `data_explore_legal.ipynb`.
- Notebook authentication now reads `HF_TOKEN` from an environment variable or, in Colab, from a secret named `HF_TOKEN` via `google.colab.userdata`.
- Safe authentication going forward: set `HF_TOKEN` in your shell or add a Colab secret named `HF_TOKEN`; do not paste raw tokens into notebooks.
- Added `notebook_main.ipynb` as the clean, presentable EDA notebook with markdown headings, safe auth, non-interactive dataset loading, and commented analysis cells for token length and rationale position.
- Smoke-tested `notebook_main.ipynb` end-to-end and saved outputs back into the notebook.
- Expanded `Notebook_main.ipynb` for task 2 with dataset split inspection, label-structure and label-frequency audit, readable example records, and a generated audit file at `docs/dataset_audit.md`.
- Reworked `Notebook_main.ipynb` so the notebook itself is cohesive and presentable, adding interpretation markdown after each major exploration block to explain why the dataset findings matter for later modelling decisions.
- Rewrote the interpretation markdown in `Notebook_main.ipynb` so it now references the actual observed outputs and explains what the numbers mean, rather than using only generic implications.

## 2026-04-08
- Added `docs/experiment_table.md` with the fixed 5-system experiment grid, required metrics, expected run output filenames, final paper tables/figures, and short criteria for what would support or weaken the main claim.
- Updated the interpretation markdown in `Notebook_main.ipynb` so each main result section now includes a short motivation, a description of what the output shows, and a concise takeaway; also updated the TF-IDF baseline interpretation using the saved run outputs.
- Added brief inline comments to every code cell in `Notebook_main.ipynb` so each chunk now explains its purpose without changing the notebook flow or outputs.
- Expanded the TF-IDF baseline interpretation in `Notebook_main.ipynb` to explain which metrics matter most, how to read strong versus weak per-label F1 scores, and what improvements would count as meaningful for the later transformer runs.

## 2026-04-08
- Added sections 13 and 14 to `Notebook_main.ipynb` covering all four full BERT runs: `bert_head`, `legalbert_head`, `bert_head_tail`, `legalbert_head_tail`.
- Section 13 (head truncation) and Section 14 (head+tail truncation) each contain two run cells plus interpretation markdown.
- Added a shared utilities cell (cell 36) defining `head_tokenize`, `head_tail_tokenize` (255+255 token strategy), `run_bert_experiment`, `evaluate_model`, `compute_rationale_coverage`, and all artifact-saving helpers.
- `run_bert_experiment` trains for 3 epochs, selects the best checkpoint by validation micro-F1, and saves all required artifacts to `results/<run_id>/` (config, metrics, predictions, per-label F1, rationale coverage).
- Runs not yet executed — code written locally, to be run on Vertex AI Workbench (T4 GPU) via GitHub sync.
