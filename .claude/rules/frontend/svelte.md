---
description: Svelte 5 runes syntax and component conventions for this project
paths:
  - src/**/*.svelte
---

# Svelte 5 Runes (required)

Always use Svelte 5 runes syntax. Never use Svelte 4 patterns.

| Svelte 5 (correct)          | Svelte 4 (forbidden)              |
|-----------------------------|-----------------------------------|
| `$state()`                  | `let x = 0` (reactive vars)       |
| `$derived()`                | `$: y = x * 2`                    |
| `$effect()`                 | `$: { sideEffect() }`             |
| `$props()`                  | `export let prop`                 |
| `onclick={handler}`         | `on:click={handler}`              |
| `mount()` from `'svelte'`   | `new App()`                       |

```svelte
<script lang="ts">
  let count: number = $state(0)
  const double = $derived(count * 2)

  let { label = 'Click me' }: { label?: string } = $props()
</script>
```

# Component Conventions

- Components live in `src/lib/`
- Entry point: `src/App.svelte` → mounted in `src/main.ts`
- Scoped styles in `<style>` block at the bottom of each component
- Use arrow functions for event handlers
- This is a pure Svelte SPA — **not SvelteKit**. No file-based routing, no `+page.svelte`, no server-side load functions.

# MCP Tool

The `@sveltejs/mcp` server is configured. Always use `mcp__svelte__*` tools when:
- Writing new Svelte components or patterns
- Debugging Svelte-specific errors
- Looking up Svelte 5 API

After making corrections, call the MCP tool again to confirm all issues are resolved.
