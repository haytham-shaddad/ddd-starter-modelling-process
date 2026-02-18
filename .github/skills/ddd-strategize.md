# ddd-strategize: Identify and Prioritize Core Domains

## Purpose
Strategically assess sub-domains to identify core domains - the parts offering greatest potential for business differentiation and strategic significance.

## Why It Matters
- **Limited Resources**: Time, money, and talent are finite
- **Optimal Impact**: Focus investment where it matters most
- **Quality Decisions**: Determine appropriate quality level for each part
- **Build vs Buy**: Make educated sourcing decisions
- **Competitive Advantage**: Invest in differentiation, not commodities
- **Strategic Alignment**: Ensure technical work supports business strategy

## Key Activities

### Assess Strategic Value
- Identify competitive differentiators
- Evaluate business criticality
- Understand revenue impact
- Assess market positioning
- Determine strategic importance

### Evaluate Complexity
- Assess domain complexity (business rules, edge cases)
- Evaluate technical complexity
- Identify expertise requirements
- Understand changeability needs

### Make Investment Decisions
- Prioritize development effort
- Determine quality standards
- Decide build, buy, or outsource
- Allocate best talent
- Set innovation budgets

### Create Strategic Portfolio
- Map all sub-domains by value and complexity
- Visualize strategic landscape
- Communicate priorities to stakeholders
- Align team understanding

## Sub-domain Classification

### Core Domain
- **Definition**: High business value, competitive differentiator
- **Characteristics**: 
  - Unique to your business
  - Provides competitive advantage
  - Complex business logic
  - Frequently changing
  - Strategic importance
- **Investment**: High quality, best developers, custom-built
- **Examples**: 
  - Google's search algorithm
  - Netflix's recommendation engine
  - Amazon's logistics optimization
  - Spotify's music discovery

### Supporting Domain
- **Definition**: Necessary but not differentiating
- **Characteristics**:
  - Supports core domain
  - Business-specific but not unique
  - Moderate complexity
  - Less frequent changes
  - Enables core capabilities
- **Investment**: Adequate quality, competent team, custom or adapted
- **Examples**:
  - Order management system
  - Customer support ticketing
  - Internal reporting tools
  - Warehouse management

### Generic Domain
- **Definition**: Solved problems, common across industries
- **Characteristics**:
  - Commodity functionality
  - No business differentiation
  - Well-understood solutions
  - Stable requirements
  - Available off-the-shelf
- **Investment**: Minimal, buy or use open source
- **Examples**:
  - Authentication and authorization
  - Payment processing
  - Email delivery
  - File storage
  - Monitoring and logging

## Recommended Tools

### Core Domain Charts
- **Purpose**: Visualize strategic value vs. complexity
- **When**: After sub-domain decomposition
- **Format**: Quadrant chart plotting domains
- **Axes**: Business differentiation (value) vs. Model complexity
- **Output**: Strategic portfolio view
- **Link**: https://github.com/ddd-crew/core-domain-charts

### Purpose Alignment Model
- **Purpose**: Assess strategic alignment of components
- **When**: Evaluating existing systems
- **Output**: Classification of components by purpose
- **Link**: https://web.archive.org/web/20241202160527/https://www.informit.com/articles/article.aspx?p=1384195&seqNum=2

### Wardley Mapping
- **Purpose**: Understand evolution and strategic positioning
- **When**: Strategic planning, ecosystem analysis
- **Format**: Map showing components and evolution
- **Output**: Strategic landscape with evolution paths
- **Link**: https://learnwardleymapping.com/

## Who to Involve
- **Critical**: Product and business strategy experts
- Software designers, builders, testers
- Domain knowledge holders
- Senior leadership (for strategic context)

## Key Questions to Answer
1. Which sub-domains differentiate us from competitors?
2. Where do we have unique business capabilities?
3. What drives revenue or reduces costs most?
4. Where is the business logic most complex?
5. What changes most frequently?
6. Where should we invest our best talent?
7. What can we buy instead of build?
8. What must be custom vs. can be generic?
9. Where do we need highest quality?
10. What provides strategic advantage?

