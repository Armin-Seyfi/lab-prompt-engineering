# Prompt Engineering Lab

**Track:** Module 2 — Prompt engineering · **When:** Week 2, Day 5 · **Status:** Required

This repository contains everything you need for this lab.

## Files

- [`instructions.md`](./instructions.md) — the lab instructions
- [`rubric.md`](./rubric.md) — how your submission is graded; this is what the AI reviewer checks your PR against

## How to complete this lab

1. **Fork** this repository.
2. Do the work described in `instructions.md`, committing to your fork.
3. Open a **pull request** back into this repository.
4. You'll receive **AI feedback** on your PR based on `rubric.md`. Address any blocking feedback and push updates to the same PR.

## Submission hygiene

- Keep this repository scoped to this lab only — no unrelated projects or personal files.
- Use clear, descriptive filenames.
- Remove secrets, API keys, and tokens before committing.

## My Lab Implementation

### Files

- `prompt_engineering_lab.ipynb`: prompt versions, repeated tests,
  failure analysis, task variations, and final evaluation.
- `lab_summary.md`: one-paragraph learning summary.
- `results/`: exported prompts, responses, evaluation data, and token usage.
- `.gitignore`: excludes local secrets and temporary files.

### How to Run

1. Use Python 3.11 with Jupyter support.
2. Install dependencies:
   ```bash
   python -m pip install openai python-dotenv ipykernel
   ```
3. Create a local `.env` file containing `OPENAI_API_KEY`.
   Do not commit this file.
4. Open `prompt_engineering_lab.ipynb` and select the Python environment.
5. Review cells before running them: API test cells incur costs.
   Saved outputs and the results export can be reviewed without new API calls.

### Evaluation

The notebook evaluates output format and factual correctness separately.
Product grounding is reviewed manually. Results on repeated baseline inputs
do not establish production readiness or broad generalization.