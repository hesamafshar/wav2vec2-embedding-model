# Wav2Vec2 for Speech Recognition

This project started from reading the original Wav2Vec 2.0 paper and trying to understand how its self-supervised speech representations can be used for automatic speech recognition in practice.

After reviewing the model, I looked for an accessible speech dataset with a similar setting and used the English part of Mozilla Common Voice 11.0. Because of the available computational resources, I worked with a smaller subset of 1,500 training samples and 300 test samples instead of trying to reproduce the large-scale experiments from the paper.

I prepared the audio and transcripts, resampled the recordings to 16 kHz, and fine-tuned `facebook/wav2vec2-base-960h` with a CTC objective. The model was then evaluated on the held-out test set using Word Error Rate (WER). The goal here was mainly to go through the complete implementation and evaluation pipeline after studying the paper, rather than to match the full benchmark results reported for Wav2Vec2.

## Repository files

- `Wav2Vec2_ASR_Training.ipynb` -- data preparation, Wav2Vec2 fine-tuning, and WER evaluation
- `Wave to vector embedding models.pdf` -- my report and technical overview of the model

## Data

The notebook uses `mozilla-foundation/common_voice_11_0` through Hugging Face Datasets. Streaming was used to load a manageable subset of the original dataset, and the processed samples were saved locally for reuse during the experiments.

## Reference

A. Baevski, H. Zhou, A. Mohamed, and M. Auli, *wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations*.
