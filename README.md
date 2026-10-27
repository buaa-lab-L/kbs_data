# TG-ResGCN Test100 dataset

[中文说明](README_zh.md) · [Data format](DATA_FORMAT.md)

This repository contains 100 frozen demand profiles for evaluating modular microreactor load-following control. The associated manuscript has not yet been published. At this stage, the public release is limited to the Test100 evaluation dataset. The complete research dataset and training code will be released after publication.

The training and validation profiles, trained model weights, training implementation, training logs, and internal research records are excluded from this package.

## Files

- `profiles/`: 100 NumPy `.npy` arrays, retained byte-for-byte from the frozen Test100 inputs.
- `manifest.json`: curve identifier, relative file path, full horizon `H`, SHA-256, and profile family.
- `DATA_FORMAT.md`: sampling, units, horizon convention and family counts.
- `MANIFEST.sha256`: integrity hashes for all package files except the hash list itself.
- `LICENSE`: the license notice copied unchanged from the existing dataset repository.

Each profile contains `H+1` samples at one-second intervals. Values are fractions of rated power. Evaluation uses all `H` control intervals; the final sample is the boundary value at time `H`. Horizons range from 200 to 433 seconds. All 100 profiles together contain 24,894 control intervals.

This package contains data and documentation only. It includes no implementation code, model checkpoints, or evaluation results. The original profile identifiers and family labels are retained to preserve dataset identity; they do not denote train/validation membership in this package. No generated replacement inputs are included.

The associated article remains under review; no publication DOI is assigned in this release. The existing repository license notice is preserved without changing its named copyright holder.
