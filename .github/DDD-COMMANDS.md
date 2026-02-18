# DDD Slash Commands for AI Coding Tools

Slash commands for quick DDD assistance when agent skills don't fit. Compatible with GitHub Copilot, Windsurf/OpenCode, and Claude/Cursor.

## Core DDD Commands

### `/ddd-help`
**Purpose:** Get overview of DDD process and available commands
**Usage:** `/ddd-help [topic]`
**Examples:**
- `/ddd-help` - Show all DDD commands
- `/ddd-help eventstorming` - Get EventStorming guidance
- `/ddd-help aggregates` - Learn about aggregates

### `/ddd-analyze`
**Purpose:** Analyze code or design for DDD patterns and anti-patterns
**Usage:** `/ddd-analyze [file|selection|description]`
**Examples:**
- `/ddd-analyze` - Analyze current file for DDD patterns
- `/ddd-analyze src/Order.java` - Check if Order is a proper aggregate
- `/ddd-analyze "Customer has orderId field"` - Identify design smell

### `/ddd-refactor`
**Purpose:** Suggest DDD refactorings for anemic or poorly designed code
**Usage:** `/ddd-refactor [target] to [pattern]`
**Examples:**
- `/ddd-refactor to rich-domain-model` - Convert anemic model
- `/ddd-refactor Order to aggregate` - Make Order a proper aggregate
- `/ddd-refactor address-fields to value-object` - Extract Address value object

## Discovery & Modeling Commands

### `/ddd-events`
**Purpose:** Identify domain events for a process or scenario
**Usage:** `/ddd-events [process-description]`
**Examples:**
- `/ddd-events order checkout process`
- `/ddd-events customer registration`
- `/ddd-events when user subscribes to premium`

### `/ddd-commands`
**Purpose:** Identify commands that trigger domain events
**Usage:** `/ddd-commands for [events]`
**Examples:**
- `/ddd-commands for OrderPlaced`
- `/ddd-commands for this process` (analyzes selection)

### `/ddd-actors`
**Purpose:** Identify actors/users in a domain
**Usage:** `/ddd-actors in [domain]`
**Examples:**
- `/ddd-actors in e-commerce`
- `/ddd-actors in healthcare patient management`

### `/ddd-language`
**Purpose:** Extract or define ubiquitous language terms
**Usage:** `/ddd-language [action] [terms]`
**Examples:**
- `/ddd-language extract` - From current file/selection
- `/ddd-language define Order` - Define term precisely
- `/ddd-language check` - Verify language consistency

## Boundary & Architecture Commands

### `/ddd-boundaries`
**Purpose:** Identify bounded context or sub-domain boundaries
**Usage:** `/ddd-boundaries in [domain-description]`
**Examples:**
- `/ddd-boundaries in e-commerce platform`
- `/ddd-boundaries for these events: [list]`
- `/ddd-boundaries check current-design` - Validate existing boundaries

### `/ddd-classify`
**Purpose:** Classify sub-domain as core/supporting/generic
**Usage:** `/ddd-classify [domain-description]`
**Examples:**
- `/ddd-classify authentication system`
- `/ddd-classify recommendation engine for streaming service`
- `/ddd-classify order management`

### `/ddd-integrate`
**Purpose:** Design integration between bounded contexts
**Usage:** `/ddd-integrate [contextA] with [contextB]`
**Examples:**
- `/ddd-integrate Orders with Payment`
- `/ddd-integrate using events` - Event-driven approach
- `/ddd-integrate sync-or-async` - Recommend pattern

### `/ddd-context-map`
**Purpose:** Create or update context map
**Usage:** `/ddd-context-map [action]`
**Examples:**
- `/ddd-context-map create for e-commerce`
- `/ddd-context-map add relationship Orders->Payment`
- `/ddd-context-map show current`

## Implementation Commands

### `/ddd-aggregate`
**Purpose:** Create or validate an aggregate
**Usage:** `/ddd-aggregate [action] [name]`
**Examples:**
- `/ddd-aggregate create Order`
- `/ddd-aggregate validate current-class`
- `/ddd-aggregate extract from Order and OrderLine`

