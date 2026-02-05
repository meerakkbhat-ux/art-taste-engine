# Art Taste Engine (Art-Tech Recommender + Insights)

If I were to build an AI art-tech startup, I’d start with taste: map visual style, segment it, and personalize discovery fast.

This project builds a lightweight “taste engine” for art prints:
- maps artworks into a 2D taste space (similar visuals sit closer),
- clusters styles into interpretable segments,
- recommends art from a few likes,
- evaluates feed quality with product-style metrics (stability, browseability, diversity, near-duplicates).

---

## Dataset
**Source:** Cleveland Museum of Art (CMA) Open Access API  
**Images downloaded:** 1,378 (print/poster-like focus)

---

## What I built (high level)
- **Feature extraction (10 traits/image):** color, contrast, edge/linework, sharpness (and related stats)
- **Taste map:** t-SNE visualization of visual similarity
- **Clustering:** 18 clusters → grouped into **6 macro style segments**
  - Muted Soft (Low-Contrast)
  - Vibrant Soft (Low-Contrast)
  - Muted Linework (Low-Contrast)
  - Vibrant Linework (Low-Contrast)
  - Monochrome Linework (High-Contrast)
  - Muted Linework (High-Contrast)
- **Personalization:** “like ~3 artworks → taste fingerprint → recommendations”
- **Insights metrics (product-style):**
  - **Browseability:** which clusters feel cohesive vs noisy while scrolling
  - **Stability:** how quickly recommendations stop changing as likes increase  
    Sample run: J(1→3)=0.37, J(3→5)=0.66, J(1→5)=0.32
  - **Recommender dashboard:** diversity, near-duplicates, match strength, within-segment rate

---


---

## Results (LinkedIn visuals)
The final visuals are in: `outputs/linkedin/`
- Taste Map (t-SNE)
- Cluster moodboards
- Personalized taste profile
- Stability chart
- Taste fingerprint card
- Recommender insights dashboard

---

## How to run
### 1) Install
```bash
pip install -r requirements.txt

