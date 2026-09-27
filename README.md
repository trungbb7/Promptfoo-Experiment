# C++ Code Reviewer Prompt Evaluation

A [Promptfoo](https://promptfoo.dev/)-based evaluation suite designed to benchmark and test LLM system prompts for automated C++ code reviews.

## Project Overview

This repository evaluates LLM performance on C++ code review tasks, checking for:

- **Memory Safety & Lifetime Issues** (e.g., dangling `std::string_view`, local references)
- **Concurrency & Multithreading** (e.g., race conditions, lock safety)
- **Modern C++ Best Practices** (C++17/20)
- **False Positive Control** (preventing hallucinated warnings via `forbidden_findings` rubrics)

## Project Structure

```text
.
├── promptfooconfig.yaml          # Main Promptfoo configuration
└── cpp-review-eval/
    ├── prompts/                  # System prompts under test
    │   ├── baseline.txt          # Standard baseline prompt
    │   └── cpp-reviewer.txt      # Specialized C++ reviewer prompt
    └── tests/                    # Benchmark test suites
        ├── cpp-reviewer-4.yaml   # Comprehensive test cases with LLM rubrics
        └── ...
```

## Quick Start

### 1. Prerequisites

Ensure [Node.js](https://nodejs.org/) is installed and set your LLM API key (e.g., Groq, DeepSeek, or OpenAI):

```bash
export GROQ_API_KEY="your-api-key"
# or export DEEPSEEK_API_KEY="your-api-key"
```

### 2. Run Evaluation

Execute the evaluation benchmark using `promptfoo`:

```bash
npx promptfoo eval
```

### 3. View Results

Open the visual dashboard in your browser to analyze prompt scores and assertion pass rates:

```bash
npx promptfoo view
```
