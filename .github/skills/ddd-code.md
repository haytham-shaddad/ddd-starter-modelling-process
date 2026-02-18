# ddd-code: Implement the Domain Model

## Purpose
Implement the domain model in code, aligning software structure with domain structure to maximize changeability and clarity.

## Why It Matters
- **Domain Alignment**: Code reflects business concepts
- **Changeability**: Domain changes map to code changes
- **Shared Understanding**: Code is a shared language with domain experts
- **Minimize Misunderstandings**: Collaborative modeling reduces errors
- **Maintainability**: Clear domain logic is easier to maintain
- **Business Rules**: Logic belongs in domain, not scattered

## Key Activities

### Aggregate Implementation
- Code aggregate roots and entities
- Enforce invariants
- Define aggregate boundaries
- Implement business logic within aggregates

### Value Object Implementation
- Create immutable value objects
- Implement equality by value
- Use for domain concepts

### Domain Event Implementation
- Define and publish domain events
- Event structure and naming
- Event versioning strategy

### Repository Implementation
- Abstract persistence
- Aggregate-oriented interface
- Hide infrastructure concerns

### Domain Service Implementation
- Operations spanning aggregates
- Stateless coordination logic

### Application Layer
- Use cases and application services
- Orchestrate domain objects
- Transaction boundaries

## Recommended Tools

### Aggregate Design Canvas
- **Purpose**: Design aggregates before coding
- **When**: Modeling tactical domain design
- **Elements**: Commands, events, state, invariants, external dependencies
- **Output**: Aggregate specification
- **Link**: https://github.com/ddd-crew/aggregate-design-canvas

### Design-Level EventStorming
- **Purpose**: Detailed process and aggregate discovery
- **When**: Drilling into specific processes
- **Format**: Detailed timeline with aggregates, policies, read models
- **Output**: Implementation-ready model
- **Link**: https://www.eventstorming.com/

### Event Modeling
- **Purpose**: Complete system behavior specification
- **When**: Need comprehensive event-driven design
- **Format**: Timeline with events, commands, views, automation
- **Output**: Complete system blueprint
- **Link**: https://eventmodeling.org/posts/what-is-event-modeling/

### C4 Component Diagrams
- **Purpose**: Show internal structure of bounded context
- **When**: Documenting architecture
- **Level**: Component level of C4 model
- **Output**: Component architecture diagram
- **Link**: https://c4model.com/#ComponentDiagram

### Hexagonal Architecture (Ports & Adapters)
- **Purpose**: Separate domain from infrastructure
- **When**: Designing overall structure
- **Pattern**: Core domain surrounded by adapters
- **Output**: Layered architecture
- **Link**: https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)

### Onion Architecture
- **Purpose**: Dependency inversion with domain at center
- **When**: Designing overall structure
- **Pattern**: Concentric layers with domain core
- **Output**: Layered architecture
- **Link**: https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/

### Model Exploration Whirlpool
- **Purpose**: Iterative refinement process
- **When**: Evolving domain model
- **Process**: Scenario exploration → modeling → testing
- **Output**: Refined, validated model
- **Link**: https://domainlanguage.com/ddd/whirlpool/

### Mob Programming
- **Purpose**: Collaborative coding
- **When**: Complex domain logic, knowledge sharing
- **Format**: Whole team codes together
- **Output**: Shared understanding in code
- **Link**: https://mobprogramming.org/

### UML (Unified Modeling Language)
- **Purpose**: Standard modeling notation
- **When**: Documenting designs
- **Diagrams**: Class, sequence, state machine
- **Output**: Technical documentation
- **Link**: https://en.wikipedia.org/wiki/Unified_Modeling_Language

## Who to Involve
- Software designers, builders, testers (primary)
- Domain experts (for validation and pairing)
- Architects (for patterns and structure)

## Code Organization Patterns

