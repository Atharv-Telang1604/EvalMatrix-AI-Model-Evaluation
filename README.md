# EvalMatrix - AI Model Evaluation Framework

## Overview

EvalMatrix is a comprehensive AI model evaluation framework designed to assess and benchmark various machine learning models across multiple dimensions including accuracy, performance, robustness, and comprehensive reporting. This framework provides a unified platform for evaluating machine learning models with detailed metrics, visualizations, and performance comparisons across different model types and use cases.

## What You've Created - Detailed Explanation

### Purpose and Problem it Solves

When developing machine learning projects, data scientists and engineers often face the challenge of selecting the best model among multiple candidates. EvalMatrix solves this by providing a **standardized, automated, and comprehensive evaluation system** that removes guesswork from model selection.

### Complete End-to-End Evaluation System

EvalMatrix is an end-to-end evaluation system that addresses every stage of the model evaluation lifecycle:

#### 1. **Evaluate Multiple ML Models**
- Load and evaluate different machine learning models (neural networks, decision trees, SVMs, ensemble methods, etc.)
- Test models with various architectures and hyperparameters
- Use a standardized evaluation interface that works across different frameworks (scikit-learn, TensorFlow, PyTorch)
- Consistency ensures fair comparison between models with identical metrics and datasets

#### 2. **Compare Model Performance**
- **Classification Performance**: Compare accuracy, precision, recall, and F1-scores across models
- **Regression Performance**: Evaluate MSE, RMSE, MAE, and R² scores to find the best predictor
- **Performance Benchmarks**: Measure which model is fastest, most memory-efficient, and most scalable
- Side-by-side comparison makes it easy to identify the optimal model for your use case

#### 3. **Test Robustness Under Adversarial Conditions**
- Test how models perform when data is slightly corrupted or altered
- Evaluate model stability with edge cases (extreme values, unusual input patterns)
- Identify vulnerabilities and weak points in model predictions
- Ensures production-ready models that won't fail unexpectedly

#### 4. **Generate Professional Reports**
- Automatically create comprehensive evaluation reports with detailed metrics
- Include visualizations: confusion matrices, ROC curves, precision-recall plots, performance comparisons
- Generate detailed comparisons showing which model outperforms others and by how much
- Share results with stakeholders in professional formats

#### 5. **Batch Processing**
- Evaluate 10, 50, or even 100+ models simultaneously without writing individual evaluation code
- Dramatically reduce evaluation time by processing multiple models in parallel
- Organize results in a centralized location for easy comparison
- Ideal for hyperparameter tuning and architecture search

#### 6. **Export Results in Multiple Formats**
- **JSON**: Machine-readable format for programmatic access and integration with other tools
- **CSV**: Spreadsheet format for data analysis in Excel or other tools
- **PDF**: Professional, shareable format for reports and documentation
- Enable further analysis, archiving, and sharing with teams

### Real-World Use Cases

1. **Model Selection**: Compare 5 different classifiers to pick the best one for your fraud detection system
2. **Performance Tracking**: Monitor how model performance changes as you retrain with new data
3. **Baseline Establishment**: Create a evaluation baseline to compare against improved versions
4. **Hyperparameter Optimization**: Evaluate hundreds of parameter combinations to find the sweet spot
5. **Production Readiness**: Verify model robustness before deploying to production

## Features

### 📊 **Multi-metric Evaluation**
Evaluate models using a comprehensive set of metrics that give you a complete picture of model performance:
- **Accuracy**: How often the model is correct overall
- **Precision**: When the model predicts positive, how often is it right?
- **Recall**: Of all actual positives, how many did the model catch?
- **F1-Score**: Balance between precision and recall
- **Custom Metrics**: Define your own metrics specific to your business problem

### 🚀 **Performance Benchmarking**
Not all accurate models are practical. Measure real-world performance:
- **Inference Speed**: How long does it take to make predictions? (milliseconds per prediction)
- **Memory Usage**: How much RAM does the model consume? (important for edge devices)
- **CPU/GPU Utilization**: Which hardware resources does the model use?
- **Throughput**: How many predictions can be made per second?

### 🛡️ **Robustness Testing**
Ensure your model won't fail in production:
- **Adversarial Conditions**: Slightly perturbed inputs that shouldn't significantly change predictions
- **Edge Cases**: Unusual or extreme values that the model might not have seen during training
- **Stability Testing**: Verify that small input changes don't cause dramatically different outputs
- **Confidence Scores**: Understand how confident the model is in its predictions

