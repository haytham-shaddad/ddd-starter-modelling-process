# ddd-connect: Connect Sub-domains into Cohesive Architecture

## Purpose
Connect decomposed sub-domains into a loosely-coupled architecture that fulfills end-to-end business use-cases while minimizing unwanted coupling and complexity.

## Why It Matters
- **Use Case Validation**: Ensures decomposition supports real business scenarios
- **Coupling Management**: Identifies and minimizes dependencies
- **Complexity Discovery**: Surfaces hidden integration complexity
- **Architecture Validation**: Tests if boundaries work in practice
- **Communication Design**: Defines how parts collaborate
- **Performance Impact**: Reveals latency and throughput implications

## Key Activities

### End-to-End Use Case Mapping
- Select critical business use cases
- Map message flows across sub-domains
- Identify required interactions
- Validate boundary decisions
- Expose hidden dependencies

### Integration Pattern Selection
- Choose appropriate integration patterns
- Design message contracts
- Define synchronous vs asynchronous flows
- Plan for failure scenarios
- Consider consistency requirements

### Complexity Assessment
- Evaluate coupling introduced by connections
- Identify choreography vs orchestration needs
- Assess transaction boundaries
- Plan for eventual consistency
- Design compensating transactions

## Recommended Tools

### Domain Message Flow Modelling
- **Purpose**: Visualize message flows across sub-domains for use cases
- **When**: After sub-domain decomposition, before detailed design
- **Format**: Sequence diagram-like flow across bounded contexts
- **Elements**: Actors, commands, events, policies, read models
- **Output**: Validated architecture through concrete scenarios
- **Link**: https://github.com/ddd-crew/domain-message-flow-modelling

### Process Modelling EventStorming
- **Purpose**: Model detailed processes spanning sub-domains
- **When**: Exploring complex processes
- **Format**: Timeline with events, commands, actors, systems
- **Output**: Process view with integration points
- **Link**: https://www.eventstorming.com/

### Sequence Diagrams
- **Purpose**: Detail message sequences between components
- **When**: Designing specific interactions
- **Format**: UML sequence diagram
- **Output**: Technical integration specification
- **Link**: https://en.wikipedia.org/wiki/Sequence_diagram

### BPMN (Business Process Model and Notation)
- **Purpose**: Standardized process modeling
- **When**: Need formal process documentation
- **Format**: BPMN diagram with pools, lanes, flows
- **Output**: Business process specification
- **Link**: https://en.wikipedia.org/wiki/Business_Process_Model_and_Notation

## Who to Involve
- Software designers, builders, testers (primary)
- Domain knowledge holders
- Architecture specialists
- Infrastructure/DevOps for deployment implications

## Integration Patterns to Consider

### Synchronous Patterns
- **Request/Response**: Direct calls, REST APIs
- **When**: Immediate response needed, strong consistency
- **Trade-offs**: Coupling, availability dependency
- **Example**: Price check before order submission

### Asynchronous Patterns
- **Event-Driven**: Publish events, subscribers react
- **When**: Loose coupling desired, eventual consistency acceptable
- **Trade-offs**: Complexity, eventual consistency
- **Example**: Order placed → inventory reserved → shipping initiated

### Data Patterns
- **Shared Database**: Anti-pattern, avoid in new systems
- **Database per Service**: Own your data
- **CQRS**: Separate read and write models
- **Event Sourcing**: Event log as source of truth

### Orchestration vs Choreography
- **Orchestration**: Central coordinator directs process
- **Choreography**: Distributed, event-driven coordination
- **Consider**: Complexity, coupling, visibility needs

## Context Map Patterns

### Partnership
- Mutual dependency, coordinated planning
- Both succeed or fail together
- Example: Separate teams on tightly coordinated features

### Shared Kernel
- Shared subset of model, careful coordination needed
- High coupling, use sparingly
- Example: Core domain concepts shared between contexts

### Customer-Supplier
- Upstream/downstream relationship
- Customer needs drive supplier priorities
- Example: Payment context supplies billing context

### Conformist
- Downstream conforms to upstream model
- No influence on upstream
- Example: Integrating with external API

### Anticorruption Layer
- Translate between incompatible models
- Protect downstream from upstream changes
- Example: Legacy system integration

