# SDD Spec-Driven Development Framework

A comprehensive framework for structured feature development using specification-driven methodology. This framework provides specialized AI agents for each phase of the development lifecycle, ensuring high-quality, well-documented, and thoroughly tested features.

## Overview

Spec-driven development is an iterative methodology that transforms rough feature ideas into production-ready implementations through systematic phases: Research → Requirements → Design → Tasks → Implementation. Each phase is supported by specialized AI agents that ensure quality, consistency, and completeness.

## Available Commands

### Core Workflow Commands

#### `/sdd:research`

**Purpose:** Conduct comprehensive research before creating specifications
**Input:** Feature description and research scope
**Output:** `docs/specs/{feature_name}/research.md`
**Benefits:**

- Identifies technical constraints early
- Uncovers existing patterns and solutions
- Reduces implementation risks
- Informs better architectural decisions

#### `/sdd:spec`

**Purpose:** Generate structured requirements using EARS methodology
**Input:** Feature description
**Output:** `docs/specs/{feature_name}/requirements.md`
**Benefits:**

- Creates testable, measurable requirements
- Uses Easy Approach to Requirements Syntax (EARS)
- Ensures stakeholder alignment
- Provides foundation for design and testing

#### `/sdd:validate`

**Purpose:** Validate spec document quality and completeness
**Input:** Feature name and validation scope
**Output:** `docs/specs/{feature_name}/validation.md`
**Benefits:**

- Ensures spec quality before implementation
- Identifies gaps and inconsistencies
- Provides quality metrics and scores
- Reduces rework and misunderstandings

#### `/sdd:design`

**Purpose:** Create comprehensive design documents with research integration
**Input:** Feature name (requires existing requirements.md)
**Output:** `docs/specs/{feature_name}/design.md`
**Benefits:**

- Documents architectural decisions
- Includes Mermaid diagrams for visualization
- Addresses security and scalability
- Provides implementation guidance

#### `/sdd:estimate`

**Purpose:** Estimate complexity, time, and resources for implementation
**Input:** Feature name (requires spec documents)
**Output:** `docs/specs/{feature_name}/estimation.md`
**Benefits:**

- Provides realistic project planning
- Identifies resource requirements
- Assesses risks and uncertainties
- Enables better stakeholder communication

#### `/sdd:test-plan`

**Purpose:** Create comprehensive testing strategies and plans
**Input:** Feature name (requires spec documents)
**Output:** `docs/specs/{feature_name}/test-plan.md`
**Benefits:**

- Defines testing pyramid approach
- Ensures comprehensive coverage
- Includes automation strategies
- Provides quality gates and exit criteria

#### `/sdd:security-review`

**Purpose:** Conduct security analysis and compliance assessment
**Input:** Feature name (requires spec documents)
**Output:** `docs/specs/{feature_name}/security-review.md`
**Benefits:**

- Implements security by design
- Identifies vulnerabilities early
- Ensures regulatory compliance
- Provides security testing strategies

#### `/sdd:tasks`

**Purpose:** Generate actionable implementation tasks for coding agents
**Input:** Feature name (requires design.md)
**Output:** `docs/specs/{feature_name}/tasks.md`
**Benefits:**

- Creates coding agent executable tasks
- Ensures incremental, testable progress
- Maintains requirement traceability
- Focuses on implementation details

#### `/sdd:implement`

**Purpose:** Execute and track individual implementation tasks for completed SDD features
**Input:** Feature name that has completed the full SDD workflow
**Output:** Implemented code changes, updated tasks.md with completion status
**Benefits:**

- Executes one task at a time with full SDD context
- Automatically marks tasks as in progress and completed
- Uses all SDD documents for proper implementation
- Ensures implementation quality matches specifications
- Provides clear progress tracking and completion announcements

## Recommended Workflow

```mermaid
graph TD
    A[Feature Idea] --> B[/sdd:research]
    B --> C[/sdd:spec]
    C --> D[/sdd:validate]
    D --> E[/sdd:design]
    E --> F[/sdd:estimate]
    F --> G[/sdd:test-plan]
    G --> H[/sdd:security-review]
    H --> I[/sdd:tasks]
    I --> J[/sdd:implement]
    J --> K[Implementation Complete]
    K --> L[/sdd:refactor]
    L --> M[Done]

    D --> N[Refine Requirements]
    N --> C

    E --> O[Refine Design]
    O --> E

    I --> P[Refine Tasks]
    P --> I

    J --> Q[Execute Next Task]
    Q --> J
```

