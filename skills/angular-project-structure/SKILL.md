---
name: angular-project-structure
description: Enforces a strict three-tier directory structure (core, shared, pages) for Angular projects. Use this skill when generating new Angular files, planning project scaffolding, deciding where to place logic (e.g., services vs. UI components), or restructuring an existing Angular application.
license: MIT
---

# Angular Project Architecture

This skill governs where code is placed and how logic is distributed across the application.

## Directory Hierarchy

1. **`/app/core`**: For non-DOM / non-UI code.
   - Includes services, classes / interfaces, constants, enums, helper/utility functions, guards, and interceptors.
2. **`/app/shared`**: For UI pieces that are reusable across many features/pages.
   - Includes reusable components, directives, and pipes.
3. **`/app/pages`**: For route-level components (screens) such as Home, Products, etc.

## Structural Rules

- If it doesn’t touch the DOM (logic, HTTP, auth, state helpers, typing), place it in `core`.
- Keep types/interfaces close to their domain but still under `core`.
- Keep helper functions in `core/utils` (or `core/helpers`) and ensure they’re UI-agnostic.
- Keep pages thin.
- Page components should mostly orchestrate UI and call services.
- Put business logic, data shaping, and API access in `core` services/helpers.
- If you see repeated UI patterns, suggest extracting them into `shared/components`.
- Put transformation logic for templates in `shared/pipes` where appropriate.

## Output Requirements

- When answering, include the intended file path(s) for any new code.
- Include any necessary imports and module/provider registrations, but do not introduce unnecessary complexity.
