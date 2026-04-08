# AGENTS.md

Project: ST311 course project on multi-label ECHR violation prediction under long-document constraints.

Objective:
Deliver a strong, defensible 10-page course paper with reproducible experiments.
Prioritize fast end-to-end execution over ambitious scope.

Core task:
- Dataset: AUEB-NLP/ecthr_cases
- Primary task: violation-prediction (multi-label)

Core experiment grid only:
1. TF-IDF + One-vs-Rest Logistic Regression on full text
2. bert-base-uncased with head truncation
3. nlpaueb/bert-base-uncased-echr with head truncation
4. bert-base-uncased with head+tail truncation
5. nlpaueb/bert-base-uncased-echr with head+tail truncation

Keep:
- head truncation as replication baseline
- head+tail as main document-access comparison
- silver rationales only for descriptive rationale-coverage analysis

Do not add unless explicitly requested:
- tail-only truncation
- chunking / hierarchical pooling
- BiGRU
- alleged-violation task
- attention interpretability
- SHAP / integrated gradients
- auxiliary rationale losses
- extra datasets

Metrics:
- validation micro-F1
- test micro-F1
- macro-F1
- subset accuracy
- per-label F1 for frequent labels
- runtime
- rationale coverage by strategy

Engineering rules:
- Code must run in Colab
- Do not use d2l
- No hardcoded secrets or tokens
- Prefer simple, robust implementations over clever ones
- Save configs, metrics, predictions, and plots to disk
- For each task, state files changed and how success was verified
- Save short progress notes to docs/status.md

Output locations:
- docs/ for plans, audits, and progress notes
- results/ for metrics, predictions, and tables
- reports/figures/ for final plots

Workflow to be followed for every addition: 
- Check if previous code is a repetition of any instruction given
- Write code(include in-line comments)
- run code (only new additions, not the whole notebook again unless explicitly asked)
- Write relevant comments, markdown below code cells explaining what the code is doing(if needed, what the results mean, why they are important, how they relate to next modelling choices and if required motivate the section)

Definition of done for any task:
- code runs
- outputs saved to disk
- brief note added to docs/status.md
- Always add relevant markdown and comments to the main notebook where changes are being made after every task to ensure that the notebook looks cohesive and presentable.
- Always look back at what's already been done in the notebook and whether the current task being asked/added is a repetition of that.

Additional Note: don't worry about working with data_explore_legal.ipynb, we only really used that for initial exploratory code, we can make new notebooks for the actual implementation/EDA tasks. 