### Phase Descriptions

1. **Research Phase** - Gather context and reduce uncertainty
2. **Specification Phase** - Define what needs to be built
3. **Validation Phase** - Ensure spec quality and completeness
4. **Design Phase** - Define how it will be built
5. **Estimation Phase** - Plan resources and timeline
6. **Testing Phase** - Define quality assurance approach
7. **Security Phase** - Address security and compliance
8. **Task Planning Phase** - Create implementation roadmap
9. **Implementation Phase** - Execute tasks one by one with `/sdd:implement`
10. **Refinement Phase** - Improve documentation and processes

## Intelligent Cross-Phase Integration

The framework commands are designed to be intelligent and context-aware:

### Research Integration

- **Research Phase**: Considers existing spec documents for iterative improvement
- **Spec Phase**: Leverages research.md findings to create more informed requirements
- **Design Phase**: Uses research.md context for better architectural decisions
- **Tasks Phase**: Incorporates research constraints into implementation planning

### Spec Document Dependencies

Each command automatically reads relevant upstream documents:

- `/sdd:spec` → reads `research.md` (if exists)
- `/sdd:design` → reads `requirements.md` + `research.md` (if exists)
- `/sdd:tasks` → reads `requirements.md` + `design.md` + `research.md` (if exists)
- `/sdd:estimate` → reads all spec docs + `research.md` (if exists)
- `/sdd:test-plan` → reads all spec docs + `research.md` (if exists)
- `/sdd:security-review` → reads all spec docs + `research.md` (if exists)
- `/sdd:validate` → reads specified docs + `research.md` (if exists)
- `/sdd:refactor` → reads all docs + `research.md` (if exists)

This creates a knowledge accumulation effect where each phase builds upon previous insights.

## Recent Improvements

### Enhanced Cross-Phase Intelligence

- **Automatic Context Reading**: Commands now automatically read relevant upstream documents
- **Research Integration**: All phases leverage research.md when available for better decisions
- **Knowledge Accumulation**: Each phase builds upon insights from previous phases
- **Iterative Enhancement**: Research phase considers existing specs for continuous improvement

### Smart Dependencies

- Commands detect and read available context documents automatically
- No manual specification of input files required
- Graceful handling when upstream documents don't exist
- Enhanced decision-making based on accumulated knowledge

## Directory Structure

```
docs/specs/{feature_name}/
├── research.md              # Research findings and recommendations
├── requirements.md          # EARS-formatted requirements
├── validation.md            # Quality assessment report
├── design.md                # Architecture and design decisions
├── estimation.md            # Complexity and resource estimates
├── test-plan.md             # Testing strategy and test cases
├── security-review.md       # Security analysis and recommendations
├── tasks.md                 # Implementation task checklist
└── refactor-report.md       # Documentation improvement report
```

## Best Practices

### General Guidelines

- **Iterative Development:** Use feedback loops between phases
- **Quality Gates:** Don't proceed until each phase is approved
- **Stakeholder Involvement:** Include relevant stakeholders in reviews
- **Documentation First:** Specs drive implementation, not vice versa
- **Traceability:** Maintain clear links between all artifacts

### Research Phase

- Use multiple sources (codebase, documentation, issues)
- Document assumptions and uncertainties
- Identify technical constraints early
- Consider business and user impact

### Requirements Phase

- Use EARS format: WHEN [condition] THEN [system] SHALL [response]
- Make requirements testable and measurable
- Include edge cases and error conditions
- Focus on user needs, not implementation details

### Design Phase

- Document architectural decisions and rationales
- Consider scalability, security, and maintainability
- Use diagrams for complex relationships
- Define clear component boundaries

### Task Planning Phase

- Create tasks executable by coding agents
- Focus only on coding activities
- Ensure incremental progress with testing
- Maintain requirement traceability

### Implementation Phase

- Follow test-driven development practices
- Implement one task at a time
- Validate against requirements continuously
- Update documentation as needed

## Quality Standards

### Requirements Quality

- **Clarity:** Unambiguous and understandable
- **Completeness:** Covers all necessary scenarios
- **Testability:** Verifiable through testing
- **Feasibility:** Technically achievable

### Design Quality

- **Consistency:** Follows established patterns
- **Scalability:** Handles growth requirements
- **Security:** Addresses security concerns
- **Maintainability:** Easy to modify and extend

### Implementation Quality

- **Traceability:** Links to requirements
- **Testability:** Includes comprehensive tests
- **Performance:** Meets performance criteria
- **Reliability:** Handles error conditions gracefully

