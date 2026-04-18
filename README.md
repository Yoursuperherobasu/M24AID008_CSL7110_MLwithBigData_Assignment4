# M24AID008 — CSL7110 Assignment 4

**Course:** CSL7110 — Machine Learning With Big Data
**Topic:** Clustering and PageRank
**Author:** Basu Singh (M24AID008)
**Programme:** M.Tech — AI and Data Science, IIT Jodhpur

---

## Contents

| Path | What it is |
| --- | --- |
| `M24AID008_Assignment4.ipynb` | Single Jupyter notebook containing all three parts with executed outputs |
| `datasets/Q1_UCI_Spam_Clustering/` | UCI Spambase data (4601 points, 58 features) used for Part 1 |
| `datasets/Q2_WebSearch/` | Webpages folder, `actions.txt` and `answers.txt` used for Part 2 |
| `datasets/Q3_PageRank/` | `small.txt` and `whole.txt` graph edge lists used for Part 3 |

## What is inside the notebook

1. **Part 1 — Clustering**
   Hand-written Farthest First traversal and KMeans++ initialization on the Spambase dataset. Includes `readVectorsSeq`, `kcenter`, `kmeansPP`, `kmeansObj`, and the hybrid (kcenter → kmeans++) coreset experiment.

2. **Part 2 — Web Search**
   Inverted index built from scratch using a small `CompactSearchEngine` class. Supports `addPage`, `queryFindPagesWhichContainWord`, and `queryFindPositionsOfWordInAPage` exactly as described in the problem. Preprocessing follows the lowercase / punctuation-replace / connector-word / singular-plural rules given in the question.

3. **Part 3 — PageRank on PySpark**
   Iterative PageRank using PySpark RDDs, β = 0.8, 40 iterations. Duplicate directed edges removed with `RDD.distinct()`. Dangling-node mass redistributed uniformly. Validated on `small.txt` (top rank ≈ 0.036) before running on `whole.txt`.

## How to run

1. Clone this repository.
2. Open `M24AID008_Assignment4.ipynb` in Jupyter / VS Code.
3. Make sure `pyspark`, `numpy` and standard Python libraries are installed.
4. Run the cells top to bottom. The notebook reads the datasets from the `datasets/` folder that is shipped with this repo.

## Key outputs (reproduced from the executed notebook)

- **Part 1:** KMeans++ objective on full dataset = 30755.50; hybrid objective = 396289.18.
- **Part 2:** 379 unique indexed words; all 17 actions match `answers.txt`.
- **Part 3 (small graph):** highest PageRank = 0.035731 (matches the ~0.036 target).
- **Part 3 (whole graph):** top node 263 (0.002020); bottom node 558 (0.000329); sum of all ranks = 1.0.
