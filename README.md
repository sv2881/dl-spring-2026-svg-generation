# DL Spring 2026: Text-to-SVG Generation Baseline

This repository packages the current Kaggle baseline notebook and an ACL-style report draft for the NYU Tandon Deep Learning Spring 2026 text-to-SVG competition.

The notebook implements a validity-first baseline built around:

- `Qwen/Qwen2.5-1.5B-Instruct`
- 4-bit loading when GPU is available
- LoRA fine-tuning on the provided `train.csv`
- SVG repair and validation utilities
- TF-IDF retrieval fallback for malformed generations
- Kaggle-ready `id,svg` submission creation

## Repository Layout

- `notebooks/qwen_lora_text_to_svg_baseline.ipynb`: cleaned notebook with the current end-to-end pipeline
- `report/main.tex`: ACL-style report draft
- `report/references.bib`: bibliography for the report
- `requirements.txt`: core Python dependencies used by the notebook

## Notebook Summary

The saved notebook outputs show:

- training data rows: `50,000`
- test data rows: `1,000`
- filtered usable rows: `50,000`
- sampled training split: `8,000`
- sampled validation split: `425`
- hardware used in the saved run: `Tesla T4`
- inference time for 1,000 prompts: `57.32` minutes
- SVG validity rate on the generated submission: `100%`

The qualitative examples in the saved notebook outputs show repeated fallback SVGs, so this should be treated as a reproducible baseline rather than a strong final model.

## Running on Kaggle

1. Upload the notebook to a Kaggle Code Competition notebook.
2. Attach the competition dataset containing `train.csv`, `test.csv`, and `sample_submission.csv`.
3. Enable a GPU accelerator.
4. Run the notebook end to end.
5. Submit the generated `submission.csv` through Kaggle Code Submission.

## Reproducibility Notes

- The notebook fixes `random`, `numpy`, and `torch` seeds to `42`.
- The current report draft is honest about what was observed in the notebook and where more ablations are still needed.
- Add your final Kaggle leaderboard score and model-weight link before report submission.
