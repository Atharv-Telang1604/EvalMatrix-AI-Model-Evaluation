# EvalMatrix: AI Model Evaluation Framework

## Overview

EvalMatrix is an AI Model Evaluation Framework developed to benchmark and compare multiple Large Language Models (LLMs) using a standardized scorecard methodology.

The project uses OpenRouter APIs to send identical prompts to multiple AI models and evaluates their responses based on quality, latency, reliability, and cost.

The objective is not simply to determine which model is the best, but to understand:

- Which model performs best for specific tasks
- Which model is the fastest
- Which model is the most reliable
- Which model hallucinates the least
- Which model provides the best value for cost

---

# Problem Statement

Large Language Models have different strengths and weaknesses.

Some models:

- Generate highly accurate answers
- Follow instructions well
- Respond quickly

while others may:

- Produce hallucinated information
- Ignore instructions
- Be slower but more accurate

Selecting the right model for production systems requires systematic evaluation rather than intuition.

This project provides a framework for evaluating and comparing multiple AI models using objective metrics.

---

# Project Objective

The objective of this project is to:

- Evaluate multiple LLMs fairly
- Measure response quality
- Measure response speed
- Track token usage
- Compare models using common benchmarks
- Export results for further analysis

---

# Models Evaluated

The framework supports any model available through OpenRouter.

Examples:

- Llama 3
- Mistral 7B
- Gemma 3
- Qwen 3
- Phi-4

All models are tested using:

- Same Prompt
- Same Temperature
- Same System Prompt
- Same Max Token Limit

This ensures fair evaluation.

---

# System Workflow

```text
Prompt Dataset
      ↓
OpenRouter API
      ↓
Multiple AI Models
      ↓
Response Collection
      ↓
Latency Measurement
      ↓
Data Storage
      ↓
CSV / Excel Export
      ↓
Performance Analysis
```

---

# What I Implemented

## Step 1: Environment Setup

Installed required libraries:

```python
requests
pandas
openpyxl
tqdm
```

Purpose:

- API communication
- Data manipulation
- Excel export
- Progress monitoring

---

## Step 2: Model Configuration

Configured multiple AI models through OpenRouter.

Example:

```python
MODELS = [
    "meta-llama/llama-3-8b-instruct",
    "mistralai/mistral-7b-instruct",
    "google/gemma-3-12b-it"
]
```

Purpose:

To compare models under identical conditions.

---

## Step 3: Prompt Dataset Creation

Created prompts from different categories:

- Factual QA
- Reasoning
- Summarization
- Instruction Following
- Coding

Purpose:

To evaluate models across diverse real-world tasks.

---

## Step 4: OpenRouter API Integration

Created a reusable function that:

- Sends prompts
- Receives responses
- Tracks token usage
- Measures latency

Purpose:

To automate communication with multiple models.

---

## Step 5: Response Collection

For every prompt:

1. Send prompt to Model A
2. Send prompt to Model B
3. Send prompt to Model C
4. Save all responses

Purpose:

To create a benchmark dataset for evaluation.

---

## Step 6: Latency Measurement

Latency measures the time required for a model to generate a response.

Formula:

Latency = Response Time − Request Time

Measured in milliseconds (ms).

Example:

```text
Request Sent      : 10:00:00.000
Response Received : 10:00:01.250

Latency = 1250 ms
```

Purpose:

To evaluate user experience and responsiveness.

---

## Step 7: Data Storage

All model outputs are stored in a Pandas DataFrame.

Each record contains:

- Prompt ID
- Prompt Category
- Prompt Text
- Model Name
- Model Response
- Latency
- Input Tokens
- Output Tokens

Purpose:

To simplify analysis and reporting.

---

## Step 8: CSV and Excel Export

Generated:

```text
model_evaluation_results.csv
model_evaluation_results.xlsx
```

Purpose:

To enable further analysis and sharing.

---

# Evaluation Metrics

## 1. Answer Correctness

Measures whether the answer is correct.

Scale:

```text
5 = Excellent
4 = Good
3 = Average
2 = Poor
1 = Incorrect
```

---

## 2. Instruction Following

Measures whether the model follows:

- Formatting rules
- Length constraints
- User instructions

Example:

Prompt:

```text
Explain recursion in exactly 2 lines.
```

A model receives a high score if it answers in exactly two lines.

---

## 3. Completeness

Measures whether all parts of a question are answered.

Example:

Prompt:

```text
Explain Java and Python.
```

If the model only explains Java:

Completeness Score = Low

---

## 4. Factuality

Measures factual accuracy.

Checks:

- Dates
- People
- Technical concepts
- Scientific facts

---

## 5. Groundedness

Measures whether answers remain faithful to provided context.

Important for:

- RAG systems
- Document QA systems

---

## 6. Relevance

Measures whether the response directly answers the user's question.

Example:

Prompt:

```text
What is Java?
```

If the model starts discussing databases:

Relevance Score decreases.

---

## 7. Hallucination Rate

Measures fabricated or unsupported information.

Scores:

```text
0 = No Hallucination
1 = Minor Hallucination
2 = Major Hallucination
```

Formula:

```text
Hallucination Rate =
(Hallucinated Responses / Total Responses) × 100
```

Purpose:

To identify unreliable models.

---

## 8. Safety

Measures whether unsafe prompts are handled correctly.

Checks:

- Harmful requests
- Dangerous instructions
- Toxic content

---

## 9. Latency Evaluation

The notebook calculates:

### p50 Latency

Also called Median Latency.

Represents the typical user experience.

Example:

```text
100
200
300
400
500
```

p50 = 300 ms

---

### p95 Latency

Represents worst-case performance.

95% of requests complete within this time.

Example:

```text
100
120
140
160
180
200
220
240
260
1000
```

p95 ≈ 260 ms

Meaning:

95% of users experience response times below 260 ms.

Only the slowest 5% experience delays.

Purpose:

To identify performance spikes.

---

## 10. Cost Efficiency

Measures quality relative to usage cost.

Formula:

```text
Cost per Successful Answer =
Total Cost / Successful Answers
```

Purpose:

To determine practical value.

---

# Output Generated

The framework generates:

- Raw Responses
- Latency Statistics
- Token Usage
- CSV Reports
- Excel Reports
- Model Comparison Data

---

# Technologies Used

- Python
- Google Colab
- OpenRouter API
- Pandas
- Requests
- OpenPyXL
- TQDM

---

# Skills Demonstrated

- Large Language Model Evaluation
- Prompt Engineering
- API Integration
- Benchmarking
- Latency Analysis
- Data Analysis
- Performance Testing
- AI Reliability Assessment

---

# Conclusion

EvalMatrix provides a structured approach for evaluating AI models using standardized benchmarks. The framework enables comparison of model quality, latency, reliability, and efficiency, helping developers select the most suitable model for their applications.

This project demonstrates practical AI evaluation techniques used in modern AI engineering, research, and production systems.
