# Installation

These steps reproduce the environment used for Probe-EM. Adjust the CUDA and
PyTorch versions to match your machine.

## Conda Environment

```bash
conda create -n ntracing python=3.10.18
conda activate ntracing
```

## PyTorch

For CUDA 12.4:

```bash
pip install torch==2.6.0 torchvision==0.21.0 torchaudio==2.6.0 --index-url https://download.pytorch.org/whl/cu124
```

For other CUDA versions, install the matching PyTorch build from the official
PyTorch instructions.

## SAM 2

Install SAM 2 from your local clone or from the official repository, then make
sure its config files and checkpoints match the paths in `config.json`.

```bash
cd /path/to/sam2
pip install -e .
```

## Probe-EM Dependencies

From this repository:

```bash
pip install -r requirements.txt
```

## Configuration

```bash
cp config.example.json config.json
```

Edit `config.json` and set local paths for `raw_path`, `seg_path`,
`checkpoint_sam`, and other output paths.
