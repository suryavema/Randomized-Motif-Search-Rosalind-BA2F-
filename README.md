# Randomized Motif Search (Rosalind BA2F)

Implementation of the **Randomized Motif Search** algorithm for motif discovery in DNA sequences, following the Rosalind Bioinformatics Stronghold problem BA2F.

## Problem
Given:
- `k` — length of the motif to search for.
- `t` — number of DNA strings.
- `t` DNA strings of equal length.

Task: Find a set of `t` motifs (one from each string) that minimizes the score — i.e., the sum of Hamming distances to the consensus string.

## Algorithm
**Randomized Motif Search**:
1. Pick a random `k`-mer from each DNA string → initial motifs.
2. Build a profile with Laplace smoothing from motifs.
3. Select the profile-most probable `k`-mer from each DNA string.
4. If the new set scores lower than the best so far, update best motifs.
5. Repeat until no improvement.
6. Iterate multiple times (e.g., 1000 restarts) to reduce local optima risk.

## Files
- `code.py` — Python implementation with:
  - `random_motifs` — picks a random `k`-mer from each DNA string.
  - `create_profile` — builds a profile matrix with Laplace smoothing.
  - `profile_most_probable` — finds the profile-most probable k-mer.
  - `find_consensus` — derives consensus string.
  - `score` — computes score of a motif set.
  - `iterate_randomized_motif_search` — runs the randomized search for many iterations.
- `rosalind_ba2f.txt` — example input: `k t` then `t` DNA strings.
