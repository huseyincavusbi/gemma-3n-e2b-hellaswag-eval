# Gemma 3n E2B HellaSwag Evaluation

A comprehensive evaluation of Google's **Gemma 3n-E2B** model on the HellaSwag benchmark for commonsense reasoning.

## What This Does

This project evaluates the Gemma 3n-E2B model's ability to complete sentences with the most plausible continuation from multiple choices, testing real-world commonsense reasoning abilities.

## Key Features

- **Log-likelihood scoring**: Uses negative loss as likelihood measure for each completion candidate
- **Progressive evaluation**: Tests on 100 → 1,000 → full 10,042 examples for robust assessment  
- **GPU-optimized**: Efficient evaluation on CUDA with bfloat16 precision
- **Kaggle-ready**: Seamless integration with Kaggle secrets for HuggingFace authentication

## Results

| Sample Size | Accuracy |
|-------------|----------|
| 100 examples | 64.00% |
| 1,000 examples | 66.80% |
| **Full dataset (10,042)** | **68.73%** |

The **68.73% accuracy** means Gemma 3n-E2B correctly identifies the most plausible sentence completion about 7 out of 10 times. This demonstrates strong commonsense reasoning capabilities, as the model must understand context, causality, and real-world knowledge to distinguish between similar but subtly different completions.

## Run the Evaluation

**Kaggle Notebook**: [Gemma 3n-E2B HellaSwag Evaluation](https://www.kaggle.com/code/huseyincavus/gemma-3n-e2b-hellaswag-eval)

Simply fork the notebook and run all cells. Make sure to:
- Add your HuggingFace token to Kaggle Secrets as `HF_TOKEN`
- Enable GPU acceleration (T4 recommended)

## What Makes This Unique

- **Direct loss-based scoring**: Instead of generation-based approaches, uses model's internal loss for more accurate likelihood estimation
- **Scalable evaluation pipeline**: Progressive testing validates consistency across different sample sizes
- **Production-ready setup**: Handles authentication, GPU allocation, and memory management automatically

---

**Dataset**: [HellaSwag](https://huggingface.co/datasets/Rowan/hellaswag) | **Model**: [Gemma 3n-E2B](https://huggingface.co/google/gemma-3n-E2B)
