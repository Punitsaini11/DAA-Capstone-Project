# TextGuard — Plagiarism Detection Using String Matching Algorithms

## Project overview
TextGuard is a browser-based educational tool that compares two text documents using:
1. Naïve Pattern Matching
2. Rabin–Karp
3. Knuth–Morris–Pratt (KMP)

It creates fixed-length word phrases from Document A, searches for each phrase in Document B with each algorithm, and reports exact matches, reference-document word coverage, and measured execution time.

## Requirements
- A modern web browser (Chrome, Firefox, Edge, etc.)
- No Python, Node.js, packages, or internet connection required.

## How to run
1. Extract `Plagiarism_Detection_Capstone.zip`.
2. Open `index.html` in a web browser.
3. Paste text into Document A and Document B, or upload `.txt` files.
4. Select phrase length (4–7 words).
5. Click **Compare documents**.

## Project structure
- `index.html` — complete user interface and JavaScript implementation.
- `REPORT.md` — project report, methodology, algorithms, complexity and limitations.
- `samples/document_a.txt` and `samples/document_b.txt` — sample input files.

## Algorithm notes
- Naïve: checks every possible alignment character by character.
- Rabin–Karp: compares rolling hash values and verifies the text when hashes match.
- KMP: preprocesses the pattern into an LPS (Longest Prefix Suffix) table to avoid rechecking characters.

## Complexity
For text length n and pattern length m:
- Naïve: worst-case O(nm), extra space O(1).
- Rabin–Karp: average O(n+m), worst-case O(nm) due to hash collisions, extra space O(1) in this implementation.
- KMP: O(n+m), extra space O(m) for the LPS array.

The complete application searches multiple candidate phrases, so total runtime also depends on the number of unique phrases generated from Document A.

## Important limitation
This is an educational exact-match detector, not a production plagiarism checker. It does not understand paraphrasing, citations, meaning, or source ownership. Coverage is a simple phrase-overlap indicator and should not be treated as proof of plagiarism.
