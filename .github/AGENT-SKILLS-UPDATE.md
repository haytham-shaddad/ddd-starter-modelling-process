# AI Agent Skills & Commands - Updated Structure

## What Changed

Transformed DDD knowledge into actual **Agent Skills** (JSON format) and **Slash Commands** per user feedback.

### Before (markdown guides)
- `.github/skills/ddd-*.md` - Long-form documentation
- `.github/copilot-prompts.md` - Prompt examples

### After (agent skills + commands)
- `.github/agents/ddd-*.json` - **Agent skill files** (8 files)
- `.github/DDD-COMMANDS.md` - **Slash commands** (40+ commands)
- `.cursorrules` - Cursor/Claude configuration
- `.windsurfrules` - Windsurf/OpenCode configuration

## New Structure

```
.github/
├── agents/                       # Agent skill files (JSON)
│   ├── README.md                # Agent catalog & usage guide
│   ├── ddd-understand.json      # Business alignment agent
│   ├── ddd-discover.json        # EventStorming agent
│   ├── ddd-decompose.json       # Boundary identification agent
│   ├── ddd-strategize.json      # Core domain assessment agent
│   ├── ddd-connect.json         # Integration patterns agent
│   ├── ddd-organise.json        # Team Topologies agent
│   ├── ddd-define.json          # Bounded Context Canvas agent
│   └── ddd-code.json            # Implementation agent
├── DDD-COMMANDS.md              # Slash commands reference
├── ddd-reference.md             # Tools & patterns catalog (kept)
├── copilot-instructions.md      # Auto-loaded instructions (kept)
└── README.md                    # Main navigation (kept)

.cursorrules                      # Cursor/Claude config (NEW)
.windsurfrules                    # Windsurf/OpenCode config (NEW)
.vscode/settings.json            # VS Code config (kept)
```

## Agent Skills (JSON Format)

Each agent is a standalone JSON file with:

```json
{
  "name": "ddd-discover",
  "description": "DDD Agent: Facilitate domain discovery using EventStorming",
  "version": "1.0.0",
  "instructions": "Detailed agent instructions...",
  "examples": [
    {
      "prompt": "User question",
      "response": "Agent's helpful response"
    }
  ],
  "capabilities": ["eventstorming", "domain_storytelling", ...],
  "dependencies": ["ddd-understand"],
  "tags": ["ddd", "discovery", "eventstorming"]
}
```

### Why JSON Format?

- **Portable** - Copy to any project
- **Tool-compatible** - Works with Copilot, Windsurf, Claude
- **Structured** - AI tools can parse and use effectively
- **Extensible** - Easy to customize and extend

## Slash Commands

Quick DDD assistance without full agent interaction.

**File:** `.github/DDD-COMMANDS.md`

### Examples:

```bash
/ddd-help                        # Show all commands
/ddd-events order-checkout       # Identify domain events
/ddd-aggregate create Order      # Generate aggregate
/ddd-analyze                     # Check code for DDD patterns
/ddd-refactor to rich-domain-model  # Fix anemic model
/ddd-boundaries in e-commerce    # Find context boundaries
/ddd-validate invariants         # Verify business rules
```

### Command Categories:

1. **Discovery** - `/ddd-events`, `/ddd-commands`, `/ddd-actors`, `/ddd-language`
2. **Boundaries** - `/ddd-boundaries`, `/ddd-classify`, `/ddd-integrate`
3. **Implementation** - `/ddd-aggregate`, `/ddd-value-object`, `/ddd-event`
4. **Validation** - `/ddd-review`, `/ddd-validate`, `/ddd-test`
5. **Team** - `/ddd-team-structure`, `/ddd-workshop`
6. **Patterns** - `/ddd-pattern`, `/ddd-architecture`, `/ddd-canvas`

## Tool Compatibility

### GitHub Copilot

Agents auto-loaded from `.github/agents/`.

**Usage:**
```
@workspace use ddd-discover agent to help me with EventStorming
```

### Windsurf/OpenCode (Codeium)

Config file: `.windsurfrules`

**Usage:**
```
Use ddd-code: Implement Order aggregate with invariant protection
/ddd-aggregate create Order
```

### Claude/Cursor

Config file: `.cursorrules`

**Usage:**
```
@ddd-discover help me identify domain events
/ddd-events order management
```

## Migration Guide

### From Old Structure

The old markdown skills (`.github/skills/ddd-*.md`) are **replaced** by:
- Agent files: `.github/agents/ddd-*.json` (for interactive guidance)
- Slash commands: `.github/DDD-COMMANDS.md` (for quick actions)

### Kept Files

These files remain useful:
- `.github/copilot-instructions.md` - Auto-loaded by Copilot
- `.github/ddd-reference.md` - Comprehensive tool/pattern catalog
- `.vscode/settings.json` - VS Code configuration

### What to Use When

**Use Agents** (JSON files) when:
- Starting new DDD step (EventStorming, Context Mapping, etc.)
- Need detailed guidance and examples
- Want interactive back-and-forth
- Learning DDD concepts

**Use Slash Commands** when:
- Quick code generation (`/ddd-aggregate`)
- Fast analysis (`/ddd-analyze`)
- Refactoring (`/ddd-refactor`)
- Validation (`/ddd-validate`)

## Usage Examples

### Example 1: Greenfield Project

```bash
# 1. Understand business (agent)
@workspace use ddd-understand: Create Business Model Canvas for meal delivery

# 2. Discover domain (agent)
@workspace use ddd-discover: Prepare EventStorming for order flow

# 3. Quick event identification (command)
/ddd-events meal ordering process

# 4. Find boundaries (command)
/ddd-boundaries in meal delivery domain

# 5. Classify domains (command)
/ddd-classify meal preparation domain

# 6. Implement (agent)
@workspace use ddd-code: Implement Order aggregate
```

### Example 2: Refactoring

```bash
# 1. Analyze current code (command)
/ddd-analyze src/Order.java

# 2. Get agent help (agent)
@workspace use ddd-code: This Order class is anemic, help me refactor

# 3. Apply refactoring (command)
/ddd-refactor Order to rich-domain-model

# 4. Extract value objects (command)
/ddd-value-object extract address-fields

# 5. Validate (command)
/ddd-validate invariants in Order
```

## Benefits

### For Users
✅ Portable - Copy agents to any project  
✅ Tool-agnostic - Works in Copilot, Windsurf, Claude  
✅ Quick commands - Slash commands for speed  
✅ Deep guidance - Agents for learning  

### For AI Tools
✅ Structured format - JSON is parseable  
✅ Clear capabilities - Know what agent does  
✅ Example-driven - Learn from examples  
✅ Modular - Load only what's needed  

## Next Steps

1. **Copy agents** to your project: `cp -r .github/agents your-project/.github/`
2. **Copy config** for your tool: `.cursorrules` or `.windsurfrules`
3. **Try commands**: `/ddd-help` to see all available
4. **Use agents**: Reference by name in your AI tool

## Files Summary

| File | Type | Purpose |
|------|------|---------|
| `.github/agents/*.json` | Agent Skills | Interactive DDD guidance |
| `.github/DDD-COMMANDS.md` | Commands | Quick slash command reference |
| `.cursorrules` | Config | Cursor/Claude integration |
| `.windsurfrules` | Config | Windsurf/OpenCode integration |
| `.github/ddd-reference.md` | Reference | Tools & patterns catalog |
| `.github/copilot-instructions.md` | Instructions | Auto-loaded Copilot context |

## License

Creative Commons Attribution 4.0 International License
