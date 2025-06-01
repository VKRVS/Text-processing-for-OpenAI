# Data Preprocessing and Cleaning for Language Models

Data cleaning is an essential step in preparing data for processing and feeding into large language models. Proper cleaning ensures data consistency, removes errors and irrelevant information, and improves model accuracy and processing speed.

---

## Table of Contents
- [Overview](#overview)
- [Token Counting](#token-counting)
- [Data Cleaning](#data-cleaning)
- [Exercises](#exercises)
  - [1. Validate Text Length](#1-validate-text-length)
  - [2. Filter Prohibited Words](#2-filter-prohibited-words)
  - [3. Detect Language](#3-detect-language)
  - [4. Generate Effective Prompts](#4-generate-effective-prompts)
  - [5. Estimate OpenAI Cost](#5-estimate-openai-cost)
  - [6. Clean JSON Text](#6-clean-json-text)
  
---

## Overview

Without data cleaning, language models may misinterpret or incorrectly process data. Cleaning helps by:

- Ensuring consistent formatting
- Removing errors and irrelevant data
- Reducing manual data checking time
- Improving model accuracy

---

## Token Counting

You do **not** need to tokenize strings manually before feeding them into the model; the model handles this automatically. However, tokenizing can help estimate the cost of API calls and check input length.

Use the `tiktoken` library to tokenize strings:

```python
import tiktoken

encoding = tiktoken.get_encoding("p50k_base")
tokens = encoding.encode("Hello world, this is fun!")
print(tokens)  # Output: [15496, 995, 11, 428, 318, 1257, 0]

# Decode tokens back to readable parts
decoded = [encoding.decode_single_token_bytes(token) for token in tokens]
print(decoded)  # Output: [b'Hello', b' world', b',', b' this', b' is', b' fun', b'!']

