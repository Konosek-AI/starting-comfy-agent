# Bootstrap and Recovery

Use Bootstrap only when the project-local runtime is missing, broken, materially changed, or explicitly requested.

## Runtime Boundary

The only valid ComfyUI runtime for this project is:

`<PROJECT_ROOT>/ComfyUI/`

Do not search for external ComfyUI installations.

Do not reuse, modify, repair, inspect, or depend on external ComfyUI runtimes.

External ComfyUI installations must remain untouched.

## Shared Model Boundary

Large static model assets may be shared only through an explicitly configured shared model root.

- Do not auto-discover arbitrary external model directories.
- If a shared model root is configured in `.agent/state.md`, use it through a ComfyUI-supported extra model path configuration when practical.
- If no shared model root is configured, use `<PROJECT_ROOT>/ComfyUI/models/`.
- Never use the shared model store for custom nodes, Python environments/packages, frontend extensions, or ComfyUI runtime code.

## Procedure

1. Determine the current project root.
2. Check `<PROJECT_ROOT>/ComfyUI/`.
3. If it exists, inspect/repair that runtime only.
4. If it does not exist, create a new ComfyUI runtime at `<PROJECT_ROOT>/ComfyUI/`.
5. Set up runtime-specific Python/dependencies for this project.
6. Verify GPU and VRAM visibility.
7. Apply the explicitly configured shared model path if enabled; otherwise use project-local models.
8. Start the project-local ComfyUI runtime.
9. Verify its API is reachable.
10. Verify MCP communicates with this exact project-local runtime.
11. Record verified state in `.agent/state.md`.

## Do Not

- search the machine for another usable ComfyUI runtime
- redirect MCP to an external runtime
- reinstall a healthy project-local runtime
- modify external ComfyUI installations
- auto-discover arbitrary model folders
- record guesses as verified state
