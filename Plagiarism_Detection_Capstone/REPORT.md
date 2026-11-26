# Capstone Project Report
## Plagiarism Detection Using String Matching Algorithms

**Project name:** TextGuard  
**Project type:** Data Structures and Algorithms  
**Algorithms:** Naïve Pattern Matching, Rabin–Karp, Knuth–Morris–Pratt (KMP)

## 1. Introduction
Plagiarism detection can help identify text that is repeated between documents. This project demonstrates how string-matching algorithms can locate exact matching phrases in two text documents and compares their execution time.

## 2. Problem statement
Develop a plagiarism detection system that identifies matching words or patterns between two text documents. Implement Naïve Pattern Matching, Rabin–Karp, and KMP, then compare the algorithms based on execution time, pattern length, and document size.

## 3. Objectives
- Accept two text documents from the user.
- Generate fixed-length phrases from the reference document.
- Search for each phrase in the second document using three algorithms.
- Display matching phrases and their character positions.
- Estimate reference-document word coverage.
- Compare execution time and theoretical complexity.

## 4. Tools and technologies
- HTML for page structure.
- CSS for responsive interface and styling.
- JavaScript for text processing and algorithm implementation.
- Modern web browser for execution.

## 5. Methodology
1. Read both documents from text areas or uploaded `.txt` files.
2. Convert text to lowercase, remove punctuation and normalize whitespace.
3. Split Document A into word sequences of the selected length (4–7 words).
4. Remove duplicate candidate phrases.
5. Search each candidate phrase in Document B using each algorithm.
6. Record match counts, positions and elapsed time.
7. Show the algorithm comparison and overlap coverage.

## 6. Algorithms

### 6.1 Naïve Pattern Matching
The algorithm checks the pattern at every possible starting position in the text. At each position it compares characters until a mismatch or a complete match occurs.

- Best case: O(n) in common early-mismatch situations.
- Worst case: O(n × m).
- Extra space: O(1).

### 6.2 Rabin–Karp
The algorithm calculates a hash for the pattern and a rolling hash for each text window. If the hash values match, it verifies the actual substring to avoid false matches caused by collisions.

- Average time: O(n + m) for a search with suitable hashing assumptions.
- Worst case: O(n × m).
- Extra space: O(1) in this implementation.

### 6.3 Knuth–Morris–Pratt (KMP)
KMP preprocesses the pattern and creates an LPS (Longest Prefix Suffix) array. When a mismatch occurs, the LPS value tells the algorithm how far the pattern can shift without repeating comparisons.

- Time: O(n + m).
- Extra space: O(m).

Here, n is the text length and m is the pattern length.

## 7. Output and performance analysis
The application displays:
- Number of matching candidate phrases.
- Percentage of words in Document A covered by matching phrases.
- Number of words in both documents.
- Measured execution time for all three algorithms.
- Theoretical time and extra-space complexity.
- Matching phrases and their positions in Document B.

Actual timings vary with browser, device, input size and phrase length. The algorithms process the same candidate phrases so their observed timings can be compared in the same run.

## 8. Testing
Test the application with:
1. Two documents containing identical sentences.
2. Two documents with a few shared phrases.
3. Two unrelated documents.
4. Different phrase lengths.
5. Empty documents and documents shorter than the selected phrase length.
6. Uploaded `.txt` files.

Expected behaviour: exact common phrases are listed; unrelated documents produce no matches; invalid empty or too-short inputs show a helpful message.

## 9. Limitations
- Detects exact phrase matches only.
- Does not detect paraphrased or semantically similar writing.
- Does not identify the original source or determine intent.
- Phrase overlap is an estimate, not a formal plagiarism score.
- Browser execution times are affected by the machine and background activity.

## 10. Future scope
- Add PDF and DOCX text extraction.
- Add sentence-level and configurable tokenization.
- Detect near matches using edit distance or shingling.
- Add source citations and report export.
- Build a server-side version with user accounts and saved reports.

## 11. Conclusion
TextGuard demonstrates the practical use of three important string-matching algorithms. It compares their results and execution times while showing exact matching phrases between two documents. The project provides a simple way to understand pattern matching and its role in text comparison.