### Layered Architecture
```
- Presentation Layer (UI, API)
- Application Layer (Use Cases)
- Domain Layer (Business Logic)
- Infrastructure Layer (Persistence, External Services)
```

### Hexagonal Architecture
```
- Core: Domain Model
- Ports: Interfaces
- Adapters: Implementations (HTTP, DB, Message Queue)
```

### Package by Feature
```
- feature1/ (order-management/)
  - domain/
  - application/
  - infrastructure/
  - api/
```

### Package by Aggregate
```
- order/
  - Order.java
  - OrderLine.java
  - OrderRepository.java
- customer/
  - Customer.java
  - CustomerRepository.java
```

## Domain Model Building Blocks

### Aggregates
- **Purpose**: Consistency boundary
- **Pattern**: Root entity + child entities/value objects
- **Rule**: External references only to root
- **Implementation**: Enforce invariants in methods
- **Example**:
  ```java
  class Order { // Aggregate Root
    private List<OrderLine> lines;
    void addLine(Product product, Quantity qty) {
      // Enforce invariant: order total ≤ credit limit
    }
  }
  ```

### Entities
- **Identity**: Has unique identifier
- **Mutability**: State changes over time
- **Equality**: By ID, not attributes
- **Example**:
  ```java
  class Customer {
    private CustomerId id;
    private Email email;
    // Identity-based equality
  }
  ```

### Value Objects
- **No Identity**: Defined by attributes
- **Immutability**: Cannot change after creation
- **Equality**: By value, not reference
- **Example**:
  ```java
  class Money {
    private final BigDecimal amount;
    private final Currency currency;
    // Immutable, value-based equality
  }
  ```

### Domain Events
- **Immutability**: Represent facts
- **Past Tense**: Things that happened
- **Naming**: Domain language
- **Example**:
  ```java
  class OrderPlaced {
    private OrderId orderId;
    private CustomerId customerId;
    private Instant occurredAt;
  }
  ```

### Repositories
- **Abstraction**: Hide persistence details
- **Aggregate-oriented**: Work with whole aggregates
- **Interface in Domain**: Implementation in infrastructure
- **Example**:
  ```java
  interface OrderRepository {
    Order findById(OrderId id);
    void save(Order order);
  }
  ```

### Domain Services
- **Stateless**: No instance state
- **Coordination**: Operations across aggregates
- **Domain Logic**: Not application orchestration
- **Example**:
  ```java
  class TransferService {
    void transfer(Account from, Account to, Money amount) {
      from.debit(amount);
      to.credit(amount);
    }
  }
  ```

### Factories
- **Complex Creation**: When creation is complex
- **Invariants**: Ensure valid initial state
- **Encapsulation**: Hide creation details
- **Example**:
  ```java
  class OrderFactory {
    Order createOrder(Customer customer, List<OrderLine> lines) {
      // Complex creation logic
    }
  }
  ```

## Key Principles

### Ubiquitous Language in Code
- Class names from domain
- Method names from domain
- Variable names from domain
- Comments in domain terms

### Make Implicit Concepts Explicit
- Hidden domain rules → value objects or entities
- Implicit processes → domain services
- Tacit knowledge → explicit code

### Model Integrity
- Protect invariants in aggregates
- Use types to make illegal states unrepresentable
- Fail fast with clear domain exceptions

### Bounded Context Boundaries
- Keep contexts separate (separate modules/namespaces)
- No shared domain objects across contexts
- Translate at boundaries (anticorruption layer)

### Side-Effect-Free Functions
- Separate queries from commands (CQS)
- Make side effects explicit
- Easier to reason about behavior

## Common Patterns

### Specification Pattern
- Encapsulate business rules
- Combinable predicates
- Example: `CustomerIsEligibleForDiscount`

### Strategy Pattern
- Varying algorithms/rules
- Example: Different pricing strategies

### State Pattern
- Object behavior changes with state
- Example: Order state machine

### Observer Pattern (Events)
- Decouple event producers from consumers
- Example: Domain event publishing

