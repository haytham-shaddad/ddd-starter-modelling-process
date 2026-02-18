# ddd-discover: Collaborative Domain Discovery

## Purpose
Discover and understand the domain visually and collaboratively, building shared knowledge across the entire team.

## Why It Matters
- Cannot skip discovery in DDD - it's the most crucial aspect
- Shared understanding enables better software decisions
- Domain knowledge spread across team creates flexibility
- Deep understanding allows team to contribute product improvements
- Misunderstanding the domain leads to misguided architecture

## Core Principle: Discovery is Continuous
Success with DDD requires frequent discovery sessions. There is always more to learn about the domain. Teams should practice discovery techniques regularly, not as one-time events.

## Key Activities

### Collaborative Exploration
- Bring together diverse perspectives (developers, domain experts, users)
- Use visual techniques to externalize knowledge
- Surface hidden assumptions and mental models
- Identify domain events, commands, and business processes
- Discover domain language and terminology

### Knowledge Sharing
- Transfer tacit knowledge from experts to entire team
- Create shared vocabulary (ubiquitous language)
- Expose conflicts in understanding
- Build collective ownership of domain knowledge

### Pattern Recognition
- Identify business processes and workflows
- Discover temporal sequences and dependencies
- Find inconsistencies and edge cases
- Recognize domain invariants and business rules

## Recommended Tools

### EventStorming
- **Purpose**: Rapidly explore complex domains through domain events
- **When**: Initial discovery, process exploration, finding bottlenecks
- **Format**: Timeline of domain events (orange stickies) on wall
- **Output**: Shared model of business processes and domain events
- **Best Practice**: Use experienced facilitator for first sessions
- **Link**: https://www.eventstorming.com/

### Domain Storytelling
- **Purpose**: Understand domain through storytelling
- **When**: Understanding workflows, communication between actors
- **Format**: Pictographic language showing actor interactions
- **Output**: Visual narratives of domain scenarios
- **Link**: https://domainstorytelling.org/

### Example Mapping
- **Purpose**: Explore business rules through concrete examples
- **When**: Understanding acceptance criteria, discovering edge cases
- **Format**: Rules, examples, and questions on colored cards
- **Output**: Shared understanding of behavior
- **Link**: https://cucumber.io/blog/bdd/example-mapping-introduction/

### User Journey Mapping
- **Purpose**: Understand user perspective through their journey
- **When**: Understanding user experience, identifying pain points
- **Format**: Visualization of user steps, touchpoints, emotions
- **Output**: User-centric view of processes
- **Link**: https://boagworld.com/audio/customer-journey-mapping/

### User Story Mapping
- **Purpose**: Organize user stories to see the whole
- **When**: Release planning, understanding user workflow
- **Format**: Two-dimensional map of user activities and stories
- **Output**: Prioritized view of user capabilities
- **Link**: https://www.jpattonassociates.com/user-story-mapping/

## Who to Involve
- Software designers, builders, testers
- Domain knowledge holders (subject matter experts)
- Product and business strategy experts
- People who understand customer needs and problems
- **Real end users** (critical for authentic understanding)

## Key Questions to Answer
1. What are the key domain events that occur?
2. What triggers these events?
3. Who are the actors in the domain?
4. What business processes exist?
5. What is the domain language?
6. What are the business rules and invariants?
7. What are the edge cases and exceptions?
8. Where is complexity hiding?
9. What assumptions are we making?
10. Where do mental models conflict?

## Success Criteria
- Team uses domain language naturally
- Developers can explain business processes
- Domain experts validate the model
- Hidden complexity is surfaced
- Shared artifacts visible to all
- Questions and gaps are identified
- Team has collective understanding, not siloed knowledge

## Common Pitfalls
- Only doing discovery once
- Not involving real users
- Letting one person (expert or developer) dominate
- Focusing on current technical implementation instead of domain
- Trying to capture everything perfectly instead of iterating
- Not using visual/tactile techniques
- Skipping facilitation training
- Rushing through discovery to "get to coding"

## EventStorming Specifics

### Event Types in EventStorming
- **Domain Events** (Orange): Things that happened
- **Commands** (Blue): Triggers for events
- **Aggregates** (Yellow): Entities that handle commands
- **Policies** (Lilac): Reactions to events
- **Read Models** (Green): Information needed
- **External Systems** (Pink): Outside integrations
- **Users/Actors** (Small yellow): People in the process
- **Hot Spots** (Red): Problems, questions, conflicts

### EventStorming Levels
1. **Big Picture**: Explore entire domain, find boundaries
2. **Process Modeling**: Detailed view of specific processes
3. **Software Design**: Design level for implementation

## Integration with Other Steps
- **Feeds into Decompose**: Events and processes inform sub-domain boundaries
- **Feeds into Define**: Domain model informs bounded context design
- **Feeds into Code**: Discoveries drive implementation
- **Iterative with all steps**: New code insights trigger rediscovery

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "What domain events would occur in [business process]?"
- "Help me prepare questions for an EventStorming session about [domain]"
- "What are typical actors in a [domain type] domain?"
- "Identify business rules in this [process description]"
- "What edge cases should we explore for [scenario]?"
- "Create a domain storytelling scenario for [use case]"

## Example Outputs
- EventStorming wall photo with annotated timeline
- Domain event list with triggers and outcomes
- Ubiquitous language glossary
- Process flow diagrams
- Business rule catalog
- Hot spots and questions list
- Domain storytelling pictographs
- User journey maps

## Tips for Success
- Book 2-4 hours minimum for effective sessions
- Use large wall space or digital whiteboard
- Start with domain events, not data structures
- Follow the timeline, left to right
- Let the model emerge, don't force predetermined structure
- Embrace hot spots - they indicate learning opportunities
- Take photos and digitize key learnings
- Schedule follow-up sessions - one is never enough
