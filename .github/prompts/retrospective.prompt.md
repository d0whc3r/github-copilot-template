---
mode: agent
description: Conduct post-session retrospective and update operational doctrine
tools:
  - runCommands/runInTerminal
  - runCommands/getTerminalOutput
  - runTasks
  - edit/createFile
  - edit/createDirectory
  - edit/editFiles
  - search
  - new/getProjectSetupInfo
  - usages
  - vscodeAPI
  - think
  - changes
  - fetch
  - githubRepo
  - todos
---

# /retrospective

Conduct critical retrospective analysis and update operational doctrine with distilled lessons.

## Phases

### Phase 0: Reconnaissance (Read-Only)

Core principle: Understand before you touch. Do not modify files or run changes during reconnaissance.

Required reconnaissance steps:

1. **Session Inventory:** Systematically review the entire conversation history to catalogue key interactions, user feedback, and behavioral patterns.
2. **Doctrine Topology:** Analyze doctrine files (e.g., `.github/copilot-instructions.md`, `AGENT.md`, `.cursorrules`) to construct a mental model of current rules and structures.
3. **Behavioral Insights:** Infer operational patterns, successes, and failures from the conversation.
4. **Quality Gates Assessment:** Identify relevant verification mechanisms (e.g., doctrine consistency checks).
5. **Reconnaissance Digest:** Produce a concise synthesis (≤ 200 lines) that anchors the plan, including system-wide implications of potential updates.

### Phase 1: Analysis Framework

Conduct holistic analysis of the session.

**Successes:** Identify core principles that enabled efficient outcomes, such as adherence to doctrine or effective tool usage.

**Failures:** Pinpoint root causes of user corrections, including violations of doctrine or incomplete understanding.

**Lessons:** Extract transferable patterns for future missions, focusing on universal principles.

### Phase 2: Lesson Distillation

Filter and refine insights into durable lessons.

**Quality Filter:** Accept only lessons that are:

- **Universal:** Apply across projects, not session-specific.
- **Abstracted:** General principles, not implementation details.
- **High-Impact:** Prevent failures or improve efficiency significantly.

**Distillation Process:**

- Abstract insights into tool-agnostic principles.
- Ensure lessons align with existing doctrine quality standards.
- Discard session-specific or low-impact observations.

### Phase 3: Doctrine Integration

Update doctrine with distilled lessons.

**Target Selection:**

1. Project doctrine first: `.github/copilot-instructions.md`, `AGENT.md`, `.cursorrules`.
2. Global doctrine fallback: Core operational files (e.g., `core.instructions.md`).

**Integration Rules:**

- Read target file structure first to understand formatting and tone.
- Refine existing rules rather than append new sections.
- Match established formatting, tone, and structure.
- Ensure backward compatibility and consistency.
- Enumerate all consumers of changed rules and plan updates.

**Execution Workflow:**

- Plan: Enumerate changes and impacts.
- Execute: Apply updates using appropriate tools.
- Verify: Reread altered files, run quality gates (e.g., consistency checks).
- Autonomous Correction: If issues arise, diagnose and fix root causes.

### Phase 4: Final Report

Document changes and learnings.

**Output Format:**

```
Doctrine Updates
- File: path/to/updated/file
- Changes: [concise diff summary]

Session Insights
- Success: [key pattern identified]
- Failure: [root cause + correction]
- Lesson: [universal principle distilled]
```

**Reporting Legend:** Use `✅` for success, `⚠️` for self-corrected issues, `🚧` for blockers.

## Critical Constraints

- Update doctrine ONLY with durable, universal lessons.
- Never create analysis artifacts in repository.
- Maintain existing doctrine quality standards.
- Execute with precision - this evolves your core logic.
- Follow radical conciseness in all outputs.
