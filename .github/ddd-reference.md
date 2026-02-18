# DDD Tools and Techniques Reference Guide

This reference guide provides quick access to all tools, techniques, and resources mentioned in the DDD Starter Modelling Process, organized for AI agent and developer use.

## Quick Navigation
- [Visual Collaboration Tools](#visual-collaboration-tools)
- [Strategic Tools](#strategic-tools)
- [Tactical Tools](#tactical-tools)
- [Organizational Tools](#organizational-tools)
- [Architecture Patterns](#architecture-patterns)
- [DDD Building Blocks](#ddd-building-blocks)
- [Integration Patterns](#integration-patterns)
- [Team Patterns](#team-patterns)

## Visual Collaboration Tools

### EventStorming
- **Type**: Visual collaborative domain discovery
- **Levels**: Big Picture, Process Modeling, Software Design
- **URL**: https://www.eventstorming.com/
- **Best For**: Rapid domain exploration, finding boundaries, process understanding
- **Facilitator**: Recommended for first sessions
- **Materials**: Unlimited wall space, colorful sticky notes
- **Step**: Discover, Decompose, Connect, Define, Code

### Domain Storytelling
- **Type**: Narrative-based domain exploration
- **URL**: https://domainstorytelling.org/
- **Best For**: Understanding workflows, actor interactions
- **Format**: Pictographic language
- **Step**: Discover

### Example Mapping
- **Type**: Rule and scenario exploration
- **URL**: https://cucumber.io/blog/bdd/example-mapping-introduction/
- **Best For**: Discovering business rules, edge cases
- **Materials**: Colored cards (rules, examples, questions)
- **Step**: Discover

## Strategic Tools

### Business Model Canvas
- **Type**: Business model visualization
- **URL**: https://www.strategyzer.com/canvas/business-model-canvas
- **Best For**: Understanding how business creates value
- **Sections**: 9 building blocks of business model
- **Step**: Understand

### Core Domain Charts
- **Type**: Strategic domain assessment
- **URL**: https://github.com/ddd-crew/core-domain-charts
- **Best For**: Identifying core vs supporting vs generic domains
- **Axes**: Business differentiation × Model complexity
- **Step**: Strategize

### Wardley Mapping
- **Type**: Strategic positioning and evolution
- **URL**: https://learnwardleymapping.com/
- **Best For**: Understanding competitive landscape, evolution, build vs buy
- **Step**: Understand, Strategize

### Impact Mapping
- **Type**: Goal-driven planning
- **URL**: https://www.impactmapping.org/
- **Best For**: Connecting features to business goals
- **Step**: Understand

### User Story Mapping
- **Type**: User journey and release planning
- **URL**: https://www.jpattonassociates.com/user-story-mapping/
- **Best For**: Organizing stories, planning releases, understanding workflow
- **Step**: Understand, Discover

## Tactical Tools

### Bounded Context Canvas
- **Type**: Context definition tool
- **URL**: https://github.com/ddd-crew/bounded-context-canvas
- **Best For**: Defining context purpose, language, interfaces
- **Sections**: Name, Purpose, Language, Messages, Dependencies
- **Step**: Define

### Aggregate Design Canvas
- **Type**: Aggregate design tool
- **URL**: https://github.com/ddd-crew/aggregate-design-canvas
- **Best For**: Designing aggregates before coding
- **Sections**: Commands, Events, State, Invariants
- **Step**: Code

### Context Maps
- **Type**: Sociotechnical architecture visualization
- **URL**: https://speakerdeck.com/mploed/visualizing-sociotechnical-architectures-with-context-maps
- **Best For**: Showing contexts, relationships, team boundaries
- **Patterns**: Partnership, Customer-Supplier, Conformist, ACL, etc.
- **Step**: Decompose, Organise

### Domain Message Flow Modelling
- **Type**: Use case validation across contexts
- **URL**: https://github.com/ddd-crew/domain-message-flow-modelling
- **Best For**: Validating architecture with concrete scenarios
- **Format**: Sequence-like diagram across contexts
- **Step**: Connect

### Event Modeling
- **Type**: Complete system behavior specification
- **URL**: https://eventmodeling.org/posts/what-is-event-modeling/
- **Best For**: Comprehensive event-driven design
- **Step**: Code

## Organizational Tools

### Team Topologies
- **Type**: Organizational design patterns
- **URL**: https://teamtopologies.com/
- **Patterns**: Stream-aligned, Enabling, Complicated-subsystem, Platform
- **Interaction Modes**: Collaboration, X-as-a-Service, Facilitating
- **Step**: Organise

### Dynamic Reteaming
- **Type**: Team evolution patterns
- **URL**: https://leanpub.com/dynamicreteaming
- **Patterns**: One by one, Grow and split, Merging, Switching
- **Step**: Organise

### Independent Service Heuristics
- **Type**: Service independence assessment
- **URL**: https://github.com/TeamTopologies/Independent-Service-Heuristics
- **Best For**: Evaluating autonomy of services/teams
- **Step**: Decompose, Organise

## Architecture Patterns

### Hexagonal Architecture (Ports & Adapters)
- **Type**: Architectural pattern
- **URL**: https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)
- **Concept**: Domain core surrounded by adapters
- **Benefit**: Separate domain from infrastructure
- **Step**: Code

### Onion Architecture
- **Type**: Architectural pattern
- **URL**: https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/
- **Concept**: Domain at center, dependencies point inward
- **Benefit**: Dependency inversion
- **Step**: Code

### CQRS (Command Query Responsibility Segregation)
- **Type**: Architectural pattern
- **Concept**: Separate read and write models
- **Best For**: Different optimization needs for reads/writes
- **Step**: Connect, Code

### Event Sourcing
- **Type**: Persistence pattern
- **Concept**: Event log as source of truth
- **Best For**: Audit, temporal queries, event-driven systems
- **Step**: Code

## DDD Building Blocks

### Aggregate
- **Purpose**: Consistency boundary
- **Pattern**: Root entity + child entities/value objects
- **Rule**: External references only to root
- **Invariants**: Protected within aggregate

### Entity
- **Characteristic**: Has identity
- **Equality**: By ID
- **Mutability**: Changes over time

### Value Object
- **Characteristic**: No identity
- **Equality**: By value
- **Mutability**: Immutable
- **Examples**: Money, Address, DateRange

### Domain Event
- **Characteristic**: Immutable fact
- **Naming**: Past tense
- **Purpose**: Communicate state changes

### Repository
- **Purpose**: Aggregate persistence abstraction
- **Interface**: In domain layer
- **Implementation**: In infrastructure layer

### Domain Service
- **Purpose**: Operations not belonging to entity/value object
- **Characteristic**: Stateless
- **Examples**: Complex calculations, multi-aggregate operations

### Factory
- **Purpose**: Complex object creation
- **Benefit**: Ensures valid initial state

### Specification
- **Purpose**: Encapsulate business rules
- **Benefit**: Reusable, testable, combinable predicates

## Integration Patterns

### Context Map Patterns

#### Partnership
- **Relationship**: Mutual dependency
- **Coordination**: Joint planning
- **When**: Teams succeed/fail together

#### Customer-Supplier
- **Relationship**: Upstream/downstream
- **Coordination**: Customer needs drive supplier
- **When**: Clear dependency direction

#### Conformist
- **Relationship**: Downstream conforms to upstream
- **Coordination**: No influence on upstream
- **When**: Integrating with external systems

#### Anticorruption Layer (ACL)
- **Relationship**: Translate between models
- **Coordination**: Protect downstream from upstream
- **When**: Incompatible models, legacy integration

#### Shared Kernel
- **Relationship**: Shared subset of model
- **Coordination**: Careful coordination needed
- **When**: Very high coupling (use sparingly)

#### Open Host Service
- **Relationship**: Published API
- **Coordination**: Upstream provides stability
- **When**: Multiple downstream consumers

#### Separate Ways
- **Relationship**: No integration
- **Coordination**: None
- **When**: Coupling cost too high

### Communication Patterns

#### Synchronous (Request/Response)
- REST APIs, RPC
- When: Immediate response needed
- Trade-off: Coupling, availability dependency

#### Asynchronous (Event-Driven)
- Message queues, event streams
- When: Loose coupling desired
- Trade-off: Eventual consistency complexity

#### Orchestration
- Central coordinator
- When: Complex workflow, central visibility needed
- Trade-off: Central point of coupling

#### Choreography
- Distributed coordination via events
- When: Loose coupling, autonomy
- Trade-off: Harder to understand flow

## Team Patterns

### Stream-Aligned Team
- **Focus**: Business capability/user journey
- **Ownership**: End-to-end delivery
- **Primary Type**: Most teams

### Enabling Team
- **Focus**: Help other teams overcome obstacles
- **Interaction**: Facilitating, time-boxed
- **Examples**: Security, testing, architecture

### Complicated-Subsystem Team
- **Focus**: Complex component requiring specialists
- **Interaction**: X-as-a-Service
- **Examples**: ML models, video processing

### Platform Team
- **Focus**: Internal services and tools
- **Interaction**: Self-service
- **Goal**: Reduce cognitive load

## Additional Resources

### Books
- **Domain-Driven Design** by Eric Evans (Blue Book)
- **Implementing Domain-Driven Design** by Vaughn Vernon (Red Book)
- **Domain-Driven Design Distilled** by Vaughn Vernon
- **Learning Domain-Driven Design** by Vlad Khononov
- **Team Topologies** by Matthew Skelton & Manuel Pais

### Online Communities
- **DDD-Crew GitHub**: https://github.com/ddd-crew
- **Domain-Driven Design Community**: https://github.com/ddd-community

### Design Heuristics
- **URL**: https://www.dddheuristics.com/
- **Purpose**: Heuristics for identifying boundaries
- **Categories**: Business rules, lifecycle, rate of change

### Process Models

#### Model Exploration Whirlpool
- **URL**: https://domainlanguage.com/ddd/whirlpool/
- **Type**: Iterative refinement process
- **Steps**: Scenario → Model → Test → Refine

#### SAP DDD Kata
- **URL**: https://github.com/SAP/curated-resources-for-domain-driven-design/blob/main/ddd-kata.md
- **Purpose**: Practice DDD techniques
- **Format**: Exercise with requirements

## Common Acronyms

- **DDD**: Domain-Driven Design
- **BDD**: Behavior-Driven Development
- **TDD**: Test-Driven Development
- **CQRS**: Command Query Responsibility Segregation
- **ACL**: Anticorruption Layer
- **BPMN**: Business Process Model and Notation
- **UML**: Unified Modeling Language
- **C4**: Context, Containers, Components, Code (modeling)

## Quality Attributes

### Performance
- Response time, throughput, scalability

### Availability
- Uptime, fault tolerance, recovery

### Security
- Authentication, authorization, encryption, audit

### Maintainability
- Readability, testability, modularity

### Operability
- Monitoring, deployment, configuration

## Heuristics for Decomposition

1. **Different Lifecycles**: Customer ≠ Order
2. **Different Rates of Change**: Pricing ≠ Customer info
3. **Different Business Rules**: Order validation ≠ Warehouse management
4. **Different Language**: Same term, different meanings
5. **Different Actors/Roles**: Different users
6. **Different Models**: Same concept, different representations
7. **Organizational Boundaries**: Team/department alignment
8. **Pivotal Events**: Events triggering different domains

## Success Indicators

- Developers explain business concepts fluently
- Domain experts understand and validate the model
- Code changes align with domain changes
- Teams work independently with minimal blocking
- Business opportunities identified quickly
- System boundaries make sense to non-technical stakeholders
- Low coupling, high cohesion
- Fast flow of value to customers