## Tool Integration

### VS Code Integration

- Commands are designed for VS Code's agent mode
- Use built-in tools for file operations and searches
- Leverage workspace context and git integration

### MCP Server Integration

- Atlassian Jira integration for issue tracking
- GitHub integration for code and issue analysis
- Upstash Context7 for library documentation
- Web search capabilities for research

### External Tool Support

- Mermaid for diagram generation
- Terminal commands for system operations
- Git integration for change tracking
- Testing frameworks integration

## Examples

### Simple Feature Example

```bash
# 1. Research the feature
/sdd:research "Add user profile pictures"

# 2. Create requirements
/sdd:spec "Add user profile pictures"

# 3. Validate specifications
/sdd:validate "user-profile-pictures"

# 4. Design the solution
/sdd:design "user-profile-pictures"

# 5. Estimate complexity
/sdd:estimate "user-profile-pictures"

# 6. Plan testing
/sdd:test-plan "user-profile-pictures"

# 7. Review security
/sdd:security-review "user-profile-pictures"

# 8. Create implementation tasks
/sdd:tasks "user-profile-pictures"

# 9. Execute implementation tasks one by one
/sdd:implement "user-profile-pictures"
```

### Complex Feature Example

For complex features requiring extensive research:

```bash
# Start with comprehensive research
/sdd:research "Implement real-time collaborative editing"

# Multiple validation and refinement cycles
/sdd:spec "Implement real-time collaborative editing"
/sdd:validate "real-time-collaboration"
/sdd:spec "Implement real-time collaborative editing"  # Refine based on validation

# Detailed planning phase
/sdd:design "real-time-collaboration"
/sdd:estimate "real-time-collaboration"
/sdd:test-plan "real-time-collaboration"
/sdd:security-review "real-time-collaboration"

/sdd:tasks "real-time-collaboration"

# Execute implementation tasks one by one
/sdd:implement "real-time-collaboration"
```

### Refactoring Example

For improving existing specifications with specific guidance:

```bash
# After implementation, add specific clarifications and improvements
/sdd:refactor "real-time-collaboration" "Use Operational Transformation for conflict resolution, implement Redis pub/sub for scalability, add rate limiting for API endpoints, ensure GDPR compliance for user data"

/sdd:refactor "user-profile-pictures" "Use AWS S3 for storage with CloudFront CDN, implement image optimization pipeline, add content moderation with AWS Rekognition, support WebP format for better performance"
```

## Troubleshooting

### Common Issues

#### Requirements Too Vague

- Use EARS format consistently
- Add concrete examples and edge cases
- Include measurable acceptance criteria

#### Design Not Scalable

- Consider future growth requirements
- Document architectural assumptions
- Include performance considerations

#### Tasks Too Large

- Break down into smaller, focused tasks
- Ensure each task is independently testable
- Maintain clear dependencies

#### Testing Coverage Insufficient

- Map tests directly to requirements
- Include edge cases and error scenarios
- Consider automated vs manual testing balance

### Getting Help

- Review existing spec examples in the workspace
- Check validation reports for specific issues
- Use refactor command to improve existing specs with specific guidance
- Consult with team members for domain expertise

### When to Use Refactor

- **After implementation**: Add clarifications discovered during development
- **Tool specification**: Specify exact frameworks, libraries, or services to use
- **Process requirements**: Clarify implementation approaches or methodologies
- **Integration needs**: Add requirements for connecting with existing systems
- **Quality standards**: Include specific compliance or performance requirements
- **Business rules**: Incorporate additional business logic or constraints

## Metrics and Success Criteria

### Process Metrics

- **Spec Quality Score:** Average > 8/10
- **Review Cycle Time:** < 2 days per phase
- **Requirement Stability:** > 90% after design phase
- **Implementation Defect Rate:** < 5% production defects

### Quality Gates

- All requirements approved before design
- Design validated before task planning
- Security review completed before implementation
- Testing plan approved before coding begins

## Contributing

### Adding New Commands

1. Follow the established YAML frontmatter format
2. Include comprehensive tool configurations
3. Implement userInput approval workflow
4. Document constraints and guidelines
5. Test with existing feature examples

### Improving Existing Commands

1. Review current implementation
2. Identify enhancement opportunities
3. Maintain backward compatibility
4. Update documentation accordingly
5. Validate with real feature examples

## License

This framework is part of the SDD IDE assistant system. See project license for usage terms.
