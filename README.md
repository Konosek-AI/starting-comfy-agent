# Comfy Agent — Project-Local Runtime V1

This package is ready to place at the root of a Codex/ComfyUI agent project.

## Runtime policy

- The only ComfyUI runtime used by the agent is `<PROJECT_ROOT>/ComfyUI/`.
- External ComfyUI installations are ignored and left untouched.
- Runtime code, Python environment, custom nodes, frontend/configuration, and runtime-specific dependencies stay project-local.
- Large static model assets may be shared only through an explicitly configured shared model root.
- No arbitrary external model-directory discovery.

## Main structure

```text
<PROJECT_ROOT>/
├── AGENTS.md
├── .agent/
│   ├── REQUEST_ROUTER_V1.md
│   ├── bootstrap.md
│   ├── state.md
│   └── skills/
├── workflow-registry/
├── workflows/
│   ├── production/
│   ├── templates/
│   └── experiments/
├── outputs/
├── docs/
└── ComfyUI/                  # created/used here only
```

A shared model store, when explicitly enabled, can live elsewhere, for example `D:/AI-Models/`, but it is not a ComfyUI runtime.

## First-use request

`/inspect 현재 프로젝트 전용 ComfyUI 환경을 확인해. <PROJECT_ROOT>/ComfyUI만 런타임으로 사용하고, 없다면 bootstrap 규칙에 따라 이 프로젝트 내부에 구성해. 외부 ComfyUI 런타임은 탐색하거나 재사용하지 마. 확인한 상태는 .agent/state.md에 기록해.`

## Normal-use principle

Reuse → Modify → Add only what is missing → Validate → Execute → Verify
