# Request Router V1

## Universal Route

`USER REQUEST → CLASSIFY → EXTRACT CAPABILITIES → RESOLVE WORKFLOW → ACTIVATE REQUIRED SKILLS → RESOLVE RESOURCES → BUILD/MODIFY → VALIDATE → EXECUTE → INSPECT → SAVE/RECOVER → REPORT`

## Request Classes

- GENERATE
- MODIFY
- CREATE_REUSABLE
- EXPERIMENT
- DIAGNOSE
- ENVIRONMENT
- INSPECT

## Existing Workflow Decision

```text
Existing workflow?
  ├─ no → create only if needed
  └─ yes
      └─ parameter change enough?
          ├─ yes → reuse
          └─ no
              └─ small graph change enough?
                  ├─ yes → version/modify
                  └─ no → create new
```

## Skill Routing

| Need | Skill |
|---|---|
| workflow reuse/design/edit | `skills/workflow.md` |
| model selection/compatibility | `skills/resources/model.md` |
| LoRA selection/use | `skills/resources/lora.md` |
| missing/uncertain custom node | `skills/resources/custom-node.md` |
| prompt creation/change | `skills/conditioning/prompting.md` |
| reference/identity/pose/control | `skills/conditioning/reference-control.md` |
| graph/resource validation | `skills/result/validation.md` |
| visual/semantic quality | `skills/result/quality.md` |
| error diagnosis/recovery | `skills/result/troubleshooting.md` |
| environment setup/recovery | `bootstrap.md` |

## Reusable Workflow Rule

For CREATE_REUSABLE:
- search registry/templates first
- separate editable/advanced/fixed parameters
- avoid unnecessary hard-coding
- validate
- execute
- test one meaningful variation
- save production only after verification
- update registry
