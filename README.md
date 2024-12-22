# Arabic Text-to-Speech (TTS) Fine-Tuning

## Overview
This repository showcases a comprehensive methodology for fine-tuning high-quality Arabic Text-to-Speech (TTS) models, with a focus on Egyptian Arabic while supporting multiple dialects. By leveraging data sourced from YouTube and using advanced tools and models, the project aims to enhance the naturalness, clarity, and expressiveness of Arabic speech synthesis.

---

## Features
- **Data Collection and Preprocessing**:
  - Scraped over 360 YouTube videos, focusing on diverse Arabic dialects and tones.
  - Preprocessed audio data using tools like `Spleeter`, `noisereduce`, and `audioop` for vocal isolation, noise reduction, and volume normalization.
  - Generated transcriptions with OpenAI's Whisper model and performed diacritic restoration using the Shakkelha model.

- **Text Normalization and Alignment**:
  - Restored diacritics using deep learning models for proper pronunciation.
  - Aligned phonemes using Buckwalter transliteration for better compatibility with TTS models.

- **Model Fine-Tuning**:
  - Fine-tuned Tacotron2 and FastPitch models on a curated dataset.
  - FastPitch achieved significant improvements with a Mel Cepstral Distortion (MCD) score of 28.39 after 40 epochs.

---

## Pipeline
1. **Data Collection**:
   - Scraped YouTube videos using `yt_dlp`.
   - Filtered relevant content using keywords and metadata analysis.

2. **Audio Preprocessing**:
   - Standardized audio to WAV format.
   - Isolated vocals and reduced noise.
   - Normalized volume and resampled audio to 22050 Hz.

3. **Transcription and Cleaning**:
   - Generated transcriptions using OpenAI Whisper.
   - Removed duplicates, special characters, and non-Arabic text entries.

4. **Feature Extraction**:
   - Extracted Mel spectrograms for TTS model training.

5. **Model Training**:
   - Fine-tuned Tacotron2 and FastPitch models with hyperparameter optimization.
   - Evaluated using MCD scores and subjective assessments of naturalness and clarity.

---

## Results
- **Tacotron2**:
  - Moderate naturalness and clarity but higher MCD values.
  - Training Loss: 2.9477
  - Validation Loss: 2.5164

- **FastPitch**:
  - Achieved the best naturalness and clarity at 40 epochs.
  - Training Loss: 8.0657
  - MCD: 28.39

---

## Tools and Libraries
- `yt_dlp`: Video scraping
- `pydub`: Audio slicing and format conversion
- `Spleeter`: Vocal isolation
- `noisereduce`: Noise suppression
- `audioop`: Volume normalization
- OpenAI Whisper: Transcription
- Shakkelha: Diacritic restoration
- Buckwalter Transliteration: Phoneme alignment

---

## Additional Resources
- [Phase 1 Notebook on Kaggle](https://www.kaggle.com/code/ahmedgamal7207/speech-recognition-final-project-phase-1)
- [Phase 2 Notebook on Google Colab](https://colab.research.google.com/drive/1YcWolHvDoaSOerPXoHHCT92dcc6isOOj?usp=sharing)
- [Pretrained Models](https://drive.google.com/drive/folders/1ZYkN4HBZZHe9w454fRzQtOAoZcdNdbDM?usp=sharing)
- [Preprocessed Datasets and Mel Spectrograms](https://drive.google.com/drive/u/1/folders/1rjuq0GPBB7itnwfkqHBcWJDQtL9figS9)
- [Final Models](https://drive.google.com/drive/folders/1eePoZZf1My8UQoZQFKrU_5vAQXHVw5xQ?usp=sharing)
- [Kaggle Dataset (Before Tacotron2 Processing)](https://www.kaggle.com/datasets/ahmedgamal7207/final-egyptian-arabic-youtube-videos)



