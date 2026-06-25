# Probe-EM

Official implementation of **Probe-EM: Targeted Neuron Tracing via Training-Free Semantic Verification**.

This repository contains the tracing and semantic verification code. Update the paths in a local config file before running the pipeline.

## Setup

```bash
pip install -r requirements.txt
```

Probe-EM depends on SAM 2. Install SAM 2 and prepare the corresponding model config and checkpoint before running the pipeline.

See [INSTALL.md](INSTALL.md) for the environment setup used in our experiments.

## Configuration

Copy the example config and edit the paths:

```bash
cp config.example.json config.json
```

Key fields:

- `raw_path`: path or CloudVolume URL for the raw image volume.
- `seg_path`: path or CloudVolume URL for the segmentation volume.
- `checkpoint_sam`: path to the SAM 2 checkpoint.
- `model_cfg_sam`: SAM 2 model config path.
- `seed_ids`: seed segment IDs to trace.
- `seed_list_file`: optional text file with one seed ID per line.
- `output_root`: output directory for tracing results.

Use local paths such as `/path/to/...` or `file:///path/to/...`.

## Run

```bash
python run_parallel.py --config config.json
```

By default, the pipeline uses SAM 2 semantic verification.

## Notes

- Keep private paths in `config.json`; the tracked `config.example.json` only contains placeholders.
- Make sure the paper, CMT metadata, and repository link use the same project name: `Probe-EM`.
