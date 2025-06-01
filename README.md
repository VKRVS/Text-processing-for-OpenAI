# Jupyter Notebook: Data Preprocessing and Cleaning for Large Language Models

This Jupyter Notebook demonstrates essential data preprocessing and cleaning techniques, specifically tailored for preparing text data for use with Large Language Models (LLMs) like those offered by Azure OpenAI Service. Proper data preparation is crucial for improving model performance, accuracy, and managing API costs.

The notebook covers:
*   Understanding and counting tokens using the `tiktoken` library.
*   Basic text normalization techniques.
*   Practical exercises for common preprocessing tasks when interacting with LLMs.

## 📍 Overview

The notebook is divided into several key sections:

1.  **Introduction to Data Preprocessing:** Explains the importance of data cleaning before feeding text to an LLM.
2.  **Token Counting with `tiktoken`:**
    *   Details why tokenization is important for LLMs (understanding structure, cost calculation).
    *   Introduces `tiktoken` and its supported encodings for different Azure OpenAI Service models (`gpt2`, `p50k_base`, `cl100k_base`).
    *   Provides examples of how to encode text into tokens and decode tokens back into human-readable strings.
    *   Includes a helper function `get_num_tokens_from_string` to count tokens in a given string.
3.  **Data Cleaning:**
    *   Discusses best practices like replacing newlines and normalizing whitespace.
    *   Provides a `normalize_text` function to perform common text cleaning operations (lowercase, remove redundant spaces, standardize punctuation).
4.  **Practical Exercises:** A series of hands-on exercises to apply preprocessing concepts:
    *   **Exercise 1: Validate Text Length (`validate_text_length`)**: Splits text into segments that do not exceed a maximum token limit, using `cl100k_base` encoding.
    *   **Exercise 2: Filter Prohibited Words (`filter_prohibited_words`)**: Removes or redacts a list of specified prohibited words from a text.
    *   **Exercise 3: Identify Language of Text (`detect_language`)**: Uses the `langdetect` library to identify the language of a given text.
    *   **Exercise 5: Generate Effective Prompts (`generate_effective_prompt`)**: Creates optimized prompts for OpenAI based on a topic and target audience using a template.
    *   **Exercise 6: Measure Estimated Cost (`estimate_cost`)**: Calculates the estimated cost of an OpenAI API request based on the number of tokens and a predefined cost per 1000 tokens.
    *   **Exercise 7: Clean JSON Text (`clean_json_text`)**: Cleans keys and values within a JSON object by removing non-ASCII characters.

## ⚙️ Prerequisites

*   Python 3.x
*   Jupyter Notebook or a compatible environment (e.g., VS Code with Jupyter extension, Databricks).
*   The following Python libraries:
    *   `tiktoken`
    *   `regex` (usually a dependency of `tiktoken`)
    *   `langdetect`

You can install the necessary libraries by running the following commands in your environment or directly in notebook cells:

```bash
pip install tiktoken
pip install langdetect
