# DDD Skills for GitHub Copilot

This directory contains individual skill guides for each step of the Domain-Driven Design (DDD) Starter Modelling Process. Each skill is prefixed with `ddd-` for easy discovery and use with GitHub Copilot CLI and VS Code.

## Available Skills

### Process Skills (8 Steps)

1. **[ddd-understand](ddd-understand.md)** - Align with Business Model and Goals
   - Business model alignment
   - User needs understanding  
   - Strategic goal clarity
   - Tools: Business Model Canvas, Impact Mapping, Wardley Mapping

2. **[ddd-discover](ddd-discover.md)** - Collaborative Domain Discovery
   - Visual collaborative exploration
   - Knowledge sharing across team
   - EventStorming and domain storytelling
   - Building ubiquitous language

3. **[ddd-decompose](ddd-decompose.md)** - Domain Decomposition into Sub-domains
   - Identifying sub-domain boundaries
   - Loose coupling and high cohesion
   - Design heuristics application
   - Core vs supporting vs generic classification

4. **[ddd-strategize](ddd-strategize.md)** - Identify and Prioritize Core Domains
   - Strategic domain assessment
   - Build vs buy decisions
   - Investment prioritization
   - Core Domain Charts

5. **[ddd-connect](ddd-connect.md)** - Connect Sub-domains into Architecture
   - End-to-end use case validation
   - Integration pattern selection
   - Domain message flows
   - Coupling management

6. **[ddd-organise](ddd-organise.md)** - Organize Teams for Fast Flow
   - Team structure design
   - Team Topologies patterns
   - Cognitive load management
   - Conway's Law application

7. **[ddd-define](ddd-define.md)** - Define Bounded Context Responsibilities
   - Context purpose and boundaries
   - Ubiquitous language documentation
   - Interface design (inbound/outbound)
   - Bounded Context Canvas

8. **[ddd-code](ddd-code.md)** - Implement the Domain Model
   - Aggregate implementation
   - Value objects and entities
   - Domain events and repositories
   - Clean architecture patterns

## How to Use These Skills

### With GitHub Copilot Chat (VS Code)

In VS Code with GitHub Copilot Chat:

```
@workspace Using ddd-discover skill, help me prepare for an EventStorming session about order management
```

```
Apply ddd-decompose to identify sub-domains in this e-commerce description: [paste description]
```

```
Use ddd-code to implement an Order aggregate with these rules: orders can't be modified after shipping
```

### With GitHub Copilot CLI

Reference skills in your prompts:

```bash
# Ask for guidance on a specific step
gh copilot suggest "using ddd-strategize, create a core domain chart for a healthcare system"

# Get help with implementation
gh copilot suggest "using ddd-code, implement value objects for address and money"
```

### General Usage

Each skill file contains:

- **Purpose**: What the skill helps you accomplish
- **Why It Matters**: Business and technical importance
- **Key Activities**: Main tasks involved
- **Recommended Tools**: Specific tools and techniques
- **Who to Involve**: Required participants
- **Key Questions**: Questions to answer during this step
- **Success Criteria**: How to know you're done
- **Common Pitfalls**: Mistakes to avoid
- **AI Agent Prompts**: Ready-to-use prompts for AI assistance
- **Example Outputs**: What artifacts you should create
- **Tips for Success**: Best practices

## Skill Dependencies

Skills build on each other in sequence:

```
ddd-understand → ddd-discover → ddd-decompose → ddd-strategize
                                        ↓
                                  ddd-connect
                                        ↓
                                  ddd-organise
                                        ↓
                                   ddd-define
                                        ↓
                                    ddd-code
```

However, in practice, you'll iterate and jump between steps based on learning and needs.

## Cross-References

- **Main Instructions**: See [../.github/copilot-instructions.md](../copilot-instructions.md) for overall DDD guidance
- **Reference Guide**: See [../.github/ddd-reference.md](../ddd-reference.md) for tools and patterns catalog
- **Prompts Catalog**: See [../.github/copilot-prompts.md](../copilot-prompts.md) for curated prompts

## Quick Start

New to DDD? Start with these skills in order:

1. **ddd-understand** - Get business context
2. **ddd-discover** - Learn the domain collaboratively (most critical!)
3. **ddd-decompose** - Break down into manageable parts
4. **ddd-strategize** - Identify where to focus effort

Then iterate through all 8 steps as you refine your understanding.

## Contributing

These skills are optimized for AI consumption while remaining human-readable. Each skill follows this structure:

- Clear, concise purpose statement
- Practical guidance over theory
- Concrete examples and prompts
- Links to authoritative resources
- Actionable success criteria

## License

These skills are derived from the DDD Starter Modelling Process, licensed under [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

## Additional Resources

- Main Repository: [DDD Starter Modelling Process](../../README.md)
- DDD Crew GitHub: https://github.com/ddd-crew
- EventStorming: https://www.eventstorming.com/
- Domain-Driven Design Community: https://github.com/ddd-community