## Core Domain Chart Quadrants

### High Value, High Complexity
- **Category**: Core Domain
- **Strategy**: Invest heavily, best team, highest quality
- **Risk**: High cost of change, but essential
- **Example**: Proprietary algorithm

### High Value, Low Complexity
- **Category**: Differentiating but Simple
- **Strategy**: Build efficiently, maintain quality
- **Risk**: May become complex over time
- **Example**: Unique but straightforward workflow

### Low Value, High Complexity
- **Category**: Necessary Evil
- **Strategy**: Simplify, buy, or outsource
- **Risk**: Waste of resources if built in-house
- **Example**: Complex but common reporting

### Low Value, Low Complexity
- **Category**: Generic Domain
- **Strategy**: Buy, use open source, minimize investment
- **Risk**: Low, standard solutions exist
- **Example**: User authentication

## Success Criteria
- Clear identification of core domains
- Stakeholder agreement on priorities
- Investment strategy aligned with value
- Team understands where to focus excellence
- Build vs buy decisions are strategic
- Resources allocated to high-impact areas
- Quality expectations match domain type

## Common Pitfalls
- **Treating everything as core**: Over-investing in generic domains
- **Ignoring business input**: Technical-only assessment
- **Confusing complex with valuable**: Complexity ≠ strategic value
- **Building everything**: Not leveraging existing solutions
- **Under-investing in core**: Penny-wise, pound-foolish
- **Static assessment**: Not revisiting as strategy evolves
- **Uniform quality**: Applying same standards everywhere

## Investment Patterns by Domain Type

### Core Domain Investment
- **Team**: Senior developers, domain experts
- **Quality**: Highest standards, extensive testing
- **Architecture**: Clean, maintainable, evolvable
- **Documentation**: Comprehensive
- **Technical Debt**: Aggressively managed
- **Innovation**: Encouraged and funded

### Supporting Domain Investment
- **Team**: Mid-level developers
- **Quality**: Good but pragmatic
- **Architecture**: Solid, standard patterns
- **Documentation**: Adequate
- **Technical Debt**: Managed periodically
- **Innovation**: Opportunistic

### Generic Domain Investment
- **Team**: Junior developers or vendors
- **Quality**: Sufficient, meets requirements
- **Architecture**: Standard, proven solutions
- **Documentation**: Minimal, rely on vendor docs
- **Technical Debt**: Acceptable if isolated
- **Innovation**: Adopt vendor innovations

## Integration with Other Steps
- **Builds on Decompose**: Requires identified sub-domains
- **Builds on Understand**: Needs business strategy context
- **Feeds into Connect**: Informs integration priorities
- **Feeds into Organise**: Influences team allocation
- **Feeds into Define**: Determines depth of modeling
- **Feeds into Code**: Sets quality and investment levels

## AI Agent Prompts

When asking AI to help with this step, use prompts like:
- "Is [sub-domain] a core, supporting, or generic domain for [industry]?"
- "What strategic questions assess business differentiation for [domain]?"
- "Create a core domain chart for [business context]"
- "Evaluate build vs buy for [capability]"
- "What makes [sub-domain] strategically important?"
- "How should we prioritize investment across these domains: [list]?"
- "What are indicators that [sub-domain] is core to [business]?"

## Example Outputs
- Core domain chart with all sub-domains plotted
- Strategic assessment document
- Build vs buy decision matrix
- Investment allocation plan
- Quality standards by domain type
- Team assignment strategy
- Wardley map showing evolution
- Stakeholder presentation on priorities

## Revisiting Strategy
Strategic assessment isn't one-time:
- **Quarterly**: Review as part of planning cycles
- **When**: Business strategy shifts
- **When**: Market conditions change
- **When**: Competitive landscape evolves
- **When**: New technology creates opportunities

## Tips for Success
- Involve business stakeholders from the start
- Use visual tools for stakeholder communication
- Challenge assumptions about what's "core"
- Consider market trends and evolution
- Be honest about complexity
- Don't conflate current with future state
- Document strategic rationale
- Create buy-in for investment decisions
- Plan for evolution of classification
