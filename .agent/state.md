# Agent State

This file stores cached project/environment hints.
Runtime truth wins when this state may be stale.

## Project Runtime

```yaml
runtime:
  scope: project-local
  path: <PROJECT_ROOT>/ComfyUI
  comfyui_endpoint:
  comfyui_version:
  frontend_version:
  mcp_status:
  gpu:
  vram:
  last_verified_at:
```

## Shared Models

```yaml
shared_models:
  enabled: false
  root:
  configuration_file:
```

Rules:
- `runtime.path` must remain inside the current project.
- External ComfyUI runtimes are not candidates.
- `shared_models.root` is used only when explicitly configured.
- Do not auto-discover a shared model root.

## Known Resources

### Custom Nodes
Project-local only.
-

### Models
Project-local or explicitly configured shared model storage.
-

### LoRAs
Project-local or explicitly configured shared model storage.
-

## Recent Production Workflow

```yaml
workflow_id:
workflow_path:
last_successful_run:
last_output:
```

## Known Issues
-

## Re-check When

- project-local runtime install/restart occurred
- relevant resources changed
- execution fails unexpectedly
- cache is stale/unknown
- user explicitly requests current status
