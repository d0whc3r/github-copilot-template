# GitHub Copilot Template

A comprehensive template for configuring AI-assisted development workflows in VS Code and GitHub Copilot. Provides a structured framework for AI agents operating as "Autonomous Principal Engineers" following strict operational doctrines and spec-driven development methodologies.

## What This Project Does

Transforms your repository into an intelligent development environment where AI agents follow rigorous protocols for:

- Systematic code and architecture analysis before changes
- Structured development using Spec-Driven Development (SDD)
- Concise, professional communication
- Autonomous execution with automatic verification and error correction
- Guaranteed quality through quality gates and audits

## Key Components

### [Operational Doctrine](.github/copilot-instructions.md)

Core instructions defining AI agent behavior:

- **Phase 0: Reconnaissance** - Complete project analysis before code changes
- **Mandatory Workflow**: Reconnaissance → Planning → Execution → Verification → Reporting
- Safe command execution with timeouts and error handling
- Extreme ownership - agents must update all consumers of modified components

### [Communication Guidelines](.github/instructions/)

- [Radical Conciseness](.github/instructions/concise.instructions.md) - Maximum signal, minimum noise
- [No Sycophantic Language](.github/instructions/no-absolute-right.instructions.md) - Professional communication rules
- [Core Doctrine](.github/instructions/core.instructions.md) - Complete operational framework

### [SDD Framework](.github/prompts/sdd/README.md)

Complete methodology for feature development with specialized prompts for each phase:

- `/sdd:research` - Comprehensive research before specifications
- `/sdd:spec` - Structured requirements using EARS methodology
- `/sdd:validate` - Specification quality validation
- `/sdd:design` - Design documents with Mermaid diagrams
- `/sdd:estimate` - Complexity and resource estimation
- `/sdd:test-plan` - Comprehensive testing strategies
- `/sdd:security-review` - Security analysis and compliance
- `/sdd:tasks` - Actionable implementation tasks
- `/sdd:implement` - Execute and track individual implementation tasks
- `/sdd:refactor` - Systematically refactor core spec documents, then guide user through sequential updates of all subsequent documents using specific SDD commands for clean, consistent workflow

### [Chat Modes](.github/chatmodes/)

- [SDD Exclusive Mode](.github/chatmodes/sdd.chatmode.md) - Forces structured development workflows

### [Specialized Prompts](.github/prompts/)

- [Feature Development](.github/prompts/feature.prompt.md) - Standard protocol for features/refactors
- [Command Creation](.github/prompts/command-creator.prompt.md) - System command generation
- [Diagnosis](.github/prompts/diagnose.prompt.md) - Problem analysis
- [Documentation](.github/prompts/docs) - Documentation/Steering docs creation
- [Execution](.github/prompts/execute.prompt.md) - Task execution
- [Testing](.github/prompts/testing.prompt.md) - Testing strategies
- [Retrospectives](.github/prompts/retrospective.prompt.md) - Project analysis

### Development with SDD

For any new feature:

```bash
/sdd:research "Feature description"
/sdd:spec "Feature description"
/sdd:validate "feature-name"
/sdd:design "feature-name"
/sdd:estimate "feature-name"
/sdd:test-plan "feature-name"
/sdd:security-review "feature-name"
/sdd:tasks "feature-name"
/sdd:implement "feature-name"  # Execute tasks one by one
```

**Optional: Post-implementation refinement**

```bash
/sdd:refactor "feature-name" "specific-refactoring-guidance"
# Examples:
/sdd:refactor "user-authentication" "Use Redis for sessions, implement JWT refresh, add rate limiting"
/sdd:refactor "payment-system" "Integrate Stripe API v3, add webhook retry logic, use database transactions"
/sdd:refactor "dashboard" "Use Chart.js for visualizations, implement WebSocket updates, cache expensive queries"
```

_Note: The refactor command now follows a systematic approach - it first improves core documents (research and requirements), then guides you through sequential updates of all subsequent documents using specific SDD commands for clean, consistent workflow._

**What to include in refactoring guidance:**

- **Tools & Frameworks**: "Use Redis for caching, implement with AWS Lambda"
- **Processes**: "Apply TDD methodology, use feature flags for rollout"
- **Business Rules**: "Support multi-tenant architecture, implement GDPR compliance"
- **Integrations**: "Connect to existing auth service, use REST APIs with OAuth2"
- **Quality Standards**: "Ensure WCAG accessibility, implement SOC2 controls"

**After tasks are approved, execute them one by one:**

```bash
/sdd:implement "feature-name"  # Executes next pending task and tracks progress
```

````

## Prerequisites for Effective SDD

### Project Knowledge Foundation

