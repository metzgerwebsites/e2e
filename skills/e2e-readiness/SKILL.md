---
name: e2e-readiness
description: Verify completion of a UI change in an e2e-enabled project. Use when handing off a feature, fix, or regression test. Requires the real user path, test assertions, retained evidence, and explicit coverage gaps. Does not install dependencies or choose a model provider.
---

# e2e readiness

Use the installed `e2e` skill for the API and `verify-<app>` for project facts.
Prefer a project's locked e2e executable; otherwise use `e2e` on PATH.
General browser work retains the user's selected browser tool.
This skill governs e2e test evidence, not every task.

1. Establish the checkout, source revision, changed user behavior, target,
   app launch command, and existing tests. Do not run a neighboring project.
2. Exercise the affected user path. Use native MCP when available, or the
   project's CLI suite. Pin outcomes with assertions, including the relevant
   side effect when a screen alone cannot prove success.
3. Run the relevant suite with a unique `--output` directory. Use the project's
   `verify-<app>` instructions. Read `report.json` and the failed trace.
   Do not infer success from server startup, an MCP close, or an agent summary.
4. Report the command, source revision, result, evidence path, and untested
   cases. Keep the report with its referenced artifacts. A normal run replaces
   the previous report and results, so retain evidence outside a reused output.
   A `--last-failed` run preserves the artifacts of tests it carries forward.
5. Close only sessions and app processes owned by this task. Separate browser
   sessions do not isolate a shared database, account, port, or mobile device.

Never hide a failed assertion or weaken it to obtain a pass.
A replay-cache option does not authorize model or provider charges.
Never transmit screenshots, videos, reports, or feedback without authorization.

If the project lacks a verification skill, use the installed
`create-verification-skill` when bootstrap is authorized. A generated skill
is a draft until its own real app checks run. An unavailable model can leave
exploration unproven while deterministic tests and interactive MCP still work.
