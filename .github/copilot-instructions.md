# Domain-Driven Design (DDD) Starter Modelling Process - AI Instructions

This repository contains a comprehensive guide for learning and applying Domain-Driven Design (DDD) principles. When working with this repository or applying DDD concepts, follow these guidelines.

## Core Principles

1. **Discovery is Continuous**: Domain knowledge is never complete. Always be prepared to revisit and refine understanding.
2. **Collaborative Modeling**: DDD is a team sport. Involve domain experts, developers, and stakeholders.
3. **Evolutionary Design**: The process is iterative, not linear. Expect to jump between steps based on new insights.
4. **Business Alignment**: Every technical decision should be aligned with business goals and user needs.
5. **Reduce Cognitive Load**: Decompose large problems into manageable sub-domains.

## The 8-Step Process

The DDD Starter Modelling Process consists of 8 interconnected steps:

1. **Understand** - Align with business model and goals
2. **Discover** - Collaboratively explore the domain
3. **Decompose** - Break domain into loosely-coupled sub-domains
4. **Strategize** - Identify core domains for differentiation
5. **Connect** - Design interactions between sub-domains
6. **Organise** - Structure autonomous teams aligned with contexts
7. **Define** - Detail bounded context responsibilities
8. **Code** - Implement the domain model

## When to Apply This Process

- Kicking off greenfield projects
- Beginning brownfield migrations
- Starting major programs of work
- Exploring domain for learning opportunities
- Assessing current project state
- Re-organizing teams
- Practicing or learning DDD

## Key DDD Concepts

### Bounded Context
A clear boundary within which a domain model is defined and applicable. Different contexts may have different models of the same concept.

### Sub-domain
A logical part of the overall domain. Can be:
- **Core Domain**: High business value, competitive advantage
- **Supporting Domain**: Necessary but not differentiating
- **Generic Domain**: Solved problems, use off-the-shelf solutions

### Context Map
Visual representation of bounded contexts and their relationships, showing integration patterns and team boundaries.

### Ubiquitous Language
A common, rigorous language between developers and domain experts, used in code and conversation.

## Recommended Tools by Step

Each step has associated tools. Prefer visual, collaborative techniques:

- **EventStorming** - Domain discovery and process modeling
- **Domain Storytelling** - Narrative-based domain exploration
- **Core Domain Charts** - Strategic domain assessment
- **Context Maps** - Sociotechnical architecture visualization
- **Bounded Context Canvas** - Context definition and design
- **Domain Message Flow** - Use-case validation across contexts
- **Aggregate Design Canvas** - Tactical domain modeling

## Process Adaptations

The process is flexible. Common adaptations:
- Start with collaborative modeling if team is unfamiliar with business strategy
- Assess IT landscape first in brownfield scenarios
- Code before finalizing architecture for MVPs or complex domains
- Blend definition and coding for rapid feedback
- Organize teams before designing contexts when org constraints exist

## Code Implementation Guidelines

When coding domain models:
- Align code structure with domain structure
- Use ubiquitous language in code (class names, methods, variables)
- Protect invariants within aggregates
- Keep bounded contexts independent
- Make implicit concepts explicit
- Favor composition over inheritance
- Use value objects for domain concepts without identity

## Common Anti-Patterns to Avoid

- Skipping domain discovery
- Technical decomposition instead of domain-driven decomposition
- Treating core, supporting, and generic domains equally
- Creating overly large bounded contexts
- Tight coupling between contexts
- Anemic domain models (data without behavior)
- Premature optimization over domain clarity

## Success Indicators

- Developers can explain business concepts
- Domain experts understand the model
- Code changes align with domain changes
- Teams can work independently
- Business opportunities are quickly identified
- System boundaries make sense to non-technical stakeholders

## References

All DDD skills are prefixed with "ddd-" for easy discovery. See the `.github/skills/` directory for detailed guidance on each process step.

## Learning Resources

- EventStorming: https://www.eventstorming.com/
- Context Mapping: https://github.com/ddd-crew/context-mapping
- Bounded Context Canvas: https://github.com/ddd-crew/bounded-context-canvas
- Core Domain Charts: https://github.com/ddd-crew/core-domain-charts
- Domain Message Flow: https://github.com/ddd-crew/domain-message-flow-modelling
- Aggregate Design Canvas: https://github.com/ddd-crew/aggregate-design-canvas
