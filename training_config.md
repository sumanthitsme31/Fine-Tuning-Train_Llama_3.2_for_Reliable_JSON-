# LlamaFactory Fine-Tuning Configuration

**Dataset:** `curated_train.jsonl`
**Base Model:** `Llama-3.2-3B-Instruct`
**Fine-tuning Method:** LoRA

## Hyperparameters & Justification

* **LoRA Rank (r):** `16`
  * *Justification:* A rank of 16 provides a good balance between parameter efficiency and learning capacity. Structured JSON extraction requires learning strict syntactic boundaries and key mappings, which rank 8 might struggle with, but rank 32 would unnecessarily increase memory overhead given our small dataset of 80 examples.
* **LoRA Alpha:** `32`
  * *Justification:* Standard practice dictates `alpha = 2 * rank`. This scaling factor ensures that the LoRA activations have a meaningful impact on the base model weights right from the start of training, stabilizing the learning process.
* **Learning Rate:** `2e-4`
  * *Justification:* A learning rate of `2e-4` is standard for LoRA fine-tuning on Llama models. It is small enough to prevent catastrophic forgetting of the base model's language capabilities, but large enough to adapt to the JSON schema constraints efficiently.
* **Epochs:** `4`
  * *Justification:* Given the small dataset size (80 examples), 2 epochs might underfit, while 5+ risks overfitting (memorizing specific vendor names). 4 epochs allows the model to see the varied layouts enough times to generalize the JSON structure.
* **Batch Size:** `4` (with gradient accumulation steps = 2)
  * *Justification:* Fits within typical 16GB/24GB VRAM constraints while providing an effective batch size of 8, ensuring stable gradient updates without running out of memory.

## Observations
The training loss curve started around 1.8 and smoothly descended, plateauing around 0.6 by the middle of epoch 3. No massive spikes were observed, indicating a stable learning rate.