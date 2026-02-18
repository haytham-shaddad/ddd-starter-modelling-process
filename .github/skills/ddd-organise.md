# ddd-organise: Organize Teams for Fast Flow and Autonomy

## Purpose
Organize autonomous teams optimized for fast flow, aligned with context boundaries, and structured to minimize dependencies.

## Why It Matters
- **Team Autonomy**: Enable independent work and decisions
- **Fast Flow**: Remove blockers and handoffs
- **Conway's Law**: System structure mirrors communication structure
- **Cognitive Load**: Right-size teams for manageable complexity
- **Purpose and Goals**: Clear ownership and accountability
- **Reduced Coordination**: Minimize cross-team dependencies

## Core Principles

### Team Self-Organization
Organization isn't done TO teams, it's done WITH teams. Teams should be involved in defining their own:
- Boundaries
- Interactions
- Responsibilities
- Goals and metrics

Example: Red Gate Software empowers teams to fully organize themselves through facilitated self-selection processes.

### Inverse Conway Maneuver
Design the team structure you want, and the architecture will follow. Use desired architecture to inform team boundaries.

## Key Activities

### Context-to-Team Alignment
- Align teams with bounded context boundaries
- One team may own multiple small contexts
- Large context may need multiple teams
- Minimize shared ownership of contexts

### Team Sizing
- Consider cognitive load on team
- Balance communication overhead
- Ensure sufficient expertise (bus factor)
- Typical size: 5-9 people

### Interaction Patterns
- Define how teams collaborate
- Minimize synchronous dependencies
- Design APIs and contracts between teams
- Establish communication protocols

### Organizational Constraints
- Work within available talent
- Respect organizational culture
- Consider geographic distribution
- Plan for growth and evolution

## Recommended Tools

### Context Maps (Sociotechnical)
- **Purpose**: Visualize contexts AND teams together
- **When**: Designing team structures
- **Format**: Context map with team annotations
- **Elements**: Bounded contexts, relationships, team boundaries
- **Output**: Sociotechnical architecture blueprint
- **Link**: https://speakerdeck.com/mploed/visualizing-sociotechnical-architectures-with-context-maps

### Team Topologies
- **Purpose**: Organizational patterns for fast flow
- **When**: Designing team interactions and types
- **Patterns**: Stream-aligned, enabling, complicated-subsystem, platform
- **Interaction Modes**: Collaboration, X-as-a-Service, facilitating
- **Output**: Team design with clear interactions
- **Link**: https://teamtopologies.com/

### Dynamic Reteaming
- **Purpose**: Evolve team structure over time
- **When**: Teams need to adapt to change
- **Patterns**: One by one, grow and split, merging, switching
- **Output**: Adaptive team organization
- **Link**: https://leanpub.com/dynamicreteaming

### Pioneers, Settlers, Town Planners
- **Purpose**: Match team type to domain maturity
- **When**: Determining team composition and focus
- **Types**: Pioneers (explore), Settlers (productize), Town Planners (scale)
- **Output**: Team type aligned with domain evolution stage
- **Link**: https://medium.com/mappingpractice/how-to-organise-yourself-f36f084a611b

## Who to Involve
- **Critical**: The people who will be on the teams
- Software designers, builders, testers
- Domain knowledge holders
- Product and business strategy experts
- Leadership (for organizational decisions)

## Team Topologies Patterns

### Stream-Aligned Teams
- **Purpose**: Deliver value streams to customers
- **Focus**: Business capability or user journey
- **Ownership**: End-to-end delivery
- **Example**: "Customer Orders" team
- **Primary type**: Most teams should be stream-aligned

### Enabling Teams
- **Purpose**: Help stream-aligned teams overcome obstacles
- **Focus**: Specialist capabilities (security, testing, architecture)
- **Interaction**: Collaboration and facilitating
- **Example**: DevOps enablement team
- **Temporary**: Often time-boxed engagements

### Complicated-Subsystem Teams
- **Purpose**: Build/maintain complex subsystems
- **Focus**: High-complexity component requiring specialists
- **Interaction**: X-as-a-Service to stream-aligned teams
- **Example**: ML model team, video processing team
- **Minimize**: Only where complexity justifies it

### Platform Teams
- **Purpose**: Provide internal services and tools
- **Focus**: Developer experience and productivity
- **Interaction**: X-as-a-Service, self-service
- **Example**: Cloud platform team, observability team
- **Goal**: Reduce cognitive load on stream teams

## Interaction Modes

### Collaboration
- Two teams work together for discovery
- High communication overhead
- Temporary, time-boxed
- Use when: exploring new territory

