# Yoga Asana Recommendation System (NLP)

An NLP-based recommendation system that suggests the most relevant yoga asanas for a user's health concerns. The user enters a few words describing their problem or goal (for example *back pain*, *stress*, *digestion*, *flexibility*), and the model returns the **top 7 asanas**, ranked by how well their benefits match the input.

*Summer project (May 2022 – Jul 2022) under the supervision of **Prof. Veena Bansal**, Department of Industrial and Management Engineering, IIT Kanpur.*

---

## Motivation

Yoga is widely recognised for its physical and mental health benefits, from lowering resting heart rate to improving endurance and reducing stress. However, people looking for asanas that address a specific health problem rarely have a reliable, structured way to find them. This project builds that bridge: a system that maps everyday health-related keywords to the asanas most likely to help, while keeping track of contraindications.

## Approach

### 1. Data scraping and curation
No ready-made structured dataset of yoga asanas existed, so we built one.
- Scraped asana information from online yoga resources using Python-based scraping scripts.
- Supplemented and cross-verified the scraped data against established yoga books to ensure accuracy.
- Cleaned and standardised everything into a structured dataset of **329 asanas**, each with four fields: **benefits**, **contraindications**, **description**, and **procedure**.

### 2. Text preprocessing
- Word tokenization and lowercasing.
- Stop-word removal using the **Gensim** library.
- Normalisation of the benefit text so that related health terms map consistently.

### 3. Word embeddings
- Converted text into numerical vectors using **one-hot encoding** and **Word2Vec**, so that semantically similar health terms (e.g. *anxiety* and *stress*) sit close together in vector space.

### 4. Recommendation model
- A feed-forward **neural network** takes the embeddings of the user's input words as context.
- It outputs a probability for each asana, and the system returns the **top 7** in decreasing order of match probability.

## Tech Stack

| Area | Tools |
|------|-------|
| Language | Python |
| Data collection | Web scraping, manual curation from yoga books |
| NLP | Gensim, Word2Vec, one-hot encoding |
| Modelling | Neural networks (TensorFlow / Keras) |
| Data handling | Pandas, NumPy |

## Example

```
Input:  back pain, posture, flexibility, stress
Output: Top 7 recommended asanas, ranked by match probability
```

## Future Work
- Use contraindications to filter out unsafe asanas for users with specific conditions.
- Replace Word2Vec with transformer-based sentence embeddings for better semantic matching.
- Wrap the model in a simple web interface or REST API.

## Acknowledgements
I am grateful to **Prof. Veena Bansal**, Department of Industrial and Management Engineering, IIT Kanpur, for her guidance and encouragement throughout the project, and to my project partner **Richa Prakash Sachan** for her collaboration.
