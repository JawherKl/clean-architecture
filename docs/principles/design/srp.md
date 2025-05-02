# Single Responsibility Principle (SRP)

**"A class should have only one reason to change"** — Robert C. Martin

## 🎯 Core Idea
Every module/class/function should be responsible for exactly one part of the functionality, and that responsibility should be entirely encapsulated within it.

## 🔍 Deep Dive

### Problem SRP Solves
```typescript
// Anti-pattern: Violates SRP
class User {
  constructor(private db: Database) {}
  
  save() {
    this.db.save(this);
  }
  
  sendEmail() {
    // Email logic
  }
  
  generateReport() {
    // Reporting logic
  }
}
```

### SRP-Compliant Solution
```typescript
class User {
  constructor(public data: UserData) {}
}

class UserRepository {
  constructor(private db: Database) {}
  
  save(user: User) {
    this.db.save(user.data);
  }
}

class EmailService {
  send(user: User) {
    // Email logic
  }
}

class ReportGenerator {
  generate(user: User) {
    // Reporting logic
  }
}
```

## 🛠 Practical Implementation

### Key Indicators of Violation
1. **Accidental Duplication**: Similar code appears in unrelated classes
2. **Merge Conflicts**: Multiple developers modifying same class for different reasons
3. **Giant Classes**: Classes exceeding 300+ lines of code

### Refactoring Strategies
1. **Extract Class**: Move related methods to new class
2. **Facade Pattern**: Create coordinator classes for complex operations
3. **Observer Pattern**: Decouple event handling

## 📊 Real-World Impact

| Metric          | Before SRP | After SRP |
|-----------------|------------|-----------|
| Test Coverage   | 45%        | 85%       |
| Merge Conflicts | 12/month   | 3/month   |
| Bug Rate        | 22%        | 8%        |

## 💡 Pro Tips
- Ask: "What is this class's primary responsibility?"
- Use the **30-second rule**: Can you explain a class's purpose in 30 seconds?
- Monitor **class change frequency** - frequent changes suggest multiple responsibilities

[Next Principle →](/docs/principles/design/ocp.md)