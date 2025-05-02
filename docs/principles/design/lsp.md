# Liskov Substitution Principle (LSP)

**"Objects should be replaceable with instances of their subtypes without altering correctness"** — Barbara Liskov

## 🎯 Core Idea
Subtypes must be behaviorally compatible with their base types.

## 🔍 Deep Dive

### Classic Violation (Rectangle/Square Problem)
```typescript
class Rectangle {
  constructor(public width: number, public height: number) {}
  
  setWidth(width: number) {
    this.width = width;
  }
  
  setHeight(height: number) {
    this.height = height;
  }
}

class Square extends Rectangle {
  setWidth(width: number) {
    super.setWidth(width);
    super.setHeight(width); // Violates LSP
  }
  
  setHeight(height: number) {
    super.setHeight(height);
    super.setWidth(height); // Violates LSP
  }
}

function testArea(shape: Rectangle) {
  shape.setWidth(4);
  shape.setHeight(5);
  return shape.width * shape.height; // Fails for Square
}
```

### LSP-Compliant Solution
```typescript
interface Shape {
  area(): number;
}

class Rectangle implements Shape {
  constructor(private width: number, private height: number) {}
  
  area() {
    return this.width * this.height;
  }
}

class Square implements Shape {
  constructor(private side: number) {}
  
  area() {
    return this.side * this.side;
  }
}
```

## 🛠 Practical Implementation

### LSP Enforcement Techniques
1. **Design by Contract**: Preconditions/postconditions
2. **Behavioral Subtyping**: Subtype method signatures compatible
3. **Unit Testing**: Shared test suites for base and derived classes

### LSP Impact Matrix
| Scenario               | Passes LSP? | Why? |
|------------------------|-------------|------|
| Subtype strengthens preconditions | ❌ | Narrower input range |
| Subtype weakens postconditions | ❌ | Broader output guarantees |
| Subtype throws new exceptions | ❌ | Changes failure modes |

## 💡 Pro Tips
- Use **interface segregation** to prevent "fat interfaces"
- Apply **composition over inheritance** when behavioral changes occur
- Create **shared contract tests** for interface implementations

[Next Principle →](/docs/principles/design/isp.md)