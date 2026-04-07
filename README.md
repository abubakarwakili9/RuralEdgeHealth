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






cccc# RuralEdgeHealth

**A Lightweight Edge-AI Framework for Offline Vital Signs Monitoring in Resource-Constrained IoT Healthcare Systems**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://developer.android.com)
[![Language](https://img.shields.io/badge/Language-Kotlin-purple.svg)](https://kotlinlang.org)
[![Phase](https://img.shields.io/badge/Development-Phase%201%20Validation-blue.svg)](GETTING_STARTED.md)

## 🎯 Overview

RuralEdgeHealth is an innovative healthcare monitoring system that brings AI-powered health assessment to underserved populations without requiring internet connectivity. The system addresses the healthcare needs of **2.6 billion people globally** who lack reliable internet access.

> **Phase 1 Status:** This foundational implementation successfully establishes technical feasibility and development priorities for advancing toward deployment-ready status. The system demonstrates sophisticated AI performance on entry-level devices while identifying specific accessibility improvements for equitable deployment.

## ✨ Key Features

- 🔄 **Offline-First Architecture**: Complete functionality without internet connectivity
- 📱 **Entry-Level Hardware Support**: Optimized for 2GB RAM Android 8.0+ devices  
- 🤖 **Model Performance**: 98.25% classification accuracy with <100ms inference time
- 🔗 **IoT Integration**: Bluetooth Low Energy sensor connectivity with manual fallback
- 🔋 **Energy Efficient**: <4% battery consumption per hour for sustained field operation
- 🌍 **Accessibility Focus**: Designed for diverse user populations and literacy levels

## 🚀 Quick Start

**New to RuralEdgeHealth?** 

📖 **[Complete Getting Started Guide →](GETTING_STARTED.md)**

### Rapid Setup (5 minutes)
```bash
# Clone and setup
git clone https://github.com/abubakarwakili9/RuralEdgeHealth.git
cd RuralEdgeHealth

# Open in Android Studio, sync Gradle, and run
# Detailed instructions: GETTING_STARTED.md
```

### Quick Test
1. 📱 Launch app → Register/Login
2. 👤 Add patient → Enter basic info  
3. 🏥 Health Assessment → Input vitals or connect BLE sensors
4. 🤖 View AI results → Real-time classification (<100ms)

**Need help?** See our **[detailed setup and usage guide](GETTING_STARTED.md)** with step-by-step instructions, troubleshooting, and demo workflows.

## 📊 Dataset

The healthcare IoT dataset used for training and validation is available in the [`data/`](data/) folder:

- **File**: [`healthcare_iot_dataset.csv`](data/healthcare_iot_dataset.csv)
- **Records**: 10,000 synthetic health monitoring records
- **Features**: 15 features including vital signs, device metrics, and contextual information
- **Classes**: Healthy (50%), Moderate (35%), Critical (15%)

For detailed dataset documentation, see [`data/README.md`](data/README.md).

## 🏗️ System Architecture

The architecture comprises a modular five-layer as follows:
- **Presentation and Interface Layer**: This provides an interactive user interface with multi-modal input support optimized for diverse user populations.
- **IoT Sensor Integration Layer**: The IoT Sensor Integration Layer manages standardized BLE medical device connectivity with intelligent fallback mechanisms.
- **Edge Intelligence & Processing Layer:**:This This layer orchestrates a lightweight AI pipeline optimized for resource-constrained inference.
- **Data Management & Persistence Layer**: This layer ensures Local storage with encryption and model caching. 
- **Infrastructure & Runtime  Layer**: The Infrastructure and the Runtime Layer provide cross-platform runtime optimization for diverse hardware configurations.
 
 
## 🔬 Phase 1 Validation Results

| Metric | Achievement | Hardware | Status |
|--------|-------------|----------|---------|
| Classification Accuracy | 98.25% | 2GB RAM Android 8.0+ | ✅ Validated |
| Inference Time | <100ms | Entry-level smartphones | ✅ Validated |
| Battery Consumption | <4%/hour | Sustained field operation | ✅ Validated |
| System Usability (Healthcare Workers) | 85.6 SUS | Professional deployment | ✅ Validated |
| Overall Task Completion | 93.3% | Cross-device testing | ✅ Validated |
| Accessibility (Rural Users) | 48.1 SUS | Requires enhancement | ⚠️ Phase 2 Priority |

### Key Phase 1 Achievements
- ✅ **Technical Feasibility Confirmed**: Clinical-grade AI operates successfully on entry-level devices
- ✅ **Cross-Device Validation**: Consistent performance across Android configurations  
- ✅ **Energy Efficiency Validated**: Sustained operation in resource-limited environments
- ✅ **Professional Usability**: Excellent acceptance among healthcare workers
- ⚠️ **Accessibility Insights**: Identified specific improvements needed for rural deployment

## 📄 Research Paper

This repository accompanies our research paper:

**"RuralEdgeHealth: A Lightweight Edge-AI Framework for Offline Vital Signs Monitoring in Resource-Constrained IoT Healthcare Systems"**

*Submitted to Array*

### Key Contributions:
- First complete offline-first edge AI healthcare system on entry-level devices
- Systematic accessibility evaluation across diverse user populations  
- Comprehensive technical validation with quantified deployment metrics
- Open-source implementation supporting global research reproducibility

## 📖 Documentation

| Document | Description | Audience |
|----------|-------------|----------|
| **[Getting Started Guide](GETTING_STARTED.md)** | Complete setup, usage, and testing instructions | Developers, Researchers |
| **[Dataset Documentation](data/README.md)** | Detailed dataset information and usage | Data Scientists, ML Engineers |
| **[API Documentation](docs/API.md)** | Technical API reference *(Coming Soon)* | Integration Developers |
| **[Deployment Guide](docs/DEPLOYMENT.md)** | Production deployment instructions *(Phase 2)* | Healthcare Organizations |

## 📊 Model Information

- **Algorithm**: Random Forest (optimized with ONNX)
- **Training Data**: 10,000 synthetic healthcare records
- **Validation**: 5-fold cross-validation with SMOTETomek balancing
- **Optimization**: ONNX Runtime v1.17.0 with ARM architecture optimization
- **Model Location**: `app/src/main/assets/random_forest_model.onnx`
- **Performance**: 98.25% accuracy, F1-score: 0.9825, ROC-AUC: 0.9989

## 🗺️ Development Roadmap

### ✅ Phase 1: Technical Validation (Current)
- Core offline-first edge AI system
- Cross-device performance validation
- Basic accessibility evaluation
- Open-source release for reproducibility

### 🔄 Phase 2: Accessibility Enhancement (Planned)
- Enhanced UI for rural/low-literacy users (Target: >75 SUS)
- Expanded BLE sensor ecosystem support
- Advanced clinical decision support features
- Comprehensive deployment documentation

### 🎯 Phase 3: Production Deployment (Future)
- Large-scale clinical validation studies
- Healthcare system integration APIs
- Multi-language support and localization
- Regulatory compliance frameworks

## 📚 Citation

If you use this code or dataset in your research, please cite:

```bibtex
@article{wakili2025ruraledgehealth,
  title={RuralEdgeHealth: A Lightweight Edge-AI Framework for Offline Vital Signs Monitoring in Resource-Constrained IoT Healthcare Systems},
  author={Wakili, Abubakar and Bakkali, Sara},
  journal={Array},
  year={2025},
  note={Manuscript submitted for publication},
  url={https://github.com/abubakarwakili9/RuralEdgeHealth}
}
```

## 🔗 Links

- **📊 Dataset**: [data/synthetic_healthcare_iot_dataset_enhanced.csv](data/synthetic_healthcare_iot_dataset_enhanced.csv)
- **📖 Getting Started**: [GETTING_STARTED.md](GETTING_STARTED.md)
- **📋 Documentation**: [data/README.md](data/README.md)
- **📄 Paper**: [Array (Under Review)](https://www.sciencedirect.com/journal/array)

## 👥 Authors

- **Abubakar Wakili** - *Lead Researcher* - [a.wakili@ueuromed.org](mailto:a.wakili@ueuromed.org)
- **Sara Bakkali** - *Co-Researcher* - [s.bakkali@insa.ueuromed.org](mailto:s.bakkali@insa.ueuromed.org)

*School of Digital Engineering and Artificial Intelligence*  
*Euromed University of Fez, Morocco*

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

We welcome contributions! This Phase 1 validation establishes the foundation for community-driven development:

- 🐛 **Bug Reports**: Help us improve system reliability
- 💡 **Feature Requests**: Suggest enhancements for Phase 2 development  
- 🔍 **Accessibility Testing**: Test with diverse user populations
- 📚 **Documentation**: Improve setup and usage guides
- 🌍 **Localization**: Add support for additional languages

Please see our **[Getting Started Guide](GETTING_STARTED.md)** for development setup instructions.

## 🌟 Impact & Recognition

This research supports **digital health equity** by extending AI-driven healthcare monitoring to underserved populations globally, advancing:

- 🎯 **UN Sustainable Development Goal 3**: Good Health and Well-being
- 🏥 **WHO Universal Health Coverage**: Equitable access to quality health services
- 🌍 **Digital Health Equity**: Accessible AI for 2.6 billion underserved people

### Phase 1 Validation Impact
- **Technical Foundation**: Proven feasibility of offline-first edge AI on accessible hardware
- **Research Reproducibility**: Open-source implementation enables global collaboration
- **Development Priorities**: Evidence-based roadmap for equitable deployment
- **Academic Contribution**: First complete system addressing digital health infrastructure barriers

---

*Made with ❤️ for global health equity*

**Ready to get started?** 🚀 **[Follow our complete setup guide →](GETTING_STARTED.md)**
