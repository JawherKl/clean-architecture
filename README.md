# Clean Architecture Template

<!--[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![CI/CD](https://github.com/JawherKl/clean-architecture/actions/workflows/main.yml/badge.svg)](https://github.com/JawherKl/clean-architecture/actions)-->

A practical implementation of Clean Architecture principles inspired by Robert C. Martin's "Clean Architecture" book. This repository serves as both a reference implementation and a template for new projects.

## 📖 Table of Contents

- [Core Principles](#-core-principles)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Testing Strategy](#-testing-strategy)
- [Documentation](#-documentation)
- [Case Studies](#-case-studies)
- [Contributing](#-contributing)
- [License](#-license)

## 🧠 Core Principles

This implementation follows the key tenets of Clean Architecture:

1. **Independent of Frameworks**: Core business logic doesn't depend on any external libraries
2. **Testable**: Business rules can be tested without UI, DB, or external services
3. **Independent of UI**: UI can change easily without changing business rules
4. **Independent of Database**: Business rules aren't bound to any specific database
5. **Independent of External Services**: Business rules don't know about external interfaces

## 🗂 Repository Structure

```
clean-architecture-project/
├── docs/          # Architectural documentation and principles
├── src/           # Source code organized by clean architecture layers
├── tests/         # Comprehensive test suites
├── examples/      # Practical implementations of concepts
└── scripts/       # Development and deployment utilities
```

### Key Layers:

1. **Core**: Enterprise business rules and entities
2. **Application**: Application-specific business rules and use cases
3. **Interface Adapters**: Controllers, presenters, and gateways
4. **Infrastructure**: Frameworks, databases, and external services
5. **Main**: Composition root and application entry point

## 🚀 Getting Started

### Prerequisites

- Node.js/Python/Java (depending on your implementation)
- Docker (for containerized dependencies)
- Make (for build automation)

### Installation

```bash
git clone https://github.com/JawherKl/clean-architecture.git
cd clean-architecture
npm install  # or pip install -r requirements.txt
```

### Running the Application

```bash
make run  # or npm start / python main.py
```

## 🧪 Testing Strategy

We employ a multi-layered testing approach:

```bash
make test       # Run all tests
make test-unit  # Run unit tests only
make test-int   # Run integration tests
make test-e2e   # Run end-to-end tests
```

## 📚 Documentation

Explore our comprehensive documentation:

- [Design Principles](docs/principles/design-principles)
- [Component Architecture](docs/principles/component-principles)
- [Case Studies](docs/case-studies)

## 🏗 Case Studies

Practical implementations included:

1. [Video Sales System](examples/video-sales) - Complete e-commerce example
2. [Embedded Systems](examples/embedded) - Clean Architecture in constrained environments
3. [Microservices](examples/services) - Service-oriented implementations

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

**Inspired by**: "Clean Architecture: A Craftsman's Guide to Software Structure and Design" by Robert C. Martin
```