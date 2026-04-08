# Experiment Table

This document fixes the exact experiment scope for the paper. It stays within the 5-system grid defined in `Agents.md`.

## 1. Exact Experiment Grid

| run_id | system | encoder / model | document access |
| --- | --- | --- | --- |
| `tfidf_ovr_fulltext` | TF-IDF + One-vs-Rest Logistic Regression | sparse TF-IDF features | full concatenated facts |
| `bert_head` | BERT baseline | `bert-base-uncased` | first 512 tokens |
| `legalbert_head` | Legal-BERT baseline | `nlpaueb/bert-base-uncased-echr` | first 512 tokens |
| `bert_head_tail` | BERT + improved access | `bert-base-uncased` | 256 head + 256 tail tokens |
| `legalbert_head_tail` | Legal-BERT + improved access | `nlpaueb/bert-base-uncased-echr` | 256 head + 256 tail tokens |

## 2. Metrics To Report For Each System

Report these for every run:
- `val_micro_f1`
- `test_micro_f1`
- `test_macro_f1`
- `test_subset_accuracy`
- `test_per_label_f1_frequent`
- `runtime_seconds`
- `rationale_coverage`

Note: `rationale_coverage` is a descriptive document-access metric tied to the input strategy. It should still be reported alongside each run for consistency.

## 3. Expected Output Files Per Run

Each run writes to `results/<run_id>/` with the same filenames:
- `results/<run_id>/config.json`
- `results/<run_id>/metrics.json`
- `results/<run_id>/val_predictions.csv`
- `results/<run_id>/test_predictions.csv`
- `results/<run_id>/per_label_f1.csv`
- `results/<run_id>/rationale_coverage.json`

Expected run directories:
- `results/tfidf_ovr_fulltext/`
- `results/bert_head/`
- `results/legalbert_head/`
- `results/bert_head_tail/`
- `results/legalbert_head_tail/`

## 4. Final Paper Figures and Tables

Include these in the paper:
- `Table 1`: main 5-system results table with `test_micro_f1`, `test_macro_f1`, `test_subset_accuracy`, and runtime
- `Table 2`: per-label F1 for the frequent labels only
- `Figure 1`: training-case token-length distribution with the 512-token cutoff marked
- `Figure 2`: silver-rationale position or rationale-coverage figure comparing `head` vs `head+tail`

## 5. Result Patterns To Watch

Patterns that support the main claim:
- `head+tail` outperforms `head` for both BERT and Legal-BERT
- Legal-BERT is at least as good as BERT under the same access strategy
- rationale coverage is clearly better for `head+tail` than for `head`

Patterns that weaken the main claim:
- little or no gap between `head` and `head+tail`
- Legal-BERT does not improve over BERT in a stable way
- better rationale coverage does not line up with any performance improvement
