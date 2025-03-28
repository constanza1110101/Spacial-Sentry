🤝 Contributing
Contributions are welcome! Please see CONTRIBUTING.md for details.

plaintext

Hide

# CONTRIBUTING.md

```markdown
# Contributing to SpatialSentry

Thank you for your interest in contributing to SpatialSentry! This document provides guidelines and instructions for contributing to the project.

## 📋 Code of Conduct

This project adheres to the Rust community's Code of Conduct. By participating, you are expected to uphold this code.

## 🔄 Development Workflow

1. Fork the repository
2. Create a new branch for your feature or bugfix
3. Implement your changes
4. Add tests for your changes
5. Ensure all tests pass with `cargo test`
6. Run the benchmarks with `cargo bench` to ensure performance is maintained
7. Submit a pull request

## 🧪 Testing

All code contributions should include appropriate tests:

```bash
# Run all tests
cargo test

# Run specific tests
cargo test mahalanobis

# Run benchmarks
cargo bench
📝 Code Style
SpatialSentry follows standard Rust style guidelines:

Run cargo fmt before submitting code
Ensure your code passes cargo clippy without warnings
Follow the Rust API Guidelines
Document all public APIs with rustdoc comments
🏗️ Project Structure
plaintext

Hide
spatial_sentry/
├── src/
│   ├── lib.rs           # Library entry point
│   ├── algorithms/      # Detection algorithms
│   ├── visualization/   # Plotting and visualization
│   ├── io/              # File I/O utilities
│   └── cli/             # Command-line interface
├── examples/            # Example programs
├── benches/             # Performance benchmarks
└── tests/               # Integration tests
🚀 Adding New Features
New Detection Algorithms
Create a new file in src/algorithms/
Implement the AnomalyDetector trait
Add appropriate tests
Update the DetectionMethod enum in lib.rs
Document the algorithm in the README
Visualization Improvements
Add new visualization functions in src/visualization/
Ensure they work with different data dimensions
Add examples showing the new visualizations
📊 Performance Considerations
SpatialSentry prioritizes performance. When adding new features:

Use appropriate data structures for the task
Avoid unnecessary allocations
Consider parallelization for computationally intensive operations
Include benchmarks for new algorithms
📚 Documentation
Document all public APIs with examples
Keep the README updated with new features
Consider adding tutorials for complex features
🐛 Reporting Bugs
When reporting bugs, please include:

A clear description of the issue
Steps to reproduce
Expected vs. actual behavior
Version information (Rust version, SpatialSentry version)
If possible, a minimal code example that demonstrates the issue
💡 Feature Requests
Feature requests are welcome! Please provide:

A clear description of the proposed feature
The motivation behind the feature
Possible implementation approaches if you have ideas
🔄 Pull Request Process
Update the README.md with details of changes if appropriate
Update the CHANGELOG.md with a description of your changes
The PR should work on the latest Rust stable and nightly versions
Ensure documentation is updated
PRs require review from at least one maintainer
📄 Licensing
By contributing to SpatialSentry, you agree that your contributions will be licensed under the project's MIT License.

Thank you for contributing to SpatialSentry!
