# Hangman Game Solver

This project provides an automated solution to play the Hangman game by leveraging data analysis and pattern recognition to make educated guesses. It analyzes a large dataset of English words to understand their characteristics and uses this information to improve guess accuracy during the game.

## Overview

The solver begins by analyzing a dataset of 250,000 English words, examining word lengths, vowel/consonant distributions, and creating a frequency distribution of letters and n-grams (substrings). This analysis informs the solver's strategy when playing Hangman, allowing it to make guesses based on statistical insights derived from the dataset.

## Methodology

The project is divided into two main components: **Data Analysis** and **Game Logic**.

### Data Analysis

1. **Word Length Distribution:** Analyzes and visualizes the distribution of word lengths.
2. **Vowel and Consonant Frequency:** Calculates the total and average number of vowels and consonants per word.
3. **Average Vowels per Word Length:** Computes the average number of vowels for words of each length.

### Game Logic

1. **Hangman API Integration:** Communicates with a Hangman game server to start games and make guesses.
2. **Dictionary Preparation:** Loads a dictionary of words and analyzes it to prepare for the game.
3. **N-Word Dictionary:** Creates a dictionary of n-grams to help with pattern matching.
4. **Guessing Strategy:** Uses regex matching and statistical analysis to make educated guesses.

## Flowchart

```mermaid
flowchart TB
    A[Start] --> B{Analyze Word List}
    B --> C[Word Length Distribution]
    B --> D[Vowel/Consonant Counts]
    B --> E[Avg. Vowels per Word Length]
    C --> F[Load Hangman Game]
    D --> F
    E --> F
    F --> G{Make Guess}
    G -->|Match| H[Find Matching Words]
    G -->|No Match| I[Use Common Letters]
    H --> J[Guess Based on Frequency]
    I --> J
    J --> K{Check Game Status}
    K -->|Win| L[End Game]
    K -->|Lose| L
    K -->|Ongoing| G
    L --> M[Report Results]
