# Fine-Tuning Llama 3.2 for Reliable JSON

This repository contains the setup for fine-tuning Llama 3.2 models to consistently output reliable JSON formats based on predefined schemas.

## Structure
- `data/`: Dataset storage (Add your JSON datasets here)
- `eval/`: Evaluation scripts and metrics
- `schema/`: JSON schema definitions
- `train.py`: Main fine-tuning script
- `requirements.txt`: Python dependencies
- `report.md`: Training reports
- `training_config.md`: Model hyperparameters and configs

## Setup
Install the necessary dependencies:

```bash
pip install -r requirements.txt
```

## Running the Training

Modify `train.py` to point to your specific dataset in `data/`, then run:
```bash
python train.py
```