### 📈 **Visualization Dashboard**
See your results visually:
- **Confusion Matrices**: Understand where the model makes mistakes
- **ROC Curves**: Trade-off between true positive and false positive rates
- **Precision-Recall Plots**: Visualize how precision and recall change with thresholds
- **Performance Comparisons**: Bar charts comparing multiple models
- **Heatmaps**: Show performance across different data segments

### 🔄 **Batch Processing**
Evaluate multiple models efficiently:
- Write evaluation code once, run it on hundreds of models
- Parallel processing for faster results
- Automatic result collection and organization
- Generate batch comparison reports

### 📝 **Detailed Reporting**
Export results in multiple formats:
- **JSON Reports**: Complete metrics data for programmatic access
- **CSV Reports**: Tabular format for spreadsheet analysis
- **PDF Reports**: Professional reports with charts and summaries
- Customizable report templates for different stakeholders

## Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Virtual environment (recommended)

### Step-by-Step Installation

```bash
# 1. Clone the repository
git clone https://github.com/Atharv-Telang1604/EvalMatrix-AI-Model-Evaluation.git
cd EvalMatrix-AI-Model-Evaluation

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Verify installation
python -c "from evalmatrix import ModelEvaluator; print('Installation successful!')"
```

## Quick Start

### Basic Workflow

```python
from evalmatrix import ModelEvaluator
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

# Step 1: Load your data
X, y = load_iris(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Step 2: Train or load your model
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)

# Step 3: Initialize evaluator
evaluator = ModelEvaluator()

# Step 4: Run evaluation
results = evaluator.evaluate(model, X_test, y_test)

# Step 5: Generate report
evaluator.generate_report(results, format='pdf', output_path='evaluation_report.pdf')

# Step 6: Access individual metrics
print(f"Accuracy: {results.accuracy}")
print(f"F1-Score: {results.f1_score}")
print(f"Inference Time: {results.inference_time}ms")
```

## Project Structure

The complete project structure is documented in detail in `notebooks/project_structure.ipynb`. This Jupyter notebook provides an interactive overview of all directories, components, and their organization.

### Key Directories Explained

