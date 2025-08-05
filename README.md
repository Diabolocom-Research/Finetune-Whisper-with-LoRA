# Everything you need to know about fine-tuning an ASR: a focus on Whisper

Before we dive into the hands-on steps, it’s helpful to understand **what** Whisper is and **why** you might need to adapt it for your own audio data.

## What is Whisper?

Whisper is a widely used open-source `sequence‑to‑sequence` model that was trained to do **automatic speech recognition (ASR)**. It supports multiple tasks: **transcription**, **translation**, **language identification**, **silence detection** and **phrase-level timestamp prediction**. Despite its popularity, some of the technical details remain lesser-known, which can limit further contributions and innovation. For a detailed technical overview, see our Diabolocom blog post: <a href="https://www.diabolocom.com/research/whisper-explained/">Whisper explained</a></p>

## Why fine-tune Whisper?

ASR systems like OpenAI’s Whisper produce accurate transcriptions by leveraging a vast, multilingual training dataset of audio and transcripts. Nevertheless, the model's performance for individual languages remains closely tied to the language distribution within the original training data.

When your use case involves specialized vocabulary or languages that were underrepresented during pretraining, fine-tuning can make a significant difference. In particular, if your data diverges from Whisper’s original training set, whether in domain, audio characteristics, or speaker demographics, adapting the model to your specific dataset could yields notable reductions in `word error rate (WER)`.

To illustrate this need, we describe the procedure to fine-tune Whisper for Quebec French telephone speech.

## Installation

```bash
# Create and activate a virtual environment
conda create --name ASR python=3.10.12
conda activate ASR
```

1. Install PyTorch (select the appropriate CUDA version and operating system):
   [https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)

2. Install required Python libraries:

   ```bash
   pip install transformers peft numpy pandas matplotlib datasets
   ```
