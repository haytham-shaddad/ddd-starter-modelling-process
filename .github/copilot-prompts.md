# GitHub Copilot CLI Prompts for DDD

This file contains curated prompts optimized for use with GitHub Copilot CLI and GitHub Copilot Chat when working with Domain-Driven Design concepts.

## General DDD Prompts

### Understanding DDD Process
```
Explain the 8 steps of the DDD Starter Modelling Process and when I should use each step
```

```
What is the difference between core, supporting, and generic domains? Give examples for [domain]
```

```
How do I know if I should use DDD for [project description]?
```

### Getting Started
```
I'm starting a new project in [domain]. Walk me through the first 3 steps of the DDD process
```

```
Create a checklist for applying DDD to [project type]
```

## Step-Specific Prompts

### ddd-understand Prompts
```
Help me create a Business Model Canvas for [domain/business]
```

```
What strategic questions should I ask stakeholders about [business area]?
```

```
Generate Impact Mapping questions to connect [feature] to [business goal]
```

```
Create a user story map outline for [user journey/domain]
```

```
What user research questions would reveal needs for [domain]?
```

### ddd-discover Prompts
```
What domain events would occur in [business process]?
```

```
Help me prepare for an EventStorming session about [domain]. What questions should I ask?
```

```
Identify potential aggregates from these domain events: [list of events]
```

```
What are typical actors in a [domain type] domain? (e.g., e-commerce, healthcare)
```

```
Create a domain storytelling scenario for [use case]
```

```
What business rules should I explore for [process/scenario]?
```

```
Identify hot spots (conflicts/questions) in this domain description: [description]
```

```
Generate a ubiquitous language glossary starter for [domain]
```

### ddd-decompose Prompts
```
What sub-domains might exist in [domain]?
```

```
How should I decompose [business area] based on these events: [event list]?
```

```
Apply DDD heuristics to identify boundaries in this domain: [description]
```

```
What business capabilities support [business function]?
```

```
Identify different models of [concept] that might exist in [domain]
```

```
Evaluate the coupling between [sub-domain A] and [sub-domain B]
```

```
Is [sub-domain description] core, supporting, or generic?
```

```
Find pivotal events that indicate sub-domain boundaries in: [process]
```

### ddd-strategize Prompts
```
Create a Core Domain Chart for [business/domain]
```

```
Evaluate whether [sub-domain] should be built, bought, or outsourced
```

```
What makes [sub-domain] strategically important for [business]?
```

```
Assess the complexity vs. differentiation of these domains: [list]
```

```
How should we prioritize investment across these domains: [domain list]?
```

```
Generate strategic questions to assess business differentiation for [domain]
```

```
Where should we invest our best engineering talent in [domain landscape]?
```

### ddd-connect Prompts
```
Create a domain message flow for [use case] across these contexts: [context list]
```

```
What integration pattern should I use for [scenario]?
```

```
Design an event flow for [business process]
```

```
Should this integration be synchronous or asynchronous: [description]?
```

```
What failure scenarios should I plan for in [integration]?
```

```
Create a sequence diagram for [use case] spanning [contexts]
```

```
How should [context A] and [context B] communicate to support [requirement]?
```

```
Design message contracts for [integration scenario]
```

### ddd-organise Prompts
```
How should we organize teams around these contexts: [context list]?
```

```
What Team Topologies patterns fit our [organization description]?
```

```
Assess the cognitive load for a team owning these contexts: [list]
```

```
Should we have one team or multiple teams for [context description]?
```

```
Design team interactions for [architectural scenario]
```

```
What enabling teams would help [organization]?
```

```
Apply the Inverse Conway Maneuver for this desired architecture: [description]
```

```
Identify team dependencies in this setup: [team structure description]
```

### ddd-define Prompts
```
Create a Bounded Context Canvas for [domain area]
```

```
What ubiquitous language terms are needed for [context]?
```

```
Identify aggregates in this context: [context description]
```

```
What domain events occur in [business process within context]?
```

```
Design the inbound API for [context]
```

```
What quality attributes matter most for [context]?
```

```
List the business rules that [context] must enforce
```

