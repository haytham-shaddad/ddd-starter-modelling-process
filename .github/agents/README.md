# DDD Agent Skills Catalog

This directory contains DDD agent skills in standard JSON format, compatible with GitHub Copilot, Windsurf/OpenCode (Codeium), and Claude/Cursor.

## Available Agent Skills

### 1. ddd-understand
**File:** `ddd-understand.json`  
**Focus:** Business model alignment and strategic planning  
**Use When:** Starting projects, connecting tech to business goals  
**Key Capabilities:**
- Business Model Canvas facilitation
- Impact Mapping
- User Story Mapping  
- Strategic goal clarification

### 2. ddd-discover
**File:** `ddd-discover.json`  
**Focus:** Collaborative domain discovery and EventStorming  
**Use When:** Learning the domain, building shared understanding  
**Key Capabilities:**
- EventStorming facilitation (Big Picture, Process, Design)
- Domain Storytelling
- Ubiquitous language extraction
- Hot spot identification

### 3. ddd-decompose
**File:** `ddd-decompose.json`  
**Focus:** Domain decomposition into sub-domains  
**Use When:** Breaking large domains into manageable parts  
**Key Capabilities:**
- Sub-domain boundary identification
- Design heuristics application
- Context mapping
- Coupling analysis

### 4. ddd-strategize
**File:** `ddd-strategize.json`  
**Focus:** Core domain identification and investment planning  
**Use When:** Prioritizing work, making build/buy decisions  
**Key Capabilities:**
- Core Domain Chart creation
- Strategic domain classification
- Build vs buy analysis
- Investment planning

### 5. ddd-connect
**File:** `ddd-connect.json`  
**Focus:** Integration patterns and message flows  
**Use When:** Designing how contexts communicate  
**Key Capabilities:**
- Domain Message Flow modeling
- Integration pattern selection
- Context map relationship definition
- Use case validation

### 6. ddd-organise
**File:** `ddd-organise.json`  
**Focus:** Team structure using Team Topologies  
**Use When:** Organizing teams, managing cognitive load  
**Key Capabilities:**
- Team Topologies pattern application
- Team interaction mode design
- Cognitive load assessment
- Inverse Conway Maneuver

### 7. ddd-define
**File:** `ddd-define.json`  
**Focus:** Bounded context detailed design  
**Use When:** Before coding, defining context responsibilities  
**Key Capabilities:**
- Bounded Context Canvas facilitation
- Ubiquitous language documentation
- Interface design (inbound/outbound)
- Business rule capture

### 8. ddd-code
**File:** `ddd-code.json`  
**Focus:** Tactical DDD implementation  
**Use When:** Writing domain model code  
**Key Capabilities:**
- Aggregate design and implementation
- Value object creation
- Domain event definition
- Repository pattern
- Rich domain model creation

## Agent Dependencies

```
ddd-understand (standalone)
ddd-discover (standalone)
ddd-decompose → depends on: ddd-discover
ddd-strategize → depends on: ddd-decompose
ddd-connect → depends on: ddd-decompose
ddd-organise → depends on: ddd-decompose, ddd-connect
ddd-define → depends on: ddd-decompose, ddd-strategize
ddd-code → depends on: ddd-define
```

## Using with Different AI Tools

### GitHub Copilot

Agents should be auto-discovered from `.github/agents/` directory.

**Usage in Copilot Chat:**
```
@workspace use ddd-discover agent to help me prepare for an EventStorming session
```

### Windsurf/OpenCode (Codeium)

Copy agent files to your project and reference in `.windsurfrules` or cascade config:

```yaml
agents:
  - path: .github/agents/ddd-discover.json
    enabled: true
  - path: .github/agents/ddd-code.json
    enabled: true
```

**Usage:**
```
Use ddd-discover: Help me identify domain events for order management
```

### Claude/Cursor

Copy agents to `.cursor/agents/` or reference in `.cursorrules`:

```markdown
# DDD Agents

Available agents in .github/agents/:
- ddd-understand: Business alignment
- ddd-discover: Domain discovery
- ddd-code: Implementation
...
```

**Usage:**
```
@ddd-code implement Order aggregate
```

## Agent File Format

Each agent file follows this JSON schema:

