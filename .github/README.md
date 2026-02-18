# AI Skills and Knowledge Extraction Index

This directory contains extracted knowledge from the DDD Starter Modelling Process repository, formatted specifically for AI agents, GitHub Copilot CLI, and VS Code GitHub Copilot.

## 📁 Directory Structure

```
.github/
├── copilot-instructions.md    # Main Copilot instructions (auto-loaded by Copilot)
├── copilot-prompts.md          # Curated prompt library for Copilot CLI
├── ddd-reference.md            # Quick reference guide for tools and patterns
├── skills/                     # Individual DDD skill guides (8 process steps)
│   ├── README.md
│   ├── ddd-understand.md
│   ├── ddd-discover.md
│   ├── ddd-decompose.md
│   ├── ddd-strategize.md
│   ├── ddd-connect.md
│   ├── ddd-organise.md
│   ├── ddd-define.md
│   └── ddd-code.md
└── README.md                   # This file

.vscode/
└── settings.json               # VS Code workspace settings with DDD configuration
```

## 🎯 Purpose

This knowledge extraction transforms the DDD Starter Modelling Process documentation into AI-consumable formats that:

1. **Guide AI Agents**: Structured guidance for AI coding assistants
2. **Enable GitHub Copilot**: Context-aware code and content suggestions
3. **Provide Quick Reference**: Fast access to tools, patterns, and techniques
4. **Support Learning**: Progressive skill building through 8 DDD steps
5. **Optimize Prompts**: Pre-built prompts for common DDD tasks

## 🚀 Quick Start

### For GitHub Copilot Users (VS Code)

1. Open this repository in VS Code
2. Install GitHub Copilot and GitHub Copilot Chat extensions
3. Copilot automatically loads `.github/copilot-instructions.md`
4. Reference skills in chat:
   ```
   @workspace Using ddd-discover, help me run an EventStorming session
   ```

### For GitHub Copilot CLI Users

1. Reference skills in CLI prompts:
   ```bash
   gh copilot suggest "using ddd-code, implement an aggregate for Order"
   ```

2. Use prepared prompts from `copilot-prompts.md`:
   ```bash
   gh copilot suggest "Create a Core Domain Chart for e-commerce platform"
   ```

### For AI Agents

1. Read `copilot-instructions.md` for overall DDD context
2. Reference specific skill files for step-by-step guidance
3. Use `ddd-reference.md` for tools and patterns lookup
4. Apply prompts from `copilot-prompts.md` for specific tasks

## 📚 Content Overview

### Main Files

#### `copilot-instructions.md`
- **Auto-loaded by GitHub Copilot**
- Overall DDD principles and guidelines
- 8-step process overview
- Core concepts and patterns
- Anti-patterns to avoid
- Success indicators

#### `copilot-prompts.md`
- 100+ curated prompts for Copilot CLI
- Organized by DDD process step
- Domain-specific examples
- Workshop facilitation prompts
- Troubleshooting prompts

#### `ddd-reference.md`
- Comprehensive tool catalog
- Pattern and technique reference
- Integration patterns
- Team topologies
- Architecture patterns
- Quick lookup guide

### Skills Directory

Eight skill files, one per DDD process step, each containing:

- **Purpose**: Clear objective
- **Key Activities**: What to do
- **Recommended Tools**: Which tools to use
- **Who to Involve**: Required participants
- **Success Criteria**: Definition of done
- **Common Pitfalls**: What to avoid
- **AI Agent Prompts**: Ready-to-use AI prompts
- **Examples**: Concrete outputs

## 🎓 The 8 DDD Skills

| # | Skill | Focus | Key Tools |
|---|-------|-------|-----------|
| 1 | `ddd-understand` | Business alignment | Business Model Canvas, Impact Mapping |
| 2 | `ddd-discover` | Domain exploration | EventStorming, Domain Storytelling |
| 3 | `ddd-decompose` | Sub-domain boundaries | Context Maps, Design Heuristics |
| 4 | `ddd-strategize` | Core domain identification | Core Domain Charts, Wardley Mapping |
| 5 | `ddd-connect` | Architecture integration | Domain Message Flow, BPMN |
| 6 | `ddd-organise` | Team structure | Team Topologies, Context Maps |
| 7 | `ddd-define` | Context definition | Bounded Context Canvas, C4 |
| 8 | `ddd-code` | Implementation | Aggregate Design Canvas, Hexagonal Architecture |

