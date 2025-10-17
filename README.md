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
- `/sdd:refactor` - Existing specification improvements

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
```

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
