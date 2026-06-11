---
description: TypeScript and code quality standards for this project
paths:
  - src/**/*.ts
  - src/**/*.svelte
---

# TypeScript and Code Quality

- All `<script>` blocks must use `lang="ts"`
- Explicit type annotations on all variables and props
- Strict mode is active — no implicit `any`, no unused locals/params
- Target: ES2023, module: ESNext
- Use `camelCase` for variables/functions and `PascalCase` for components.
- Name event handlers with the `handle` prefix (e.g., `handleClick`).
- Run `npm run check` and `npm run format` after major changes.