**For SDD to produce optimal results, it is HIGHLY RECOMMENDED to have a deep understanding of the project before starting.** AI agents need complete context about:

- Existing project architecture
- Code patterns and conventions
- Technologies and frameworks used
- Data structures and models
- Non-functional requirements (security, performance, scalability)

### Steering Documents - Fundamental Base

**BEFORE starting any SDD workflow, steering documents for the project MUST be generated and kept updated.** These documents provide:

- **Project Standards**: Code conventions, architectural patterns, quality standards
- **Coding Conventions**: Style guides, naming conventions, file structure
- **Architectural Patterns**: Design patterns used, architectural principles
- **Team Norms**: Team processes, documentation standards, collaboration practices

### Command for Steering Documents

```bash
/docs:create-steering [type]
````

**Run this command at project start and keep steering documents updated** whenever project standards change, new technologies are incorporated, or team practices evolve.

#### Steering Document Types

The `/docs:create-steering` command accepts an optional `type` parameter to generate specific types of steering documents. It is **HIGHLY RECOMMENDED** to have at minimum the following three types:

- **`product`**: Product vision, business requirements, user personas, and market context
- **`technology`**: Technology stack, frameworks, tools, and technical standards
- **`structure`**: Team organization, development processes, and project structure

##### Examples of Steering Document Types

```bash
# Generate all recommended steering documents
/docs:create-steering product
/docs:create-steering technology
/docs:create-steering structure

# Generate additional specialized documents
/docs:create-steering security      # Security policies and standards
/docs:create-steering quality       # Quality assurance and testing standards
/docs:create-steering deployment    # Deployment and DevOps practices
/docs:create-steering compliance    # Regulatory and compliance requirements
/docs:create-steering architecture  # Architectural principles and patterns
/docs:create-steering testing       # Testing strategies and methodologies
```

**Additional steering document types can be created as needed** to document specific aspects of your project, team, or organization. Each type creates a focused document that provides essential context for AI agents to understand and work effectively within your project's ecosystem.

### Why Steering Documents Are Critical

Without updated steering documents:

- Specifications may not align with project standards
- Designs may use inconsistent patterns
- Estimates may be inaccurate
- Generated code quality may be inferior

**Steering documents are the foundation that guarantees SDD produces consistent, high-quality results aligned with the project vision.**

## Directory Structure

```
.github/
├── copilot-instructions.md          # Main operational doctrine
├── instructions/                    # Specific rules
│   ├── concise.instructions.md      # Conciseness rules
│   ├── core.instructions.md         # Complete doctrine
│   └── no-absolute-right.instructions.md  # Communication rules
├── prompts/                         # Task-specific prompts
│   ├── *.prompt.md                  # Various specialized prompts
│   └── sdd/                         # Complete SDD framework
│       ├── README.md                # Detailed SDD documentation
│       └── *.prompt.md              # SDD phase prompts
└── chatmodes/                       # Interaction modes
    └── sdd.chatmode.md              # Exclusive SDD mode
```

## Benefits

### Quality Assurance

- Clear specifications before coding
- Documented designs with architectural decisions
- Comprehensive testing from inception
- Integrated security reviews

### Efficiency Gains

- Standardized processes reduce review time
- Autonomous agents handle repetitive tasks
- Early problem and risk detection
- Automatic documentation during development

### Optimized Collaboration

- Consistent language across communications
- Complete traceability from idea to implementation
- Structured approvals at each phase
- Accumulated knowledge in specifications

## Examples

### REST API Development

```bash
/sdd:research "Implement REST API for user management"
/sdd:spec "Implement REST API for user management"
/sdd:validate "user-management-api"
/sdd:design "user-management-api"
/sdd:estimate "user-management-api"
/sdd:test-plan "user-management-api"
/sdd:security-review "user-management-api"
/sdd:tasks "user-management-api"
/sdd:implement "user-management-api"
```

### Component Refactor

```bash
/sdd:research "Refactor authentication component"
/sdd:spec "Refactor authentication component"
/sdd:validate "auth-refactor"
/sdd:design "auth-refactor"
/sdd:estimate "auth-refactor"
/sdd:test-plan "auth-refactor"
/sdd:security-review "auth-refactor"
/sdd:tasks "auth-refactor"
/sdd:implement "auth-refactor"
```

## Contributing

- Follow the operational doctrine in contributions
- Maintain radical conciseness in documentation
- Test changes with real examples
- Update documentation as needed

## License

MIT License - Fork, modify, and use as needed.

---

**Note**: This template maximizes quality and efficiency of AI-assisted development. The operational doctrine ensures agents maintain high engineering standards while operating autonomously.
