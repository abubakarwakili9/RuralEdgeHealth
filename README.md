# RuralEdgeHealth

**RuralEdgeHealth: A Sustainable Offline Mobile Edge AI Reference Architecture for Intelligent IoT Sensor Classification in Resource-Constrained Environments**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://developer.android.com)
[![Language](https://img.shields.io/badge/Language-Kotlin-purple.svg)](https://kotlinlang.org)
[![Status](https://img.shields.io/badge/Status-Under%20Review-blue.svg)](#research-paper)

## Overview

RuralEdgeHealth is an offline-first mobile edge AI reference architecture designed for intelligent IoT sensor classification in resource-constrained environments. It enables fully on-device inference on entry-level Android smartphones without requiring persistent internet connectivity or cloud infrastructure.

The framework addresses deployment conditions common in rural, remote, and infrastructure-constrained settings, where reliable connectivity, stable energy access, and modern high-performance devices cannot be assumed. It combines Bluetooth Low Energy (BLE) sensing, manual fallback input, ONNX-based on-device inference, encrypted local storage, and runtime optimization into a reusable five-layer architecture for intelligent IoT applications.

Although the current implementation is demonstrated through a health-oriented sensor classification scenario, the architecture itself is domain-agnostic and can be adapted to broader IoT application areas such as environmental monitoring, smart agriculture, livestock monitoring, industrial sensing, and remote infrastructure monitoring.

## Why RuralEdgeHealth?

Many intelligent IoT systems still depend on stable internet access, cloud services, and relatively powerful hardware. These assumptions limit deployment in underserved and low-resource environments.

RuralEdgeHealth is designed to address this gap through:

- **Offline-first operation** without reliance on continuous internet connectivity
- **Entry-level hardware support** for Android 8.0+ smartphones with 2 GB RAM
- **On-device AI inference** using ONNX Runtime
- **BLE sensor integration** with manual input fallback
- **Encrypted local storage** for secure offline data persistence
- **Energy-aware runtime optimization** for sustained field use
- **Reusable reference architecture** for broader intelligent IoT deployment

## Key Features

- 🔄 **Offline-First Architecture**: Core system functionality works without internet connectivity
- 📱 **Entry-Level Device Support**: Optimized for Android 8.0+ smartphones with 2 GB RAM
- 🤖 **On-Device AI Inference**: ONNX-based model execution directly on the mobile device
- 🔗 **IoT Integration**: BLE sensor acquisition with manual fallback input
- 🔒 **Secure Local Storage**: Encrypted persistence using Room and SQLCipher
- 🔋 **Energy Efficiency**: Runtime optimization for battery-constrained environments
- 🏗️ **Five-Layer Reference Architecture**: Structured and reusable design for intelligent IoT systems
- 🌍 **Domain-Agnostic Design**: Demonstrated in healthcare, transferable to other IoT domains

## Architecture

RuralEdgeHealth follows a modular **five-layer architecture**:

### 1. Presentation and Interface Layer
Provides an interactive Android user interface with multi-modal input support. It is designed to support both BLE-based sensing and manual entry while remaining usable in constrained settings and by diverse user populations.

### 2. IoT Sensor Integration Layer
Manages BLE communication, sensor discovery, pairing, data acquisition, and fallback handling. It supports standardized sensor integration workflows and preserves the same downstream pipeline when manual input is used.

### 3. Edge Intelligence and Processing Layer
Executes the on-device inference pipeline using ONNX Runtime. This layer performs lightweight processing and sensor classification on resource-constrained hardware, without relying on cloud connectivity.

### 4. Data Management and Persistence Layer
Supports secure offline data storage using Room and SQLCipher. It manages model assets, cached results, and local historical records while preserving full offline functionality.

### 5. Infrastructure and Runtime Layer
Optimizes execution across heterogeneous Android devices. It supports Android API 26+ and includes memory-aware and energy-aware runtime management for sustained operation on entry-level hardware.

## Validation Highlights

The current paper reports the following Phase 1 technical results:

| Metric | Result |
|--------|--------|
| Classification Accuracy | 98.25% |
| Inference Latency | <100 ms |
| Model Type | Random Forest |
| Model Format | ONNX |
| Approximate Model Size | 3.5 MB |
| Target Devices | Android 8.0+, 2 GB RAM |
| Battery Consumption | <4% per hour under evaluation workload |

These findings demonstrate the feasibility of offline intelligent IoT sensor classification on accessible mobile hardware.

## Current Demonstration Scenario

The present implementation validates the architecture through a health-oriented sensor classification scenario based on synthetic IoT sensor data and offline mobile inference.

This scenario was selected because it provides a clear and understandable sensing context for architectural and deployment evaluation. However, RuralEdgeHealth is intended as a **general reference architecture**, not a healthcare-only system.

Its design principles are transferable to:

- Environmental sensing
- Smart agriculture
- Livestock monitoring
- Water and air quality monitoring
- Industrial IoT sensing
- Remote and low-connectivity intelligent monitoring systems

## Dataset

The repository includes a synthetic IoT sensor classification dataset used for training and evaluation.

### Dataset Summary
- **Records**: 10,000 samples
- **Features**: 15 features
- **Classes**: Normal (50%), Moderate (35%), Critical (15%)
- **Purpose**: Computational feasibility and architectural evaluation for offline edge AI deployment

For detailed dataset documentation, see the `data/` folder.

## Model Information

- **Selected Model**: Random Forest
- **Other Evaluated Models**: XGBoost, LightGBM, Multi-Layer Perceptron
- **Export Format**: ONNX
- **Inference Runtime**: ONNX Runtime Mobile
- **Validation Strategy**: 5-fold cross-validation with SMOTETomek balancing
- **Deployment Goal**: Efficient and accurate sensor classification on entry-level Android hardware

## Technology Stack

- **Platform**: Android
- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture Pattern**: MVVM
- **Database**: Room + SQLCipher
- **ML Runtime**: ONNX Runtime Mobile
- **Connectivity**: Bluetooth Low Energy (BLE)

## Repository Structure

```text
RuralEdgeHealth/
├── app/                      # Android application source code
├── data/                     # Dataset and supporting files
├── docs/                     # Documentation and figures
├── models/                   # Trained/exported models
├── GETTING_STARTED.md        # Setup and usage guide
├── LICENSE                   # MIT License
└── README.md


Quick Start
Clone the Repository
git clone https://github.com/abubakarwakili9/RuralEdgeHealth.git
cd RuralEdgeHealth
Open and Run
Open the project in Android Studio
Sync Gradle dependencies
Build the project
Run on an Android emulator or physical Android device

For detailed setup and usage instructions, see:

GETTING_STARTED.md
data/README.md
Research Paper

This repository accompanies the manuscript:

RuralEdgeHealth: A Sustainable Offline Mobile Edge AI Reference Architecture for Intelligent IoT Sensor Classification in Resource-Constrained Environments

Journal: Array
Manuscript Number: ARRAY-D-25-01450
Status: Under review
Main Contributions

This work provides:

A reusable five-layer reference architecture for offline mobile edge AI
A structured framework for intelligent IoT sensor classification on entry-level Android devices.
A practical implementation for resource-constrained environments
Demonstrating fully offline inference without cloud dependency.
A comparative evaluation of lightweight machine learning models
Showing that tree-based models, particularly Random Forest, provide strong deployment trade-offs.
Evidence-based insights into usability and accessibility
Supporting more inclusive design for edge AI systems.
An open-source implementation for reproducibility
Enabling further research, validation, and extension across multiple IoT domains.
Development Roadmap
Phase 1: Reference Architecture and Technical Validation
Offline-first mobile edge AI implementation
Lightweight model benchmarking
Cross-device technical validation
Preliminary usability evaluation
Phase 2: Accessibility and Generalization
Enhanced interfaces for low-literacy and non-technical users
Broader BLE sensor support
Stronger domain generalization across IoT applications
Expanded reproducibility and deployment documentation
Phase 3: Broader Deployment and Research Extension
Real-world pilot adaptation
Multi-domain IoT extensions
Advanced runtime and energy optimization
Collaborative research development
Citation

If you use this repository in your research, please cite:

@article{wakili2025ruraledgehealth,
  title={RuralEdgeHealth: A Sustainable Offline Mobile Edge AI Reference Architecture for Intelligent IoT Sensor Classification in Resource-Constrained Environments},
  author={Wakili, Abubakar and Bakkali, Sara},
  journal={Array},
  year={2025},
  note={Under review},
  url={https://github.com/abubakarwakili9/RuralEdgeHealth}
}
Authors
Abubakar Wakili – Lead Researcher
Sara Bakkali – Co-Researcher

School of Digital Engineering and Artificial Intelligence
Euromed University of Fez, Morocco

License

This project is licensed under the MIT License. See the LICENSE file for details.

Contributing

Contributions are welcome, especially in the following areas:

Bug fixes and stability improvements
Documentation enhancement
Accessibility improvement
BLE sensor integration extension
Interface localization
Reproducibility and benchmarking support

Please open an issue or submit a pull request to contribute.

Impact

RuralEdgeHealth supports inclusive digital infrastructure by demonstrating that intelligent IoT sensor classification can operate on affordable and widely available mobile hardware without persistent connectivity.

The work contributes to broader goals in:

Sustainable and accessible edge AI
Rural and low-connectivity digital systems
Intelligent IoT deployment in constrained settings
Open and reproducible applied research

RuralEdgeHealth is designed as a reusable foundation for offline mobile edge AI in intelligent IoT systems.
