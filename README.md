# EvalMatrix - AI Model Evaluation Framework

## Overview
EvalMatrix is a comprehensive AI model evaluation framework designed to assess and benchmark various machine learning models across multiple dimensions including accuracy, performance, robustness, and comprehensive reporting. This framework provides a unified platform for evaluating machine learning models with detailed metrics, visualizations, and performance comparisons.

## What You've Created

EvalMatrix is an end-to-end evaluation system that allows you to:
- **Evaluate multiple ML models** using a standardized framework with consistent metrics
- **Compare model performance** across classification, regression, and performance benchmarks
- **Test robustness** of models under adversarial conditions and edge cases
- **Generate professional reports** with visualizations, charts, and detailed comparisons
- **Process multiple models in batch** for streamlined evaluation workflows
- **Export results** in multiple formats for further analysis and sharing

This framework is ideal for model selection, performance tracking, and establishing evaluation baselines for machine learning projects.

## Features
- 📊 **Multi-metric Evaluation**: Evaluate models across accuracy, precision, recall, F1-score, and custom metrics
- 🚀 **Performance Benchmarking**: Compare model inference speed, memory usage, and computational requirements
- 🛡️ **Robustness Testing**: Test model performance under adversarial conditions and edge cases
- 📈 **Visualization Dashboard**: Generate comprehensive evaluation reports with charts and comparisons
- 🔄 **Batch Processing**: Evaluate multiple models simultaneously
- 📝 **Detailed Reporting**: Export evaluation results in multiple formats (JSON, CSV, PDF)

## Installation

```bash
pip install -r requirements.txt
```

## Quick Start

```python
from evalmatrix import ModelEvaluator

# Initialize evaluator
evaluator = ModelEvaluator()

# Load your model and dataset
model = load_model('your_model.pkl')
test_data = load_data('test_data.csv')

# Run evaluation
results = evaluator.evaluate(model, test_data)

# Generate report
evaluator.generate_report(results)
```

## Project Structure

The complete project structure is documented in detail in `notebooks/project_structure.ipynb`. This Jupyter notebook provides an interactive overview of all directories, components, and their organization.

Key directories:
- **src/** - Source code (evaluators, metrics, utilities)
- **notebooks/** - Jupyter notebooks for analysis and examples
- **data/** - Sample datasets and pre-trained models
- **reports/** - Generated evaluation reports (JSON, CSV, PDF)

## Evaluation Metrics

### Classification Metrics
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix

### Regression Metrics
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score

### Performance Metrics
- Inference Time
- Memory Usage
- CPU/GPU Utilization
- Throughput

## Usage Examples

### Basic Model Evaluation
```python
results = evaluator.evaluate(model, test_data, task='classification')
```

### Custom Metrics
```python
from evalmatrix.metrics import CustomMetric

custom_metric = CustomMetric(name='custom_score', function=your_metric_function)
results = evaluator.evaluate(model, test_data, custom_metrics=[custom_metric])
```

### Batch Evaluation
```python
models = {'model1': m1, 'model2': m2, 'model3': m3}
batch_results = evaluator.batch_evaluate(models, test_data)
```

## Contact
For questions or support, please reach out to [your contact info]

---

**Last Updated**: June 2026