```json
{
  "name": "agent-name",
  "description": "One-line description",
  "version": "1.0.0",
  "instructions": "Detailed instructions...",
  "examples": [
    {
      "prompt": "User question",
      "response": "Agent response"
    }
  ],
  "capabilities": ["list", "of", "capabilities"],
  "dependencies": ["other-agent-names"],
  "tags": ["searchable", "tags"]
}
```

## Slash Commands

For quick DDD assistance without full agent interaction, see:
**[DDD-COMMANDS.md](../DDD-COMMANDS.md)** - 40+ slash commands

Examples:
- `/ddd-events` - Identify domain events
- `/ddd-aggregate create Order` - Generate aggregate
- `/ddd-analyze` - Check code for DDD patterns
- `/ddd-refactor to rich-domain-model` - Convert anemic model

## Workflow Example

### Greenfield Project

1. **Understand** (`ddd-understand`)
   - Create Business Model Canvas
   - Map user journeys
   - Define strategic goals

2. **Discover** (`ddd-discover`)
   - Run EventStorming sessions
   - Build ubiquitous language
   - Identify processes and events

3. **Decompose** (`ddd-decompose`)
   - Find sub-domain boundaries
   - Create context maps
   - Apply design heuristics

4. **Strategize** (`ddd-strategize`)
   - Create Core Domain Chart
   - Classify domains
   - Plan investment

5. **Connect** (`ddd-connect`)
   - Design message flows
   - Choose integration patterns
   - Validate with use cases

6. **Organise** (`ddd-organise`)
   - Design team structure
   - Apply Team Topologies
   - Define interactions

7. **Define** (`ddd-define`)
   - Complete Bounded Context Canvas
   - Document ubiquitous language
   - Design interfaces

8. **Code** (`ddd-code`)
   - Implement aggregates
   - Create value objects
   - Code domain events

### Refactoring Legacy Code

1. **Discover** (`ddd-discover`)
   - Understand current domain
   - Extract implicit language

2. **Analyze** (use `/ddd-analyze`)
   - Identify anti-patterns
   - Find boundaries

3. **Decompose** (`ddd-decompose`)
   - Break monolith
   - Define contexts

4. **Code** (`ddd-code`)
   - Refactor to rich models
   - Extract aggregates
   - Protect invariants

## Best Practices

### Agent Selection
- Use **one agent at a time** for focused guidance
- Follow **dependency order** when learning
- Combine **agents + slash commands** for efficiency

### Effective Prompts
- Be specific about your domain
- Provide context (industry, constraints)
- Share concrete examples
- Ask follow-up questions

### Examples

**Good:**
```
@ddd-code: Implement Order aggregate for e-commerce.
Business rules:
- Orders can't be modified after shipping
- Max 100 line items
- Total must be positive
```

**Better:**
```
@ddd-code: Implement Order aggregate for B2B e-commerce platform.
Context: Manufacturing supplies, bulk orders, net-30 payment terms.
Rules:
- Orders locked after shipment starts
- Min order $500
- Volume discounts apply
- Credit limit enforcement
Current issue: Anemic Order class with setters everywhere
```

## Installation

### Option 1: Use In-Place
Keep agents in `.github/agents/` and reference directly.

### Option 2: Copy to Tool-Specific Location

**For Cursor:**
```bash
mkdir -p .cursor/agents
cp .github/agents/*.json .cursor/agents/
```

**For Windsurf:**
```bash
mkdir -p .cascade/agents
cp .github/agents/*.json .cascade/agents/
```

### Option 3: Symlink
```bash
ln -s .github/agents .cursor/agents
```

## Customization

Agents are templates. Customize for your domain:

1. **Add Domain Examples:** Include your specific domain in `examples`
2. **Extend Instructions:** Add domain-specific guidance
3. **Modify Capabilities:** Tailor to your tech stack
4. **Create New Agents:** Follow the JSON schema

## Support

- **Issues:** Open issue in parent repository
- **Questions:** Use GitHub Discussions
- **Contributions:** PRs welcome for improvements

## License

Creative Commons Attribution 4.0 International License

## See Also

- **[DDD-COMMANDS.md](../DDD-COMMANDS.md)** - Slash commands reference
- **[ddd-reference.md](../ddd-reference.md)** - Tools and patterns catalog
- **[README.md](../README.md)** - Main documentation
- **Parent Repository:** [DDD Starter Modelling Process](../../README.md)
