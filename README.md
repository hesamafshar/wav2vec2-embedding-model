# Wav2Vec2 for Speech Recognition

This project started from reading the original Wav2Vec 2.0 paper and trying to understand how its self-supervised speech representations could be used for automatic speech recognition in practice.

After reading the paper, I looked for an accessible speech dataset with a similar setting and used the English part of Mozilla Common Voice 11.0. Because of the available computational resources, I worked with a smaller subset of 1,500 training samples and 300 test samples instead of trying to reproduce the large-scale experiments from the paper.

I prepared the audio and transcripts, resampled the recordings to 16 kHz, and fine-tuned `facebook/wav2vec2-base-960h` with a CTC objective. I then evaluated the model on the held-out test set using Word Error Rate (WER). The purpose was to implement the method on a new accessible dataset and understand the training and evaluation process, not to match the full benchmark numbers reported in the original work.

## Repository files

- `Wav2Vec2_ASR_Training.ipynb` -- data preparation, Wav2Vec2 fine-tuning, and WER evaluation
- `Wave to vector embedding models.pdf` -- my report and technical overview of the model

## Data

The notebook uses `mozilla-foundation/common_voice_11_0` through Hugging Face Datasets. Streaming was used to load a manageable subset of the original dataset, and the processed samples were saved locally for reuse during the experiments.

## Reference

A. Baevski, H. Zhou, A. Mohamed, and M. Auli, *wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations*.
