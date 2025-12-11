Data Expansion (From Text to Audio)
Lyrics only contain the message of a song. However, the musical atmosphere is also crucial for a hit song. We broadened the model's perspective by collecting additional audio features such as MFCC (timbre) and Frequency Ratios (energy across different frequency bands).

Technical Challenges in Data Engineering (Robust Preprocessing)
Combining data from different sources (Billboard vs. Spotify) resulted in many missing values ​​due to differences in naming conventions (e.g., "feat." vs. "featuring"). To address this, we applied normalization and string matching algorithms to minimize data loss.

Modeling Strategy (Random Forest)
This is a complex dataset mixing lyrical data (sparse vectors) and audio data (continuous numerical values). To effectively capture the non-linear relationships between these heterogeneous data types and prevent overfitting, we adopted the Random Forest Classifier. As a result, we achieved improved accuracy (approximately 85%) compared to a model using only lyrics.

Real-World Validation (Model in Action)
We didn't just rely on test set scores. We tested the model on the latest hit songs from 2023-2024 that were not used in training. The model accurately predicted that these songs had a high probability of becoming hits. This proves that our model didn't simply memorize past data but generalizes well  the formula for successful songs.

Furthermore, we plan to upload a function to this GitHub repository that allows users to input their own WAV files and lyrics to predict song rankings.
