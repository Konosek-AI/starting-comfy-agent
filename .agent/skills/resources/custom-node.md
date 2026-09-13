# Custom Node Skill

1. Identify exact missing capability/error.
2. Check built-in nodes.
3. Check installed custom nodes.
4. Inspect live node registry/schema.
5. Evaluate candidate packages only if still necessary.
6. Verify source, compatibility, dependencies, environment impact, and correct package identity.
7. Install only required package.
8. Restart/reload when required.
9. Verify:
   installed → loaded → recognized → schema-compatible → workflow-compatible → executed
10. Run a minimal test.
11. Run target workflow.
12. Record useful verified state.

ComfyUI-Manager:
- distinguish CNR vs Git package installation semantics
- do not use CNR-only latest semantics for Git-only packages
