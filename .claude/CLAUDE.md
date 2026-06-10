# Project: Svelte 5 + Vite + TypeScript SPA

Udemy course follow-along project. Pure Svelte SPA — **not SvelteKit**. No file-based routing, no `+page.svelte`, no server-side load functions.

## Commands

```bash
npm run dev       # start dev server
npm run build     # production build
npm run preview   # preview production build
npm run check     # type-check all .svelte, .ts, .js files
```

## Svelte 5 Runes (required)

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

## TypeScript and Code Quality

- All `<script>` blocks must use `lang="ts"`
- Explicit type annotations on all variables and props
- Strict mode is active — no implicit `any`, no unused locals/params
- Target: ES2023, module: ESNext
- Use `camelCase` for variables/functions and `PascalCase` for components.
- Name event handlers with the `handle` prefix (e.g., `handleClick`).
- Run `npm run check` and `npm run format` after major changes.

## Component Conventions

- Components live in `src/lib/`
- Entry point: `src/App.svelte` → mounted in `src/main.ts`
- Scoped styles in `<style>` block at the bottom of each component
- Use arrow functions for event handlers
  
## Styling
- Use Tailwind CSS classes over inline styles.
- Do not use CSS-in-JS libraries unless explicitly added.

## MCP Tool

The `@sveltejs/mcp` server is configured. Always use `mcp__svelte__*` tools when:
- Writing new Svelte components or patterns
- Debugging Svelte-specific errors
- Looking up Svelte 5 API

After making corrections, call the MCP tool again to confirm all issues are resolved.