### `/ddd-value-object`
**Purpose:** Create value object from fields or concept
**Usage:** `/ddd-value-object [name] with [fields]`
**Examples:**
- `/ddd-value-object Money with amount,currency`
- `/ddd-value-object extract address-fields`
- `/ddd-value-object EmailAddress`

### `/ddd-entity`
**Purpose:** Create entity with proper identity
**Usage:** `/ddd-entity [name]`
**Examples:**
- `/ddd-entity Customer`
- `/ddd-entity Order with OrderId`

### `/ddd-repository`
**Purpose:** Create repository interface for aggregate
**Usage:** `/ddd-repository for [aggregate]`
**Examples:**
- `/ddd-repository for Order`
- `/ddd-repository OrderRepository with methods`

### `/ddd-domain-service`
**Purpose:** Create domain service for cross-aggregate logic
**Usage:** `/ddd-domain-service [name] for [purpose]`
**Examples:**
- `/ddd-domain-service TransferMoney between accounts`
- `/ddd-domain-service PricingCalculation`

### `/ddd-event`
**Purpose:** Define domain event class
**Usage:** `/ddd-event [name]`
**Examples:**
- `/ddd-event OrderPlaced`
- `/ddd-event CustomerRegistered with fields`

## Validation & Review Commands

### `/ddd-review`
**Purpose:** Review code for DDD best practices
**Usage:** `/ddd-review [scope]`
**Examples:**
- `/ddd-review current-file`
- `/ddd-review aggregate Order`
- `/ddd-review bounded-context OrderManagement`

### `/ddd-validate`
**Purpose:** Validate domain model against business rules
**Usage:** `/ddd-validate [target]`
**Examples:**
- `/ddd-validate invariants in Order`
- `/ddd-validate business-rules`
- `/ddd-validate ubiquitous-language`

### `/ddd-test`
**Purpose:** Generate domain tests for aggregates/rules
**Usage:** `/ddd-test [target]`
**Examples:**
- `/ddd-test Order aggregate`
- `/ddd-test invariant: orders-cant-modify-after-shipping`
- `/ddd-test business-rule: order-total-calculation`

## Team & Process Commands

### `/ddd-team-structure`
**Purpose:** Recommend team organization using Team Topologies
**Usage:** `/ddd-team-structure for [contexts]`
**Examples:**
- `/ddd-team-structure for Orders, Payment, Inventory`
- `/ddd-team-structure recommend`

### `/ddd-workshop`
**Purpose:** Prepare for DDD workshops (EventStorming, etc.)
**Usage:** `/ddd-workshop [type] [domain]`
**Examples:**
- `/ddd-workshop eventstorming order-management`
- `/ddd-workshop bounded-context-canvas Payment`
- `/ddd-workshop prep` - General preparation

## Pattern & Tool Commands

### `/ddd-pattern`
**Purpose:** Apply or explain DDD pattern
**Usage:** `/ddd-pattern [name]`
**Examples:**
- `/ddd-pattern aggregate`
- `/ddd-pattern repository`
- `/ddd-pattern specification`
- `/ddd-pattern anticorruption-layer`

### `/ddd-architecture`
**Purpose:** Apply architectural pattern
**Usage:** `/ddd-architecture [pattern]`
**Examples:**
- `/ddd-architecture hexagonal`
- `/ddd-architecture onion`
- `/ddd-architecture cqrs`
- `/ddd-architecture event-sourcing`

### `/ddd-canvas`
**Purpose:** Create DDD canvases (Bounded Context, Aggregate, Core Domain)
**Usage:** `/ddd-canvas [type] for [target]`
**Examples:**
- `/ddd-canvas bounded-context for OrderManagement`
- `/ddd-canvas aggregate for Order`
- `/ddd-canvas core-domain for entire-system`

## Quick Reference Commands

### `/ddd-glossary`
**Purpose:** Show DDD terminology glossary
**Usage:** `/ddd-glossary [term]`
**Examples:**
- `/ddd-glossary` - Show all terms
- `/ddd-glossary aggregate` - Define aggregate
- `/ddd-glossary ubiquitous-language`