## 🔍 Finding What You Need

### By Activity

- **Starting a project**: `ddd-understand` → `ddd-discover`
- **Finding boundaries**: `ddd-decompose`
- **Prioritizing work**: `ddd-strategize`
- **Designing integration**: `ddd-connect`
- **Organizing teams**: `ddd-organise`
- **Detailed design**: `ddd-define`
- **Writing code**: `ddd-code`

### By Tool

Check `ddd-reference.md` for:
- Visual Collaboration Tools (EventStorming, Domain Storytelling)
- Strategic Tools (Core Domain Charts, Wardley Mapping)
- Tactical Tools (Bounded Context Canvas, Aggregate Design Canvas)
- Organizational Tools (Team Topologies)

### By Question

Common questions mapped to skills:
- "How do I start with DDD?" → `ddd-understand`, `ddd-discover`
- "How do I find bounded contexts?" → `ddd-decompose`
- "What should I build vs buy?" → `ddd-strategize`
- "How should teams communicate?" → `ddd-connect`, `ddd-organise`
- "How do I implement aggregates?" → `ddd-code`

## 💡 Usage Examples

### Example 1: Starting a New Project

```
# In VS Code Copilot Chat
@workspace I'm starting a new e-commerce project. Guide me through ddd-understand and ddd-discover.

# In Copilot CLI
gh copilot suggest "using ddd-understand, create a business model canvas for an e-commerce platform"
```

### Example 2: Finding Boundaries

```
# In VS Code Copilot Chat
@workspace Using ddd-decompose, help me identify sub-domains from these events: OrderPlaced, PaymentProcessed, ItemShipped

# In Copilot CLI
gh copilot suggest "apply DDD heuristics to decompose an order management system"
```

### Example 3: Implementing Code

```
# In VS Code Copilot Chat
@workspace Using ddd-code, implement an Order aggregate that enforces: orders cannot be modified after shipping

# In Copilot CLI
gh copilot suggest "implement a value object for Money with currency and amount"
```

## 🎯 Optimization for AI

All content is optimized for AI consumption:

- **Structured Format**: Consistent sections across all skills
- **Explicit Context**: Clear purpose and scope for each skill
- **Actionable Guidance**: Concrete activities and outputs
- **Ready-to-Use Prompts**: Pre-formulated prompts for common tasks
- **Cross-References**: Links between related concepts
- **Examples**: Real-world illustrations
- **Success Criteria**: Clear completion definitions

## 📖 Learning Path

For those new to DDD:

1. **Start**: Read `copilot-instructions.md` for overview
2. **Understand**: Work through `ddd-understand` and `ddd-discover` (most critical!)
3. **Practice**: Use prompts from `copilot-prompts.md` with sample domains
4. **Reference**: Keep `ddd-reference.md` handy for tool lookup
5. **Iterate**: Progress through all 8 skills, revisiting as needed

## 🔄 Iteration and Feedback

DDD is iterative - you'll frequently revisit steps:

- Discovery is continuous
- Boundaries evolve with understanding
- Strategy shifts with market changes
- Architecture adapts to new insights
- Team structure evolves over time
- Code refactors as model improves

## 🌟 Key Principles for AI Agents

When using these skills, AI agents should:

1. **Prioritize Discovery**: Never skip domain exploration
2. **Collaborate**: Involve domain experts and stakeholders
3. **Iterate**: Expect to revisit and refine
4. **Business-First**: Technical decisions support business goals
5. **Reduce Coupling**: Design for independence
6. **Use Domain Language**: Code reflects business concepts
7. **Protect Invariants**: Maintain consistency boundaries
8. **Evolve Continuously**: Embrace change as understanding grows

## 📝 License

Content derived from the DDD Starter Modelling Process, licensed under [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

All skills are prefixed with `ddd-` as requested.

## 🔗 Additional Resources

- **Main README**: [../../README.md](../../README.md)
- **DDD Crew**: https://github.com/ddd-crew
- **EventStorming**: https://www.eventstorming.com/
- **Visual Collaboration Tools**: https://leanpub.com/visualcollaborationtools
- **Team Topologies**: https://teamtopologies.com/

## 🤝 Contributing

Improvements welcome! When contributing:
- Keep AI optimization in focus
- Maintain consistent structure
- Provide concrete examples
- Include actionable guidance
- Test with actual AI agents
- Follow author's style (clear, concise, practical)
