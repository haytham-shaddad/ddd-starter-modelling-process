# ddd-define: Define Bounded Context Responsibilities

## Purpose
Define the roles, responsibilities, and design of each bounded context before committing to implementation.

## Why It Matters
- **Explicit Decisions**: Make design choices visible early
- **Collaborative Design**: Ensure team alignment before coding
- **Change is Cheap**: Easy to modify before implementation
- **Alternative Exploration**: Consider multiple designs
- **Technical Constraints**: Surface limitations and opportunities
- **Stakeholder Communication**: Visual models facilitate discussion

## Key Activities

### Define Context Purpose
- Articulate the business capability
- Identify strategic classification (core/supporting/generic)
- Define success criteria
- Establish context boundaries

### Model Domain Concepts
- Identify key domain entities
- Define aggregates and their boundaries
- Specify value objects
- Document domain events
- Catalog business rules

### Design Interfaces
- Define inbound contracts (APIs, commands)
- Specify outbound events
- Document dependencies on other contexts
- Design integration points

### Consider Technical Aspects
- Identify technology constraints/opportunities
- Plan data storage strategy
- Consider scalability requirements
- Address security concerns
- Plan for deployment model

## Recommended Tools

### Bounded Context Canvas
- **Purpose**: Collaborative design tool for defining bounded contexts
- **When**: Before detailed implementation begins
- **Sections**: Name, Purpose, Strategic Classification, Domain Language, Business Decisions, Inbound/Outbound Communication, Ubiquitous Language
- **Format**: Canvas workshop with team
- **Output**: Complete context definition
- **Link**: https://github.com/ddd-crew/bounded-context-canvas

### C4 System Context Diagram
- **Purpose**: Visualize context in system landscape
- **When**: Showing external dependencies
- **Level**: System context level of C4 model
- **Output**: Context boundary with external systems
- **Link**: https://c4model.com/#SystemContextDiagram

### Quality Storming
- **Purpose**: Discover quality attributes and architectural characteristics
- **When**: Identifying non-functional requirements
- **Format**: Workshop to surface quality needs
- **Output**: Quality attribute scenarios
- **Link**: https://speakerdeck.com/mploed/quality-storming

## Who to Involve
- Software designers, builders, testers (primary)
- Domain knowledge holders
- Product owners/managers
- Architects (for cross-cutting concerns)

## Bounded Context Canvas Sections

### Name
- Clear, meaningful name from domain language
- Reflects business capability
- Example: "Order Management", "Inventory"

### Purpose
- One sentence describing responsibility
- Business-focused, not technical
- Example: "Manages the lifecycle of customer orders from placement to fulfillment"

### Strategic Classification
- Core, Supporting, or Generic domain
- Informs investment level
- From "Strategize" step

### Business Decisions
- Key business rules and policies
- Invariants that must be protected
- Decision points in workflows
- Example: "Orders cannot be modified after shipment"

### Ubiquitous Language
- Key domain terms and definitions
- Precise meanings within this context
- May differ from other contexts
- Example: "Product: Purchasable item with SKU, price, inventory count"

### Model Traits
- Characteristics of the domain model
- Example: Event-sourced, CRUD, workflow-based
- Helps set implementation expectations

### Messages Consumed (Inbound)
- Commands from users/other contexts
- Events subscribed to
- Queries served
- Example: "PlaceOrder command", "ProductDiscontinued event"

### Messages Produced (Outbound)
- Events published
- Commands sent
- Queries made
- Example: "OrderPlaced event", "ReserveInventory command"

### Dependencies
- Other bounded contexts relied upon
- External systems
- Shared infrastructure
- Example: "Depends on Payment Context for charge processing"

### Open Questions/Assumptions
- Unknowns to be resolved
- Assumptions to validate
- Risks to mitigate
- Example: "Assumption: Payment processing completes within 30 seconds"

## Key Questions to Answer
1. What is this context responsible for?
2. What are the key domain concepts?
3. What business rules must it enforce?
4. What messages does it consume?
5. What messages does it produce?
6. What are its dependencies?
7. What are the quality requirements?
8. What is the ubiquitous language?
9. What technical constraints exist?
10. What are the unknowns?

## Success Criteria
- Clear context boundaries
- Documented business rules
- Defined interfaces (inbound/outbound)
- Team alignment on design
- Stakeholder understanding
- Technical constraints identified
- Ubiquitous language documented
- Open questions captured