### `/ddd-heuristics`
**Purpose:** Apply design heuristics for decomposition
**Usage:** `/ddd-heuristics [apply|list]`
**Examples:**
- `/ddd-heuristics list` - Show all heuristics
- `/ddd-heuristics apply to this-domain`

### `/ddd-checklist`
**Purpose:** Get checklist for current DDD step
**Usage:** `/ddd-checklist [step]`
**Examples:**
- `/ddd-checklist understand`
- `/ddd-checklist eventstorming`
- `/ddd-checklist aggregate-design`

## Troubleshooting Commands

### `/ddd-debug`
**Purpose:** Debug common DDD issues
**Usage:** `/ddd-debug [issue]`
**Examples:**
- `/ddd-debug anemic-model`
- `/ddd-debug aggregate-too-large`
- `/ddd-debug unclear-boundaries`
- `/ddd-debug distributed-monolith`

### `/ddd-compare`
**Purpose:** Compare design alternatives
**Usage:** `/ddd-compare [optionA] vs [optionB]`
**Examples:**
- `/ddd-compare sync vs async integration`
- `/ddd-compare one-aggregate vs two-aggregates`
- `/ddd-compare shared-kernel vs anticorruption-layer`

## Usage Notes

### Command Aliases
Many commands have short aliases:
- `/ddd-h` → `/ddd-help`
- `/ddd-a` → `/ddd-analyze`
- `/ddd-r` → `/ddd-refactor`
- `/ddd-v` → `/ddd-validate`

### Chaining Commands
Some tools support chaining:
```
/ddd-events order-checkout | /ddd-commands | /ddd-aggregate create Order
```

### Context-Aware Commands
Commands use current context (file, selection, or project):
```
// With file open: Order.java
/ddd-analyze          // Analyzes Order.java
/ddd-review           // Reviews Order.java

// With text selected
/ddd-events           // Finds events in selection
/ddd-value-object extract  // Extracts value object from selection
```

### Tool-Specific Syntax

**GitHub Copilot Chat:**
```
@workspace /ddd-events order checkout
```

**Windsurf/OpenCode:**
```
/ddd-events order checkout
```

**Claude/Cursor:**
```
/ddd-events order checkout
```

## Creating Custom Commands

Add to your tool's configuration file:

**For Cursor (.cursorrules):**
```markdown
## Custom DDD Commands

### /my-ddd-command
Description of what it does
```

**For Windsurf (.windsurfrules):**
```yaml
commands:
  - name: my-ddd-command
    description: What it does
    prompt: Detailed instructions
```

## Examples in Practice

### New Feature: Add Subscription Management

```bash
# 1. Discover domain
/ddd-events subscription lifecycle

# 2. Identify boundaries
/ddd-boundaries in subscription-domain

# 3. Classify strategic importance
/ddd-classify subscription-management

# 4. Design aggregate
/ddd-aggregate create Subscription

# 5. Validate design
/ddd-review aggregate Subscription

# 6. Generate tests
/ddd-test Subscription aggregate
```

### Refactor Legacy Code

```bash
# 1. Analyze current code
/ddd-analyze src/legacy/OrderManager.java

# 2. Identify smells
/ddd-debug anemic-model

# 3. Refactor to rich model
/ddd-refactor OrderManager to aggregate

# 4. Extract value objects
/ddd-value-object extract address-fields

# 5. Validate refactoring
/ddd-validate invariants in Order
```

### Prepare for Workshop

```bash
# EventStorming prep
/ddd-workshop eventstorming order-management

# Get facilitation tips
/ddd-help eventstorming-facilitation

# Create agenda
/ddd-checklist eventstorming-session
```

## See Also

- DDD Agents (`.github/agents/ddd-*.json`) - For longer interactions
- Reference Guide (`.github/ddd-reference.md`) - For tool catalog
- Copilot Prompts (`.github/copilot-prompts.md`) - For detailed prompts