### Open Host Service
- Published API for multiple consumers
- Upstream provides stability for many downstreams
- Example: Product catalog API

### Published Language
- Well-documented, shared data format
- Example: Industry standard formats (HL7, SWIFT)

### Separate Ways
- No integration, duplicate capability if needed
- Avoid coupling cost
- Example: Independent mobile and web apps

## Key Questions to Answer
1. How do end-to-end use cases span sub-domains?
2. What messages need to be exchanged?
3. What are the failure modes?
4. Where is synchronous communication required?
5. Where can we use asynchronous communication?
6. What consistency guarantees are needed?
7. How do we handle distributed transactions?
8. What are the latency requirements?
9. What events should be published?
10. How do we version integration contracts?

## Success Criteria
- Critical use cases validated across boundaries
- Integration patterns documented
- Message contracts defined
- Failure scenarios addressed
- Performance characteristics understood
- Team understands message flows
- No hidden coupling discovered late

## Common Pitfalls
- **Chatty Interactions**: Too many fine-grained calls
- **Distributed Monolith**: Synchronous coupling everywhere
- **Data Coupling**: Sharing database instead of APIs
- **Ignoring Failures**: Not designing for partial failures
- **Premature Optimization**: Over-engineering before understanding needs
- **Uniform Patterns**: Using same integration style everywhere
- **Missing Contracts**: Implicit rather than explicit agreements
- **Temporal Coupling**: Requiring all services up simultaneously

## Domain Message Flow Elements

### Actors
- Users or external systems initiating flows
- Start point of use cases

### Commands
- Requests to change state
- Blue in EventStorming
- Example: "Place Order"

### Events
- Things that happened
- Orange in EventStorming
- Example: "Order Placed"

### Policies
- Automated reactions to events
- Lilac in EventStorming
- Example: "When Order Placed, then Reserve Inventory"

### Read Models
- Information queries
- Green in EventStorming
- Example: "View Available Products"

### Bounded Contexts
- Swimlanes in message flow
- Show context boundaries clearly

## Integration Considerations

### Consistency Models
- **Strong Consistency**: Immediate, ACID transactions
- **Eventual Consistency**: Async, eventual convergence
- **Saga Pattern**: Distributed transaction coordination
- **Trade-offs**: Complexity vs guarantees

### Failure Handling
- Retry strategies
- Circuit breakers
- Fallback behaviors
- Compensating actions
- Dead letter queues

### Versioning
- Contract evolution strategy
- Backward compatibility
- Consumer-driven contracts
- API versioning scheme

### Monitoring
- End-to-end tracing
- Message flow visibility
- Performance metrics
- Error tracking

## Integration with Other Steps
- **Builds on Decompose**: Uses identified sub-domains
- **Validates Decompose**: May reveal need to adjust boundaries
- **Feeds into Organise**: Team dependencies visible
- **Feeds into Define**: Integration contracts inform design
- **Iterative with Code**: Implementation may require adjustments

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "Create a domain message flow for [use case] across [sub-domains]"
- "What integration pattern fits [scenario]?"
- "How should [context A] and [context B] communicate for [requirement]?"
- "Design event flow for [business process]"
- "What failure scenarios exist for [integration]?"
- "Should this be synchronous or asynchronous: [description]?"
- "Create a sequence diagram for [use case]"

## Example Outputs
- Domain message flow diagrams for key use cases
- Integration pattern catalog
- Message/event schemas
- Context map with relationship patterns
- Sequence diagrams for complex flows
- Failure scenario playbook
- API contract specifications
- Event catalog

## Validation Techniques
- Walk through concrete scenarios
- Simulate failure conditions
- Review with domain experts for correctness
- Assess performance implications
- Check for hidden coupling
- Verify consistency requirements are met
- Test with prototype if uncertainty exists

## Tips for Success
- Start with most critical use cases
- Use concrete examples, not abstractions
- Make temporal sequences explicit
- Don't hide complexity, surface it
- Consider both happy path and failures
- Balance synchronous and asynchronous
- Document integration decisions and rationale
- Keep message contracts stable
- Version carefully
- Monitor message flows in production
- Iterate based on real-world performance
