# ASR fine-tuning: focus on Whisper and LoRA

## Overview

This notebook illustrate how to fine-tune the OpenAI Whisper models for automatic speech recognition (ASR) tasks using Low-Rank Adaptation (LoRA). The goal is to reduce computational requirements while maintaining or improving transcription accuracy on a specific language and domain.

## Requirements

* Python 3.10.12 or above
* `torch` 1.13 or above
* `transformers` 4.30 or above
* `peft` 0.4 or above
* `torchaudio` 0.13 or above
* Additional utilities: `numpy`, `pandas`, `matplotlib`, `datasets`

## Installation

```bash
pip install torch torchvision torchaudio transformers peft numpy pandas matplotlib datasets
```