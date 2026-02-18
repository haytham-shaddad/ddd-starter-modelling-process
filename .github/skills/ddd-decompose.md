# ddd-decompose: Domain Decomposition into Sub-domains

## Purpose
Decompose a large, complex domain into smaller, loosely-coupled sub-domains that can be understood and developed independently.

## Why It Matters
- **Reduced Cognitive Load**: Reason about parts independently
- **Team Autonomy**: Enable teams to work on separate parts
- **Loose Coupling**: Identify natural boundaries in the domain
- **High Cohesion**: Group related concepts together
- **Scalability**: Enable parallel development and evolution

## Key Activities

### Identify Sub-domains
- Look for natural boundaries in the domain
- Group related events and processes
- Find different rates of change
- Identify different business capabilities
- Recognize different models of the same concept

### Assess Coupling
- Identify dependencies between parts
- Find temporal coupling (sequence dependencies)
- Recognize information coupling (data sharing)
- Discover organizational coupling (team dependencies)

### Define Boundaries
- Draw clear lines between sub-domains
- Name each sub-domain using domain language
- Document the purpose of each sub-domain
- Identify the core business capability each supports

## Recommended Tools

### EventStorming with Sub-domains
- **Purpose**: Discover sub-domain boundaries through event clustering
- **When**: After big picture EventStorming
- **Technique**: Look for event clusters, pivotal events, and swimlanes
- **Output**: Event timeline partitioned into sub-domains
- **Credit**: Alberto Brandolini
- **Link**: https://www.eventstorming.com/

### Design Heuristics
- **Purpose**: Apply heuristics to identify boundaries
- **When**: Evaluating potential decompositions
- **Heuristics**: Business rules, lifecycle, rate of change, bounded context
- **Output**: Justified sub-domain boundaries
- **Link**: https://www.dddheuristics.com/

### Business Capability Modelling
- **Purpose**: Model business capabilities independent of organization
- **When**: Understanding business structure
- **Format**: Hierarchical capability map
- **Output**: Business capability model
- **Link**: https://www.slideshare.net/trondhr/from-capabilities-to-services-modelling-for-businessit-alignment-v2

### Context Maps
- **Purpose**: Visualize sub-domains and their relationships
- **When**: Documenting decomposition decisions
- **Format**: Diagram showing contexts and integration patterns
- **Output**: Visual sociotechnical architecture
- **Link**: https://speakerdeck.com/mploed/visualizing-sociotechnical-architectures-with-context-maps

### Independent Service Heuristics
- **Purpose**: Evaluate independence of services/sub-domains
- **When**: Validating decomposition
- **Heuristics**: Can deploy independently, has own data, etc.
- **Output**: Assessment of autonomy
- **Link**: https://github.com/TeamTopologies/Independent-Service-Heuristics

## Who to Involve
- Software designers, builders, testers
- Domain knowledge holders
- (Less business strategy focus than other steps)

## Decomposition Heuristics

### Look for Different Lifecycles
Sub-domains often have different lifecycles. A customer may have a different lifecycle than an order.

### Identify Different Rates of Change
Parts that change for different reasons should be separate. Pricing rules may change more frequently than customer information.

### Find Different Business Rules
Different sets of business rules indicate different sub-domains. Validation rules for orders vs. warehouse management.

### Recognize Different Language
When domain experts use different terminology or the same term differently, you've found a boundary.

### Spot Different Actors/Roles
Different users or roles often indicate different sub-domains.

### Observe Different Models
The same concept (e.g., "Product") may be modeled differently in different parts of the domain.

### Notice Organizational Boundaries
Existing team or department boundaries often align with domain boundaries.

### Identify Pivotal Events
Events that trigger different sub-domains to react are boundary indicators.

## Types of Sub-domains

### Core Domain
- Highest business value
- Competitive differentiator
- Where to invest most effort
- Custom-built with high quality
- Example: Recommendation engine for e-commerce

### Supporting Domain
- Necessary for business
- Not differentiating
- May be custom but simpler than core
- Adequate quality is sufficient
- Example: Order management for e-commerce

### Generic Domain
- Solved problem
- No competitive advantage
- Buy or use open source
- Don't build yourself
- Example: Authentication, payments

## Key Questions to Answer
1. What are the major business capabilities?
2. Where are natural boundaries in the domain?
3. Which parts change independently?
4. Where do models diverge?
5. What are the pivotal events?
6. Which parts are coupled and why?
7. Can teams work independently on different parts?
8. What are the communication patterns?

## Success Criteria
- Clear, named sub-domains
- Justification for each boundary
- Low coupling between sub-domains
- High cohesion within sub-domains
- Team can explain decomposition rationale
- Sub-domains align with business capabilities
- Different models of same concepts are recognized

## Common Pitfalls
- **Technical decomposition**: Breaking up by technical layers instead of business capabilities
- **Too granular**: Creating too many sub-domains too early
- **Too coarse**: Missing important boundaries
- **Ignoring organizational reality**: Creating boundaries that don't match team structure
- **Premature optimization**: Optimizing for scale before understanding domain
- **Missing core domain**: Not identifying what's truly differentiating
- **Uniform investment**: Treating all sub-domains as equally important

## Integration with Other Steps
- **Builds on Discover**: Uses domain knowledge from discovery
- **Feeds into Strategize**: Sub-domains are assessed for strategic value
- **Feeds into Connect**: Sub-domains must be connected for use cases
- **Feeds into Organise**: Sub-domain boundaries inform team boundaries
- **Feeds into Define**: Each sub-domain becomes one or more bounded contexts

## Patterns for Decomposition

### By Business Capability
Organize around what the business does (e.g., "Inventory Management").

### By Use Case
Organize around user goals (e.g., "Order Fulfillment").

### By Data Ownership
Organize around data lifecycle and ownership (e.g., "Product Catalog").

### By Bounded Context
Organize around linguistic boundaries (e.g., "Shipping Context").

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "What sub-domains might exist in [domain]?"
- "How should I decompose [business area] based on these events: [list]?"
- "Apply DDD heuristics to identify boundaries in [description]"
- "What business capabilities support [business function]?"
- "Identify different models of [concept] in this domain"
- "Evaluate coupling between [sub-domain A] and [sub-domain B]"
- "Is this a core, supporting, or generic sub-domain: [description]?"

## Example Outputs
- EventStorm annotated with sub-domain boundaries
- Context map showing sub-domains
- Business capability map
- Sub-domain catalog with descriptions
- Coupling analysis document
- Boundary decision records
- List of pivotal events at boundaries

## Validation Techniques
- Walk through use cases across boundaries
- Test independence: can one part change without affecting others?
- Check team understanding: can team members explain boundaries?
- Verify with domain experts: do boundaries make business sense?
- Assess autonomy: can teams deploy independently?

## Tips for Success
- Start with bigger chunks, refine over time
- Don't force perfect boundaries too early
- Accept that boundaries will evolve
- Use multiple heuristics, not just one
- Validate with concrete use cases
- Consider organizational constraints
- Document rationale for boundaries
- Be willing to challenge initial assumptions
