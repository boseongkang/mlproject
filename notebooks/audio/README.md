## Part 2 — Audio Analysis 🎧 Geonho Lee

This part focuses on extracting **audio-based features** from Billboard Hot 100 songs using WAV files.  
Our goal is to capture **instrument / timbre characteristics** (e.g., bass / vocal / cymbal dominance) and build a feature table that can later be combined with lyric features for prediction models.

To actually run the code in a new environment, quite a few parts (such as the sections related to wav_path) need to be commented out. I left them in the script so that we could still see the outputs from the final run. If all the commented cells are uncommented and the WAV file exist, the entire notebook will run without any issues. However, we cannot upload the WAV files here due to legal reasons.

All the steps required by the rubric are included in a single notebook.

---

###  Goal

- Quantify frequency–domain characteristics of each track  
- Summarize them into a **single row per song** (CSV / DataFrame)  
- Use these features to explore **“Top 30 vs. non–Top 30”** prediction with simple ML models

All experiments in this part are implemented in **`Audio_Analysis.ipynb`** using **pre-computed CSV files**  
(`audio_features_100songs.csv`, `audio_features_audio2.csv`), so the notebook can be run without the original WAV files.

---

###  Files in this folder

- `Audio_Analysis.ipynb` – main notebook for audio feature extraction and ML experiments  
- `audio_features_100songs.csv` – features for 100 training songs  
- `audio_features_audio2.csv` – features for an additional set of songs (used for later experiments)  
- `audio_wav/`, `audio_wav_2/` – placeholder folders for the original WAV files (not required to run the notebook)  

---

###  Processing Pipeline (per WAV file)

For each WAV file, the pipeline performs:

1. **Load WAV**
   - Read raw audio waveform and sample rate.

2. **Stereo → Mono**
   - Convert 2-channel audio into a single mono channel for consistent analysis.

3. **Normalization**
   - Scale amplitudes to the range **[-1, 1]** to stabilize comparisons across tracks.

4. **Waveform Visualization**
   - Plot the normalized waveform (usually the first few seconds) as a **sanity check**.

5. **Spectrogram / Frequency Analysis**
   - Convert the waveform into a **time–frequency representation** using STFT / spectrogram.

6. **Band Energy Ratios**
   - Compute energy proportions across three frequency bands:
     - **Bass (low)**
     - **Mid / Vocal (mid)**
     - **High / Cymbal (high)**
   - These ratios approximate dominant instrument / timbre ranges.

7. **Feature Aggregation**
   - Extract summary statistics (band ratios + MFCC means/stds, etc.).
   - Store one feature vector per song → **DataFrame / CSV (one row per track)**.

---

###  ML Experiments (short summary)

Using the aggregated audio features:

- We train **Logistic Regression** and **Random Forest** models  
- Target: a manually defined **`top30`** flag (our own Top-30 list, not true Billboard labels)
- The results show:
  - Audio features contain **some predictive signal**, especially in timbre-related stats  
  - But audio-only information is **not sufficient** for reliable Top-30 prediction  
  - This motivates combining audio with **lyrics and other metadata** in later parts

---

###  How to run

1. Open `Audio_Analysis.ipynb`.
2. Make sure `audio_features_100songs.csv` and `audio_features_audio2.csv` are in the **same folder**.
3. Run the notebook from top to bottom (`Run all`).  
   - The notebook uses the pre-computed CSVs, so it does **not** require the original WAV files to be present.