## Common Pitfalls
- **Too Early**: Before understanding domain
- **Too Late**: After code is written
- **Skipping Collaboration**: Solo design instead of team activity
- **Technical Focus**: Focusing on how instead of what
- **Ignoring Constraints**: Not considering real limitations
- **Missing Language**: Not documenting ubiquitous language
- **Unstated Assumptions**: Hidden assumptions cause surprises
- **Over-specification**: Too much detail, not enough flexibility

## Design Considerations

### Aggregate Design
- What are the consistency boundaries?
- What is the lifecycle of key entities?
- What invariants must be protected?
- How are references handled?

### Event Design
- What domain events occur?
- What information do events carry?
- Who needs to know about events?
- How are events versioned?

### Command Design
- What operations are requested?
- What validation is required?
- What business rules apply?
- How are failures handled?

### Query Design
- What information is queried?
- What are the read patterns?
- Is CQRS appropriate?
- What are consistency requirements?

### Data Design
- What data is owned?
- What is the schema?
- How is data partitioned?
- What are retention requirements?

## Quality Attributes to Consider

### Performance
- Response time requirements
- Throughput needs
- Scalability targets

### Availability
- Uptime requirements
- Failure handling
- Recovery time objectives

### Security
- Authentication/authorization
- Data protection
- Audit requirements
- Compliance needs

### Maintainability
- Code organization
- Testing strategy
- Documentation needs

### Operability
- Monitoring requirements
- Deployment model
- Configuration management

## Context Map Relationships

Document relationships with other contexts:
- **Partnership**: Mutual dependency
- **Customer-Supplier**: Dependency direction
- **Conformist**: Accepting upstream model
- **Anticorruption Layer**: Translating upstream model
- **Shared Kernel**: Shared code (use sparingly)
- **Open Host Service**: Providing API
- **Separate Ways**: No integration

## Integration with Other Steps
- **Builds on all previous steps**: Uses all prior outputs
- **Refines Decompose**: Detailed boundaries
- **Refines Connect**: Specific message contracts
- **Refines Organise**: Team responsibilities clarified
- **Feeds into Code**: Blueprint for implementation
- **Iterates with Code**: Implementation insights refine definition

## Domain Model Patterns

### Aggregates
- Consistency boundaries
- Transaction scope
- Root entity
- Example: Order aggregate with OrderLine entities

### Entities
- Objects with identity
- Mutable over time
- Tracked individually
- Example: Customer, Product

### Value Objects
- Objects without identity
- Immutable
- Defined by attributes
- Example: Address, Money, DateRange

### Domain Services
- Operations not naturally belonging to entity/value object
- Stateless
- Example: PricingService

### Domain Events
- Things that happened
- Immutable facts
- Trigger reactions
- Example: OrderPlaced, PaymentReceived

### Repositories
- Access to aggregates
- Abstraction over storage
- Domain-focused interface
- Example: OrderRepository

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "Create a Bounded Context Canvas for [domain area]"
- "What ubiquitous language terms are needed for [context]?"
- "Identify aggregates in [context description]"
- "What domain events occur in [business process]?"
- "Design the inbound API for [context]"
- "What quality attributes matter for [context]?"
- "What business rules exist in [domain]?"
- "Identify value objects in [description]"

## Example Outputs
- Completed Bounded Context Canvas
- Ubiquitous language glossary
- Aggregate diagram
- Domain event catalog
- API contract specifications
- C4 system context diagram
- Quality attribute scenarios
- Architecture decision records

## Workshop Format

### Pre-work
- Gather relevant discovery materials
- Identify key stakeholders
- Prepare canvas template
- Set agenda

### During Workshop
1. **Intro** (10 min): Purpose and goals
2. **Name & Purpose** (10 min): Define identity
3. **Business Decisions** (20 min): Capture rules
4. **Language** (20 min): Define terms
5. **Messages** (20 min): Inbound and outbound
6. **Dependencies** (15 min): External needs
7. **Open Questions** (10 min): Capture unknowns
8. **Review** (10 min): Validate completeness

### Post-workshop
- Digitize canvas
- Share with stakeholders
- Track open questions
- Update as understanding evolves

## Validation Techniques
- Walk through use cases using the model
- Check business rules are enforceable
- Verify dependencies are necessary
- Ensure language is precise
- Test understanding with domain experts
- Review with other teams for integration clarity

## Tips for Success
- Collaborate, don't dictate
- Use visual tools
- Keep it business-focused
- Document assumptions
- Capture open questions
- Start simple, refine iteratively
- Validate with concrete scenarios
- Make implicit concepts explicit
- Update as you learn
- Share widely for feedback
- Don't over-design upfront
- Leave room for emergence
