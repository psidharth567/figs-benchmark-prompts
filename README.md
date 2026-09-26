# FIGS: Prompt Materials

This repository contains the complete, verbatim prompts used to build and evaluate the FIGS benchmark (Sycophancy / Calibrated Validation axes), released as supplementary material for an anonymous ICLR 2027 submission.

## Contents

### `system_prompts/`
System prompts used by the assistant under test.

- `baseline.txt` — the baseline assistant system prompt.
- `factual.txt` — the factual assistant system prompt.
- `optimal.txt` — the optimal (calibrated) assistant system prompt.

### `judge_prompts/`
Prompts used by the LLM judge. Each axis (Sycophancy, Calibrated Validation) uses a two-pass pipeline: a Pass 1 prompt that assigns a score, and a Pass 2 prompt that tags the rule(s) responsible for that score without changing it.

- `sycophancy_score_pass1.txt` — Pass 1 sycophancy scoring prompt.
- `sycophancy_rule_pass2.txt` — Pass 2 sycophancy rule-tagging prompt.
- `calibrated_validation_score_pass1.txt` — Pass 1 calibrated-validation scoring prompt.
- `calibrated_validation_rule_pass2.txt` — Pass 2 calibrated-validation rule-tagging prompt.
- `worked_examples.txt` — abridged rule-example transcripts referenced by the judge prompts.

### `generation_prompts/`
Prompts used to build the benchmark scenarios (Section "Generation prompts" in the paper). The scenario-authoring prompts (generator, refiner, revision, user simulator, transcript auditor) are assembled at runtime from templates plus per-sample fields, so each is included here as a fully rendered example on one frozen sample per axis rather than as a bare template.

- `rendered_examples/sycophancy_example/` — the five authoring-stage prompts (`1_scenario_generator.txt` … `5_transcript_auditor.txt`) as rendered for one frozen sycophancy sample.
- `rendered_examples/calibrated_validation_example/` — the same five stages rendered for one frozen calibrated-validation sample.
- `expansion/expansion_prompt.txt` — the scenario-plan expansion template (Section "5. Expansion"), with its `{plan}`/`{role}`/`{rule}`/`{arch}` placeholders unfilled.

## Note

This repository is released anonymously for double-blind review. Please access it via the anonymized link provided in the paper rather than this repository's direct URL.
