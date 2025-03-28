# SpatialSentry

<p align="center">
  <img src="docs/images/logo.png" alt="SpatialSentry Logo" width="200"/>
</p>

[![Crates.io](https://img.shields.io/crates/v/spatial_sentry.svg)](https://crates.io/crates/spatial_sentry)
[![Documentation](https://docs.rs/spatial_sentry/badge.svg)](https://docs.rs/spatial_sentry)
[![Build Status](https://github.com/constanza/spatial_sentry/workflows/Rust/badge.svg)](https://github.com/constanza/spatial_sentry/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 🌌 High-Performance Spatial Anomaly Detection

SpatialSentry is a Rust-based tool for detecting anomalies in spatial data. It leverages advanced algorithms to identify unusual patterns or outlier locations that may indicate important phenomena across geographic, astronomical, or any coordinate-based data.

## 🚀 Features

- **Multiple Detection Algorithms**: Isolation Forest, Mahalanobis Distance, with more coming soon
- **High Performance**: Optimized Rust implementation for speed and memory efficiency
- **Visualization Tools**: Generate plots to visualize detected anomalies
- **Serialization**: Save and load trained models
- **Easy API**: Simple interface for integration with existing systems

## 📦 Installation

Add SpatialSentry to your Cargo.toml:

```toml
[dependencies]
spatial_sentry = "0.1.0"
Or install the CLI tool:

bash

Hide
cargo install spatial_sentry
🔧 Usage
Basic Example
rust

Hide
use spatial_sentry::{SpatialSentry, DetectionMethod};
use ndarray::Array2;

fn main() -> Result<(), Box<dyn std::error::Error>> {
    // Load or generate your spatial data
    let data = Array2::from_shape_vec((100, 2), 
        (0..200).map(|i| (i as f64 / 10.0).sin()).collect()
    )?;
    
    // Initialize detector with Isolation Forest
    let mut detector = SpatialSentry::new(
        DetectionMethod::IsolationForest, 
        0.05,  // contamination rate 
        100    // number of estimators
    );
    
    // Train the model
    detector.fit(&data);
    
    // Detect anomalies
    let labels = detector.detect(&data);
    
    // Visualize results
    detector.visualize_2d(&data, &labels, "anomalies.png")?;
    
    // Save model for later use
    detector.save_model("spatial_model.json")?;
    
    Ok(())
}
CLI Usage
bash

Hide
# Analyze a CSV file with spatial data
spatial_sentry analyze --input coords.csv --method isolation_forest --output results.png

# Generate a heatmap of anomaly density
spatial_sentry heatmap --input coords.csv --resolution 200 --output heatmap.png
📊 Visualization Examples
<p align="center">
  <img src="docs/images/example_detection.png" alt="Example Detection" width="400"/>
  <img src="docs/images/example_heatmap.png" alt="Example Heatmap" width="400"/>
</p>
🔍 Use Cases
Cybersecurity: Detect anomalous network traffic patterns
Astronomy: Identify unusual celestial phenomena
GIS: Find geographic outliers in spatial datasets
Surveillance: Spot unusual movement patterns
IoT: Detect anomalies in sensor networks
📚 Documentation
For detailed documentation, visit docs.rs/spatial_sentry.

🔬 Algorithm Details
SpatialSentry includes implementations of:

Isolation Forest: An ensemble method that isolates anomalies through recursive partitioning
Mahalanobis Distance: A statistical measure that accounts for correlations in multivariate data
Coming Soon: Local Outlier Factor (LOF) and DBSCAN-based anomaly detection
📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

