# Variable Selection and Bayesian Methods Simulation Study

This repository contains comprehensive simulation studies comparing various variable selection methods, with a focus on Bayesian approaches and their comparison with LASSO. The project includes multiple simulation scenarios with different data distributions and parameter settings.

## Project Structure

### Core Simulation Notebooks

<!-- - **`simulation_study.ipynb`** - Main simulation study comparing multiple methods -->
- **`simulation_study_T.ipynb`** - Student's t-distribution simulation study (50 features)
- **`simulation_study_T_100.ipynb`** - Student's t-distribution simulation study (100 features)
- **`simulation_study_Gau.ipynb`** - Gaussian distribution simulation study (50 features)
- **`simulation_study_Gau_100.ipynb`** - Gaussian distribution simulation study (100 features)
- **`simulation_study_Gamma.ipynb`** - Gamma distribution simulation study (50 features)
- **`simulation_study_Gamma_100.ipynb`** - Gamma distribution simulation study (100 features)
<!-- - **`simulation_study_Time.ipynb`** - Computational time comparison study -->

### Benchmarking and Testing

- **`embayes_bench.ipynb`** - Empirical Bayes benchmarking

### Data and Results

- **`R_test_bench/`** - R benchmarking data and results
- **`Result/`** - Simulation results and visualizations
- **`saved_metrics/`** - Saved performance metrics


## Simulation Studies Overview

### Data Generation
The simulations use block-structured correlation matrices with AR(1) correlation within blocks:

```python
# Default simulation parameters
N = 500            # samples
P = 1000           # total features
S = 50/100         # number of true nonzero features
BLOCK = 100        # correlation block size
RHO = 0.8          # within-block AR(1) correlation
SNR = 16.0         # signal-to-noise ratio
NUM_RUNS = 50   # number of simulation runs
```

### Distribution Types
1. **Gaussian**: Standard normal distribution with block correlation
2. **Student's t**: Heavy-tailed t-distribution
3. **Gamma**: Gamma distribution with shape and scale parameters

### Methods Compared
- **LASSO** (L1 regularization)
- **SuSiE** (Sum of Single Effects)
- **Empirical Bayes** methods

## Key Features

### Performance Metrics
- **True Positive Rate (TPR)**
- **False Positive Rate (FPR)**  <!-- - **Precision and Recall** -->
- **F1 Score**
- **Brier Score**
- **Computational Time**

### Visualization
- ROC curves and precision-recall plots
- Performance comparison across different distributions
- Computational time analysis
- Correlation structure visualization

## Getting Started

### Prerequisites

```bash
# Python dependencies
pip install numpy scipy scikit-learn pandas matplotlib
pip install cupy  # for GPU acceleration (optional)
pip install rpy2  # for R integration

# R dependencies
install.packages(c("susieR", "emBayes"))
```

### Running Simulations

1. **Basic Simulation**:
   ```bash
   jupyter notebook simulation_study.ipynb
   ```

2. **Distribution-specific Studies**:
   ```bash
   # Gaussian distribution
   jupyter notebook simulation_study_Gau.ipynb
   
   # Student's t-distribution
   jupyter notebook simulation_study_T.ipynb
   
   # Gamma distribution
   jupyter notebook simulation_study_Gamma.ipynb
   ```

3. **High-dimensional Studies** (100 features):
   ```bash
   jupyter notebook simulation_study_Gau_100.ipynb
   jupyter notebook simulation_study_T_100.ipynb
   jupyter notebook simulation_study_Gamma_100.ipynb
   ```

## Results and Outputs

### Generated Files
- **CSV files**: Performance metrics for each method
- **PNG files**: Visualization plots
- **PKL files**: Saved metrics for further analysis

### Key Results Locations
- `Result/` - Main result visualizations
- `R_test_bench/` - R benchmarking results
- `saved_metrics/` - Pickled performance metrics

## Configuration

### Simulation Parameters
You can modify simulation parameters in each notebook:

```python
# Adjust these parameters as needed
N = 500            # Number of samples
P = 1000           # Number of features
S = 50             # Number of true signals
BLOCK = 100        # Correlation block size
RHO = 0.8          # Within-block correlation
SNR = 16.0         # Signal-to-noise ratio
NUM_RUNS = 50      # Number of simulation runs
```

### Method Configuration
- **LASSO**: Cross-validation for lambda selection
- **SuSiE**: Default parameters with L=10
- **Empirical Bayes**: Various prior specifications

## External Methods

This repository includes implementations of several external methods:

<!-- - **CaviaR**: Causal Variants Identification -->
<!-- - **SparsePro**: Sparse projection methods -->
<!-- - **Fine-mapping tools**: Various fine-mapping approaches -->
- **SuSiE**: Sum of Single Effects implementation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions or issues, please open an issue on GitHub.

## Related Work

- SuSiE: [Sum of Single Effects](https://github.com/stephenslab/susieR)
- Empirical Bayes: [Empirical Bayes](https://github.com/stephenslab/empBayes)
<!-- - CAVIAR: [Causal Variants Identification](https://github.com/fhormoz/caviar) -->
<!-- - SparsePro: [Sparse Projection Methods](https://github.com/zhqiu/SparsePro) -->

---

**Note**: This repository contains simulation studies for research purposes. Results may vary depending on system configuration and random seeds.