```
Identify value objects needed in [context]
```

```
Define the boundaries of [aggregate] in [context]
```

### ddd-code Prompts
```
Implement an aggregate for [domain concept] with these invariants: [rule list]
```

```
Create value objects for [domain concepts]
```

```
Design domain events for [business process]
```

```
Implement a repository interface for [aggregate]
```

```
Write a domain service for [operation]
```

```
How should I structure the code for [bounded context]?
```

```
Create unit tests for this aggregate invariant: [rule]
```

```
Refactor this anemic domain model to a rich domain model: [code snippet]
```

```
Implement the [pattern] pattern for [use case]
```

```
Generate an aggregate with: commands [list], events [list], invariants [list]
```

## Cross-Cutting Prompts

### Architecture and Design
```
Compare hexagonal vs onion architecture for [context/project]
```

```
Should I use CQRS for [scenario]?
```

```
Design an anticorruption layer for integrating with [legacy system]
```

```
When should I use event sourcing for [domain]?
```

### Validation and Review
```
Review this domain model for DDD best practices: [description/code]
```

```
What DDD anti-patterns exist in this design: [description]?
```

```
Validate that these aggregates have proper boundaries: [list]
```

```
Check if this bounded context definition is complete: [canvas content]
```

### Learning and Explanation
```
Explain [DDD concept] with an example from [industry/domain]
```

```
What's the difference between [concept A] and [concept B] in DDD?
```

```
Give me examples of [pattern] from [domain type]
```

```
What are common mistakes when implementing [DDD concept]?
```

### Refactoring and Improvement
```
How can I improve the boundaries in this design: [description]?
```

```
Refactor these anemic services into a rich domain model: [code]
```

```
How should I split this god aggregate: [description]?
```

```
Improve this ubiquitous language: [current terms]
```

## Workshop Facilitation Prompts

```
Create an agenda for a [duration]-hour EventStorming session for [domain]
```

```
Generate icebreaker questions for a domain discovery workshop
```

```
What supplies do I need for an in-person [workshop type] session?
```

```
Create a remote EventStorming template for [tool] (Miro/Mural)
```

## Context-Specific Prompts

### E-commerce Domain
```
What are typical bounded contexts in an e-commerce platform?
```

```
Model the order aggregate for e-commerce with these rules: [rules]
```

### Healthcare Domain
```
Identify sub-domains in a healthcare patient management system
```

```
What privacy and compliance concerns affect DDD modeling in healthcare?
```

### Financial Services
```
Design aggregates for a banking domain with these transactions: [list]
```

```
What domain events are critical in a payment processing system?
```

## Troubleshooting Prompts

```
I'm struggling to find bounded context boundaries in [domain]. Help me identify them.
```

```
My aggregates are getting too large. How should I split them in [context]?
```

```
Teams keep blocking each other. How should I adjust these boundaries: [description]?
```

```
How do I handle this cross-cutting concern in DDD: [concern]?
```

```
I have conflicting models of [concept]. Should this be separate contexts?
```

## Meta Prompts (About Using These Prompts)

```
Suggest the best DDD prompts for [my current situation]
```

```
What DDD process step should I focus on for [problem]?
```

```
Create a custom prompt for [specific need] using DDD principles
```

## Usage Tips

1. **Be Specific**: Replace placeholders like [domain], [context], [business area] with your actual domain
2. **Provide Context**: Include relevant details from your domain for better responses
3. **Iterate**: Use follow-up prompts to refine and deep-dive
4. **Combine Steps**: You can ask about multiple steps together (e.g., "discover and decompose")
5. **Ask for Examples**: Request examples from similar domains for better understanding
6. **Request Validation**: Ask Copilot to validate your designs against DDD principles

## Example Usage

Instead of:
```
What are aggregates?
```

Use:
```
Identify aggregates in an order management context that handles customer orders, 
order lines, and shipping. Orders can be modified until shipped.
```

Instead of:
```
Help with EventStorming
```

Use:
```
Help me prepare for an EventStorming session about a meal delivery service. 
What domain events should I expect? What questions should I ask restaurant partners?
```