### Repository Pattern
- Aggregate persistence abstraction
- Example: `OrderRepository`

## Anti-Patterns to Avoid

### Anemic Domain Model
- **Problem**: Objects with only getters/setters, logic in services
- **Solution**: Put behavior with data in domain objects

### Feature Envy
- **Problem**: Method in one class using data from another
- **Solution**: Move method to class with data

### Primitive Obsession
- **Problem**: Using primitives (strings, ints) for domain concepts
- **Solution**: Create value objects (Email, OrderId, Money)

### Leaking Domain to UI
- **Problem**: UI depends on domain objects directly
- **Solution**: Use DTOs/view models at boundaries

### Transaction Script
- **Problem**: Procedural code, not object-oriented domain model
- **Solution**: Move logic into domain objects

### God Object
- **Problem**: One class does everything
- **Solution**: Split responsibilities, find aggregates

## Testing Strategy

### Unit Tests
- Test domain logic in isolation
- Fast, no dependencies
- Example: Test aggregate invariants

### Integration Tests
- Test repository implementations
- Test with real database
- Example: Test persistence round-trip

### Domain Tests (Specification by Example)
- Business scenario tests
- Given-When-Then format
- Example: Given order with items, when place order, then inventory reserved

### Acceptance Tests
- End-to-end use case tests
- Validate business requirements
- Example: Complete order flow

## Key Questions to Answer
1. What are the aggregates?
2. What are the invariants?
3. What domain events occur?
4. Where does business logic belong?
5. What are the value objects?
6. How are aggregates persisted?
7. What are the use cases?
8. How do we handle transactions?
9. How do we version the model?
10. How do we test domain logic?

## Success Criteria
- Code matches domain model
- Ubiquitous language in code
- Domain experts can read code
- Business rules in domain layer
- Invariants are protected
- Tests specify behavior
- Code is changeable
- Team understands model

## Common Pitfalls
- Starting with database schema
- Letting framework dictate domain model
- Skipping value objects
- Anemic domain model
- Not protecting invariants
- Large aggregates (too much in one)
- Scattered business logic
- Missing domain events
- Over-engineering early
- Under-testing domain logic

## Integration with Other Steps
- **Builds on Define**: Implements designed model
- **Validates all previous steps**: Reality check through code
- **Informs Define**: Coding insights improve design
- **Iterative**: Code → learn → refine model → code

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "Implement an aggregate for [domain concept] with these rules: [list]"
- "Create value objects for [domain concepts]"
- "Design domain events for [business process]"
- "Implement repository interface for [aggregate]"
- "Write domain service for [operation]"
- "How should I structure [bounded context] code?"
- "Create tests for [aggregate] invariant: [rule]"
- "Refactor this anemic model to rich domain model: [code]"

## Example Outputs
- Domain model code (aggregates, entities, value objects)
- Domain event definitions
- Repository interfaces and implementations
- Domain service implementations
- Application service/use case code
- Unit and integration tests
- Architecture documentation
- Code structure aligned with domain

## Development Practices

### Pair/Mob Programming
- Share domain understanding
- Real-time code review
- Knowledge distribution

### Test-Driven Development
- Specify behavior before implementation
- Design from usage perspective
- Refactor with confidence

### Continuous Refactoring
- Improve model as understanding grows
- Keep code aligned with domain
- Pay down technical debt

### Code Reviews
- Validate domain alignment
- Share knowledge
- Maintain quality

## Tips for Success
- Start with aggregates and their invariants
- Use value objects liberally
- Make domain events explicit
- Test business rules thoroughly
- Separate domain from infrastructure
- Keep aggregates small
- Use ubiquitous language everywhere
- Refactor as understanding improves
- Pair with domain experts
- Don't let persistence drive design
- Make illegal states unrepresentable
- Fail fast with meaningful errors
- Document key design decisions
- Keep domain layer framework-independent
- Evolve the model continuously
