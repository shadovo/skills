---
name: harsh-code-review
description: Detailed instructions for performing a thorough code review. Use this skill when asked to review code or create a code review.
---

When performing a code review, follow these steps:

Harshly review this PR. Do not hold back — suggest large refactors or rewrites if the situation calls for it.

1. Check for correctness and logic errors
2. Is the code kept simple and avoids overcomplicating things?
3. Verify adherence to the project's coding standards
4. Is this the right long-term solution, or just a workaround?
5. Make sure dead code and unused options are removed
6. There is no need to be backwards compatible. Remove old versions, shims, and fallbacks — everything should use the new approach.
7. Assess performance implications
8. Confirm adequate test coverage
9. Review naming conventions and code readability
10. Check for proper error handling
11. Make sure docs and copilot instructions are up to date
12. Evaluate what became better and what became worse in this PR

Always provide constructive, specific feedback with line references where applicable.

## Implementing the Fix

After completing the review, also implement the fixes for all issues identified:

1. Apply all suggested code changes directly — do not just describe what should be done.
2. If a large refactor or rewrite was recommended, carry it out fully.
3. Remove dead code, unused options, old shims, and fallbacks as part of the fix.
4. Update or add tests to cover the changes made.
5. Update any relevant docs or Copilot instructions affected by the fix.
6. Ensure all fixes align with the project's coding standards and long-term direction.
7. After implementing, do a final pass to confirm no new issues were introduced.

## Validation

After implementing all fixes, run the following to confirm nothing is broken:

1. **Linting**: `npm run format && npm run lint` — must pass with 0 errors and 0 warnings.
2. **Type checking**: `npm run check` — must pass with no type errors.
3. **Unit tests**: `npm run test:unit -- --run` — all tests must pass.
4. **E2E tests**: `npm run test:e2e` — all Playwright tests must pass.

Fix any failures before considering the review complete.
