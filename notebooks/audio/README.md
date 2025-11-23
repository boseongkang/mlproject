# Part 2 — Audio Analysis

## Goal
This part focuses on extracting audio based features from Billboard Hot 100 songs using WAV files.  
The goal is to quantify instrument related frequency characteristics (e.g., bass / vocal / cymbal dominance) and prepare audio features that can later be combined with lyric features for Top 10 prediction.

---

## What This Part Does

For each WAV file, the pipeline:

### 1. Load WAV
- Read audio waveform and sample rate.

### 2. Stereo → Mono
- Convert 2-channel audio into a single mono channel for consistent analysis.

### 3. Normalization
- Scale amplitudes to the range **[-1, 1]** to stabilize comparisons across tracks.

### 4. Waveform Visualization
- Plot the normalized waveform (usually first few seconds for sanity check).

### 5. Spectrogram / Frequency Analysis
- Convert waveform into a time-frequency representation (STFT / spectrogram).

### 6. Band Energy Ratios
Compute energy proportions across frequency bands:
- **Bass (low)**
- **Mid / Vocal (mid)**
- **High / Cymbal (high)**

These ratios approximate dominant instrument ranges.

### 7. Feature Aggregation
- Store extracted audio features into a table (DataFrame/CSV), one row per song.

