# ComfyUI Agent Orchestration Specification V1

## Architecture

```text
USER
 ↓
AGENTS.md                  policy + invariants
 ↓
REQUEST ROUTER             classify + select route
 ↓
WORKFLOW REGISTRY          reuse discovery
 ↓
SELECTIVE SKILLS           domain procedures
 ↓
MCP / TOOLS                live operations
 ↓
LIVE COMFYUI               runtime source of truth
 ↓
VALIDATE → EXECUTE → INSPECT
 ↓
SAVE / RECOVER / REPORT
```

## Responsibility Boundaries

- `AGENTS.md`: what must be true
- Router: which path/skills are needed
- Skills: how to handle a subsystem
- MCP/tools: perform actual actions
- State: cached hints
- Registry: reusable workflow discovery
- Validation: structural success
- Quality inspection: goal/output success

## Core Strategy

Reuse → Modify → Add only what is missing → Validate → Execute → Verify

## Production Gate

A workflow is production only when:
- purpose is clear
- graph validates
- required resources are recognized
- execution succeeds
- editable/advanced/fixed parameters are separated
- unnecessary request-specific hard-coding is absent
- at least one meaningful variation works without structural modification
- registry metadata exists
