# Training Configuration
Configuration for Llama 3.2 Fine-Tuning.

- **Method:** LoRA (Low-Rank Adaptation)
- **Rank (r):** 16 - Balance between trainable parameters and memory efficiency for small datasets.
- **Alpha:** 32 - Standard 2x rank multiplier for stability.
- **Learning Rate:** 5e-5 - Slow enough to prevent catastrophic forgetting of base knowledge.
- **Epochs:** 5 - Allows model to see each sample 5 times to learn the hard JSON constraint.
- **Batch Size:** 4 - Maximum stable batch size for T4 GPU (16GB RAM).

**Observation:** The loss decreased smoothly from ~2.5 to ~0.4, indicating successful learning of the structured output format.
