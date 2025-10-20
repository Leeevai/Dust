# Dust
## Data Analysis and Mining in Rust

> Inspired by *Data Mining and Analysis: Fundamental Concepts and Algorithms*  

---

## Overview

**Dust** is a data analysis and mining library written in **Rust**, based on the theoretical and algorithmic foundations presented in  
*Data Mining and Analysis: Fundamental Concepts and Algorithms* by Zaki and Meira.

The objective of Dust is to combine the safety and performance of Rust with the rigor of data mining theory, providing a modular and efficient framework for developing algorithms in data analysis, pattern discovery, and predictive modeling.

---

## Features

- Core data structures for datasets, attributes, and transactions  
- Descriptive analysis: summaries, distributions, and correlations  
- Pattern discovery: frequent itemsets and association rule mining  
- Predictive models: decision trees, naive Bayes, k-NN  
- Clustering: k-means, hierarchical, and density-based algorithms  
- Dimensionality reduction: PCA, SVD, and feature selection  
- Parallel and memory-safe execution through Rust’s ownership model  
- Modular architecture for easy extension and experimentation

---

## Reference Framework

This implementation follows the algorithmic structure outlined in *Zaki & Meira*:

| Concept | Module | Reference Chapter |
|----------|---------|-------------------|
| Data Preprocessing | `dust::preprocess` | Ch. 2 |
| Similarity Measures | `dust::metrics` | Ch. 3 |
| Classification | `dust::classify` | Ch. 4 |
| Clustering | `dust::cluster` | Ch. 5 |
| Association Analysis | `dust::associate` | Ch. 6 |
| Anomaly Detection | `dust::anomaly` | Ch. 7 |
| Dimensionality Reduction | `dust::reduce` | Ch. 8 |
| Evaluation Metrics | `dust::eval` | Ch. 9 |

Each module adheres closely to the algorithmic principles described in the textbook, implemented in idiomatic Rust with generics and safe concurrency.

---

## Getting Started

### Prerequisites

- Rust (version 1.78 or newer)
- Cargo package manager

### Installation

```bash
git clone https://github.com/your-username/dust.git
cd dust
cargo build
cargo test
```

### Example Usage

```rust
use dust::preprocess::Dataset;
use dust::classify::DecisionTree;

fn main() -> Result<(), Box<dyn std::error::Error>> {
    let data = Dataset::from_csv("data/iris.csv")?;
    let tree = DecisionTree::train(&data, "species")?;
    let prediction = tree.predict(&data[0])?;
    println!("Predicted: {:?}", prediction);
    Ok(())
}
```

---

## Architecture

```
dust/
 ├── src/
 │   ├── preprocess/   # Data cleaning and transformation
 │   ├── metrics/      # Similarity and distance measures
 │   ├── classify/     # Classification algorithms
 │   ├── cluster/      # Clustering algorithms
 │   ├── associate/    # Association rule mining
 │   ├── anomaly/      # Outlier detection
 │   ├── reduce/       # Dimensionality reduction
 │   └── eval/         # Evaluation metrics
 ├── data/             # Example datasets
 └── examples/         # Usage examples
```

---

## Goals and Philosophy

- Implement algorithms faithfully as described in *Zaki & Meira (2014)*  
- Optimize for performance using parallelism and efficient memory layouts  
- Maintain strict memory safety (no unsafe code unless necessary)  
- Ensure modular, trait-based extensibility  
- Provide educational clarity for research and learning

---

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/new-algorithm`)  
3. Commit your changes  
4. Open a pull request

---

## License

This project is licensed under the MIT License.  
See the [LICENSE](LICENSE) file for details.

---

Dust — Data Mining in Rust
