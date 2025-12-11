## Part 1: Boseong Kang

**Automated Data Collection:** We developed a script using the billboard.py library to automatically scrape and compile Billboard Hot 100 charts over 24 years (2000-2023), building a dataset consisting of over 28,000 entries.<br>

**Strategic Data Integration:** To overcome copyright restrictions and API limitations encountered when directly scraping lyrics, we utilized a high-quality "Billboard Hot 100 Data with Features" dataset available on Kaggle.<br>

**Data Alignment and Cleaning:** We implemented a robust data merging pipeline.<br>
By applying string normalization techniques, we addressed title/artist inconsistencies between the scraped Billboard data and the Kaggle dataset (e.g., differences between 'feat' and 'featuring'), ensuring accurate mapping of lyric data and ranking data.<br>

**Modeling Strategy (Random Forest)** This is a complex dataset mixing lyrical data (sparse vectors) and audio data (continuous numerical values).<br>
To effectively capture the non-linear relationships between these heterogeneous data types and prevent overfitting, we adopted the Random Forest Classifier.<br>
As a result, we achieved improved accuracy (approximately 85%) compared to a model using only lyrics.

**Real-World Validation (Model in Action)** We didn't just rely on test set scores.<br>
We tested the model on the latest hit songs from 2023-2024 that were not used in training.<br>
The model accurately predicted that these songs had a high probability of becoming hits.<br>
This proves that our model didn't simply memorize past data but generalizes well the formula for successful songs.

## Future Roadmap<br>
Plan to deploy a user-interactive feature allowing users to upload their own WAV files and lyrics to predict potential Billboard rankings.