### X-as-a-Service
- One team provides service to others
- Low communication overhead
- Stable API/contract
- Use when: well-understood interface

### Facilitating
- Helping team assists another to learn
- One-directional support
- Time-boxed
- Use when: capability building needed

## Key Questions to Answer
1. How many teams do we have/need?
2. What bounded contexts does each team own?
3. How do teams interact?
4. What is each team's cognitive load?
5. Do teams have clear goals and purpose?
6. Can teams deploy independently?
7. What skills does each team need?
8. How do we handle shared responsibilities?
9. What are the communication patterns?
10. How do teams evolve over time?

## Success Criteria
- Teams have clear ownership and purpose
- Teams can work independently
- Minimal waiting on other teams
- Clear APIs/contracts between teams
- Teams can deploy without coordination
- Cognitive load is manageable
- Team members feel empowered
- Fast flow of value to customers

## Common Pitfalls
- **Component Teams**: Organized by technical layer, not business capability
- **Shared Ownership**: Multiple teams modifying same code
- **Too Many Dependencies**: Constant coordination needed
- **Cognitive Overload**: Team owns too much complexity
- **Unclear Boundaries**: Teams stepping on each other
- **Top-Down Only**: Not involving team members
- **Static Structure**: Never evolving team boundaries
- **Ignoring Conway's Law**: Hoping architecture won't mirror org structure

## Organizational Patterns

### Team Ownership Models

#### Single Team Per Context
- Ideal for medium-sized contexts
- Clear ownership
- Full autonomy
- Example: Payments team owns Payments context

#### Multiple Contexts Per Team
- For smaller, related contexts
- Reduces team count
- Team must manage multiple domains
- Example: Team owns both Shipping and Returns

#### Multiple Teams Per Context
- For very large contexts
- Need coordination within context
- Split by feature or sub-component
- Example: Large e-commerce catalog split into teams

### Context Relationship to Team Patterns

#### Partnership → Closely Collaborating Teams
- Joined planning and delivery
- Frequent communication
- Example: Frontend and backend teams for new feature

#### Customer-Supplier → X-as-a-Service
- Downstream team is customer
- Upstream team provides service
- Clear SLAs and contracts
- Example: Platform team serves app teams

#### Anticorruption Layer → Specialized Team
- May need dedicated integration team
- Protects core from legacy complexity
- Example: Legacy integration team

## Cognitive Load Management

### Types of Cognitive Load
1. **Intrinsic**: Domain complexity (inherent)
2. **Extraneous**: Environmental friction (reduce this)
3. **Germane**: Learning and growing (valuable)

### Strategies to Reduce Load
- Limit number of domains per team
- Provide good tooling and platforms
- Reduce coordination requirements
- Clear documentation and contracts
- Automation of toil
- Remove technical debt

### Load Assessment Questions
- How many domains must team understand?
- How many technologies/platforms?
- How many other teams to coordinate with?
- How much undifferentiated work?
- Can team deliver end-to-end?

## Integration with Other Steps
- **Builds on Decompose**: Uses sub-domain boundaries
- **Builds on Strategize**: Allocates best talent to core
- **Builds on Connect**: Understands team dependencies
- **Feeds into Define**: Team structure influences detailed design
- **Feeds into Code**: Teams execute implementation
- **Influences all steps**: Team structure affects all work

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "How should we organize teams around these contexts: [list]?"
- "What Team Topologies patterns fit [organization description]?"
- "Assess cognitive load for a team owning [contexts/domains]"
- "Design team interactions for [architectural scenario]"
- "Should we have one team or multiple teams for [context]?"
- "What enabling teams would help [organization]?"
- "How can we apply Inverse Conway Maneuver for [desired architecture]?"

## Example Outputs
- Context map with team boundaries marked
- Team topology diagram
- Team charter documents
- Interaction mode definitions
- Responsibility assignment matrix (RACI)
- Cognitive load assessment
- Team evolution plan
- Communication protocol guide

## Team Charter Elements
- Team name and mission
- Owned bounded contexts
- Key responsibilities
- Success metrics
- Team composition and roles
- Interaction modes with other teams
- Communication channels
- Decision-making authority

## Tips for Success
- Start with team purpose and goals
- Involve teams in the design
- Design for evolution, not permanence
- Balance autonomy with alignment
- Minimize team dependencies
- Right-size teams for cognitive load
- Provide enabling teams for common needs
- Use platform teams to reduce toil
- Clear contracts between teams
- Measure flow metrics (lead time, deployment frequency)
- Iterate based on feedback
- Don't force everyone into same interaction mode
- Conway's Law is real - use it intentionally
