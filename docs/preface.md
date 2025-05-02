# Preface: How to Use This Repository

## 🎯 Intended Audience

This repository serves:
- **Practicing developers** seeking architectural clarity
- **Tech leads** establishing project templates
- **Students** of software design principles
- **Architects** validating design decisions

## 📐 Structure Philosophy

We follow a **principle-first** approach:
1. **Core Layer**: Pure business objects (language primitives)
2. **Domain Layer**: Business rules and use cases
3. **Adapter Layer**: Interface implementations
4. **Infrastructure**: Framework-specific code

## 🛠 Usage Patterns

### As a Learning Tool
```bash
git clone https://github.com/JawherKl/clean-architecture
open docs/principles/srp.md  # Start with Single Responsibility Principle
```

### As a Project Template
```bash
npx degit JawherKl/clean-architecture my-project
rm -rf .git  # Start fresh history
```

### As a Reference
```bash
grep -r "interface Repository" src/core  # Find core contracts
```

## 🚨 Anti-Patterns We Avoid
- Framework contamination of business logic
- Mock-heavy testing that verifies implementation
- Premature optimization at architectural boundaries

[Explore Acknowledgments →](/docs/acknowledgments.md)