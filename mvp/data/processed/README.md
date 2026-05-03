# Processed Recipe Data

Put normalized recipe files here after validation.

Current main offline dataset artifacts:

- `recipenlg-full-20260416T0625Z.json`
- `recipenlg-full-20260416T0625Z.stats.json`
- `recipenlg-full-20260416T0625Z.checkpoint.json`
- `recipenlg-deployment/manifest.json`
- `recipenlg-deployment/recipes-0001.json` through `recipes-0006.json`

Verified full-import counts for the current main dataset:

- `raw_count`: `2231142`
- `accepted_count`: `23021`
- `written_count`: `23021`
- `rejected_count`: `2208121`

Recommended organization:

- store deterministic exports only
- keep file formats simple for the MVP, such as JSON or JSONL
- partition by source or batch once the dataset grows

Runtime priority:

- prefer the local single-file full dataset when it exists
- otherwise load the tracked sharded deployment corpus
- otherwise fall back to the built-in sample dataset

Examples:

- `mvp/data/processed/recipes.normalized.json`
- `mvp/data/processed/demo-source/recipes-0001.jsonl`
