# Audio-quality-enhancement-and-noise-cancellation-Audio-translation-using-Audio-processing

# Task 1: Audio Quality Enhancement and Noise Cancellation

## Short-Time Fourier Transform (STFT)
- Compute the STFT of the audio signal, transforming it into the frequency domain over short time intervals.
- Extract both the magnitude and phase using `np.abs()` and `np.angle()` functions.

## Noise Profile Creation
- Load the noisy audio and calculate its STFT and magnitude.
- Compute the average magnitude along `axis=1` to create a noise profile.
- This profile helps identify and remove noise.

## Hyperparameter Adjustment
- Multiply the noise profile array by a hyperparameter (alpha).
- Experiment with different alpha values (starting with 2) to fine-tune results.

## Audio Denoising
- Subtract the mean noise array from the original audio.
- Ensure any negative values in the resulting array are replaced with 0.
- This step effectively reduces noise.

## Incorporating Phase Information
- Multiply the modified audio by the complex exponential of the phase information obtained in step 3 (using `np.exp(1.0j * phase)`).

## Inverse Short-Time Fourier Transform (ISTFT)
- Reconstruct the audio by performing ISTFT on the modified signal using librosa.
- Save the resulting denoised audio file.

# Task 2: Audio Translation using Audio Processing

## Whisper Inference for Text Extraction
- Utilized whisper inference to extract text from an audio file.
- Whisper is a powerful tool for automatic speech recognition (ASR) that converts spoken language into written text.

## Translation Using deep_translator Library
- Employed the deep_translator library to translate the extracted text into another language.
- This library provides seamless integration with various translation services.

## gTTS (Google Text-to-Speech) System
- Leveraged the gTTS system to generate audio from the translated text.
- gTTS converts written text into natural-sounding speech using Google’s Text-to-Speech API.
