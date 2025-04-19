# Wav2Vec2 Embedding Model for Speech Representation

This repository contains code and documentation for working with the Wav2Vec2 model, a state-of-the-art self-supervised model developed for extracting rich speech representations from raw audio waveforms.

## 📁 Repository Structure

```
wav2vec2-embedding-model/
├── Wav2Vec2_ASR_Training.ipynb     # Jupyter notebook implementing Wav2Vec2 model
├── Wav2Vec2_Model_Overview.pdf     # Conceptual explanation and background of Wav2Vec2
```

## 🧠 Project Description

The goal of this project is to explore and implement the Wav2Vec2 model, including its application to speech recognition and representation learning. This includes:

- Understanding the architecture of the Wav2Vec2 model.
- Working with pre-trained models or training from scratch.
- Visualizing speech features and embeddings.
- Investigating performance on audio datasets.

## 📊 About the Data

The project uses the **Common Voice 11.0** English dataset by Mozilla, which is one of the largest open-source speech datasets suitable for ASR tasks.

- **Dataset Source**: `mozilla-foundation/common_voice_11_0` via Hugging Face Datasets
- **Streaming Mode**: Data is loaded using streaming to handle large datasets without full download
- **Sampling Rate**: All audio files are resampled to 16,000 Hz
- **Sample Sizes**:
  - Training: 1,500 samples
  - Testing: 300 samples
- **Persistence**: Once extracted, datasets are saved locally for reusability using Hugging Face’s `save_to_disk()` feature

## 📚 Resources

- Based on the Facebook AI Research paper: *"wav2vec 2.0: A Framework for Self-Supervised Learning of Speech Representations"*
- Hugging Face Transformers library is used for model loading and inference.
https://huggingface.co/blog/fine-tune-wav2vec2-english

