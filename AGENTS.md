# Agents

## Runtime & Package Manager

This project uses **Bun** as both the runtime and package manager. Do not use Node.js or npm/pnpm/yarn commands.

- Install dependencies: `bun install`
- Run the app: `bun start`
- Dev mode (watch): `bun dev`

## Build & Run

There is no separate build step. Bun runs TypeScript directly. The entrypoint is `src/index.ts`.

## Docker

```bash
bun docker:build    # Build the image
bun docker:start    # Start detached
bun docker:stop     # Stop
bun docker:restart  # Stop, rebuild, and start
```

The Dockerfile uses a multi-stage build with `oven/bun:1-alpine`.

## TypeScript Configuration

- Target: ESNext, Module: NodeNext
- Strict mode enabled
- ESM only (`"type": "module"` in package.json)
- Output dir: `./dist`, source root: `./src`

## Conventions

- No test framework or linter is configured. If adding one, prefer Bun-native tooling (`bun test`).
- The README references `pnpm` but the project actually uses Bun — maintain Bun usage.