- **src/** - **Source Code**: Contains all the core evaluation logic
  - `evaluators/` - Classes that handle different types of evaluations
  - `metrics/` - Implementations of various evaluation metrics
  - `utils/` - Helper functions for data loading, visualization, and reporting

- **notebooks/** - **Jupyter Notebooks**: Interactive guides and examples
  - `project_structure.ipynb` - Project organization and architecture
  - `quick_start.ipynb` - Getting started guide with examples
  - `evaluation_examples.ipynb` - Detailed usage scenarios

- **data/** - **Sample Datasets**: Test datasets and example models
  - `train/` - Training data samples
  - `test/` - Test data samples
  - `sample_models/` - Pre-trained models for quick testing

- **reports/** - **Generated Reports**: Where evaluation results are saved
  - `json/` - Machine-readable metric reports
  - `csv/` - Spreadsheet-compatible results
  - `pdf/` - Professional evaluation reports

- **requirements.txt** - **Dependencies**: All Python packages needed to run the project

## Evaluation Metrics - Detailed

### Classification Metrics
Used when your model predicts categories (e.g., spam/not spam, cat/dog/bird):

- **Accuracy**: (Correct Predictions) / (Total Predictions) - Overall correctness
- **Precision**: (True Positives) / (True Positives + False Positives) - When we predict positive, how often are we right?
- **Recall**: (True Positives) / (True Positives + False Negatives) - Of all actual positives, how many did we catch?
- **F1-Score**: Harmonic mean of precision and recall - Balance between missing positives and false alarms
- **ROC-AUC**: Area under the Receiver Operating Characteristic curve - Overall model discrimination ability
- **Confusion Matrix**: Shows true positives, true negatives, false positives, false negatives

### Regression Metrics
Used when your model predicts continuous values (e.g., house price, temperature):

- **Mean Squared Error (MSE)**: Average of squared differences - Penalizes large errors more
- **Root Mean Squared Error (RMSE)**: Square root of MSE - Same scale as original data
- **Mean Absolute Error (MAE)**: Average of absolute differences - Average prediction error
- **R² Score**: Proportion of variance explained - How much better than just predicting the mean?

### Performance Metrics
Measure real-world resource usage and speed:

- **Inference Time**: How many milliseconds per prediction?
- **Memory Usage**: Peak RAM consumption during evaluation
- **CPU/GPU Utilization**: Percentage of computational resources used
- **Throughput**: Predictions per second the model can handle

## Usage Examples

### Example 1: Basic Model Evaluation
Evaluate a single classification model:

```python
from evalmatrix import ModelEvaluator

evaluator = ModelEvaluator()

# Evaluate for classification
results = evaluator.evaluate(
    model=your_model, 
    X_test=test_features,
    y_test=test_labels,
    task='classification'
)

# View results
print(f"Accuracy: {results.accuracy:.4f}")
print(f"Precision: {results.precision:.4f}")
print(f"Recall: {results.recall:.4f}")
print(f"F1-Score: {results.f1_score:.4f}")
```

### Example 2: Custom Metrics
Add your own business-specific metrics:

```python
from evalmatrix.metrics import CustomMetric
import numpy as np

# Define a custom metric function
def profit_score(y_true, y_pred):
    """Calculate profit based on predictions"""
    tp = np.sum((y_pred == 1) & (y_true == 1))
    fp = np.sum((y_pred == 1) & (y_true == 0))
    return (tp * 100) - (fp * 50)  # $100 per correct prediction, -$50 per false alarm

# Create custom metric
custom_metric = CustomMetric(
    name='profit_score', 
    function=profit_score
)

# Evaluate with custom metric
results = evaluator.evaluate(
    model=your_model,
    X_test=test_features,
    y_test=test_labels,
    custom_metrics=[custom_metric]
)

print(f"Profit Score: ${results.profit_score}")
```

### Example 3: Batch Evaluation
Compare multiple models at once:

```python
from evalmatrix import ModelEvaluator
from sklearn.ensemble import RandomForestClassifier, GradientBoostingClassifier
from sklearn.svm import SVC

evaluator = ModelEvaluator()

# Create multiple models
models = {
    'RandomForest': RandomForestClassifier(n_estimators=100),
    'GradientBoosting': GradientBoostingClassifier(n_estimators=100),
    'SVM': SVC(kernel='rbf')
}

# Batch evaluate all models
batch_results = evaluator.batch_evaluate(
    models=models,
    X_test=test_features,
    y_test=test_labels
)

# Compare results
for model_name, results in batch_results.items():
    print(f"\n{model_name}:")
    print(f"  Accuracy: {results.accuracy:.4f}")
    print(f"  F1-Score: {results.f1_score:.4f}")
    print(f"  Inference Time: {results.inference_time:.2f}ms")

# Generate comparison report
evaluator.generate_comparison_report(batch_results, format='pdf')
```

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                    EvalMatrix Workflow                          │
└─────────────────────────────────────────────────────────────────┘
                              │
                    ┌─────────▼─────────┐
                    │   Load Data       │
                    │  (CSV, NumPy,     │
                    │   Pandas)         │
                    └─────────┬─────────┘
                              │
                    ┌─────────▼─────────┐
                    │   Load/Train      │
                    │   Models          │
                    └─────────┬─────────┘
                              │
                    ┌─────────▼─────────┐
                    │  Initialize       │
                    │  Evaluator        │
                    └─────────┬─────────┘
                              │
                    ┌─────────▼─────────┐
                    │  Run Evaluation   │
                    │  (Single/Batch)   │
                    └─────────┬─────────┘
                              │
                    ┌─────────▼──────────┐
                    │  Collect Results   │
                    │  (Metrics, Plots)  │
                    └─────────┬──────────┘
                              │
                    ┌─────────▼──────────┐
                    │  Generate Reports  │
                    │ (JSON/CSV/PDF)     │
                    └─────────┬──────────┘
                              │
                    ┌─────────▼──────────┐
                    │  Visualizations    │
                    │  & Comparisons     │
                    └────────────────────┘
```

## Contact & Support

For questions, issues, or support, please reach out to:
- **Email**: [your contact info]
- **GitHub Issues**: Report bugs or request features
- **Documentation**: See notebooks/ for detailed examples

---

**Last Updated**: June 2026
**Version**: 1.0
**Status**: Production Ready
