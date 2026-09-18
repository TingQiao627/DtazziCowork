# DtazziCowork Code Review Profile

## Project
Electron + React 19 + TypeScript application — AI cowork assistant with multi-provider AI API support.

## Changed surface
- `src/ui/`: React UI components, hooks, store (Zustand)
- `src/electron/`: Electron main process
- `src/shared/`: Shared utilities
- `tests/`: Vitest unit tests

## Review gates
- **No debug artifacts**: `console.log` / `debugger` statements must not remain in production code unless justified by a comment explaining their purpose.
- **i18n**: User-facing strings must use `useTranslation()` / `t(...)` from `react-i18next`.
- **Type safety**: Avoid `any` casts; prefer precise types from `@qwen-code/sdk` or shared type definitions.
- **Error handling**: Async paths must have `.catch()` or `try/catch` with logging via `./src/ui/utils/logger`.
- **Performance**: Avoid unnecessary re-renders — check deps arrays in `useEffect`/`useCallback`/`useMemo`.
- **Test coverage**: New features should include Vitest tests under `tests/`.

## Linting
- ESLint configured; run `npm run lint` before merge.