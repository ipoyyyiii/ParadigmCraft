# ParadigmCraft — goals

**North star:** build a clean-room reimplementation of Visual Paradigm in Rust, aiming for 1:1 functional parity with the selected baseline, then add clearly separated improvements.

**Baseline:** Visual Paradigm 18.1 installed at `/Applications/Visual Paradigm.app`. Edition, enabled modules, and complete behavior baseline are not confirmed yet.

## Guardrails

- Recreate behavior with independently written Rust code and original UI/assets; do not copy proprietary implementation or bypass licensing.
- Treat parity as a measured target: document workflows, file compatibility, commands, and test results instead of promising unverified equivalence.
- Keep coursework projects outside the workspace and unopened unless explicitly approved.
- Do not upgrade macOS as part of this project.

## Milestones

- [x] Create the workspace, project instructions, goals, and durable project memory.
- [x] Inventory the installed Visual Paradigm 18.1 app bundle by path and metadata; do not copy its contents.
- [x] Create a local Git repository, add project ignore rules, and configure the provided GitHub remote.
- [x] Confirm the public repository and review/sanitize the initial publication contents.
- [x] Publish the initial workspace and metadata-only inventory to the public GitHub repository.
- [ ] Confirm the exact product edition/modules and map the user-visible feature surface.
- [ ] Establish a clean-room evidence plan and a parity matrix (feature, observed behavior, expected result, test).
- [ ] Set up and verify the Rust toolchain; initialize the smallest useful Rust project structure.
- [ ] Select one end-to-end workflow, implement it independently, and add parity tests.
- [ ] Expand feature-by-feature, updating evidence, tests, and memory as scope grows.

## Current blockers / next actions

1. Rust is not currently available in the shell (`rustc` and `cargo` were not found).
2. Determine the exact Visual Paradigm edition/modules and map the user-visible feature surface.
3. Build the parity matrix, then choose the first vertical slice.

Update milestone checkboxes only when the stated work is verified.
