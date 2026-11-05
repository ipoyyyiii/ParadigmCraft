# ParadigmCraft project memory

Updated: 2026-11-06

## Mission and baseline

- Reimplement Visual Paradigm from scratch in Rust, aspiring to 1:1 parity, then add user-requested features separately.
- Baseline installed: Visual Paradigm 18.1 at `/Applications/Visual Paradigm.app`; edition/modules are not yet confirmed.
- WordCraft (`storytold/wordcraft`) is an architectural/process reference for clean-room Rust work, not code to clone.

## Verified findings

- App bundle: about 1.0 GB; signed by Visual Paradigm International Ltd.; Java application with bundled JRE.
- Bundle inventory contains 1,727 regular files, 237 directories, and 117 symlinks. Full path/type/size inventory: `inventory/visual-paradigm-18.1-manifest.tsv`.
- There are 53 regular JAR archives. Their sizes and ZIP central-directory entry/class counts are recorded in `inventory/visual-paradigm-18.1-jars.tsv`; no archive contents were extracted or copied.
- Major areas: `Contents/Resources/app/{lib,resources,shapes,sde,ormlib,bundled,scripts,bin,integration,UserLanguage}` and `Contents/Resources/jre.bundle`.
- `lib` includes `vpplatform.jar`, `vpserver.jar`, and `vpserverres.jar`; `resources` includes dictionaries, process material, templates/data, and web-diagram resources. Inventory records paths only; assets are not copied for reuse.
- REA 6.8.0 and Ghidra 12.1.4 are connected and passed a real x86_64 analysis test. This validates native analysis tooling, not Java/JAR decompilation.
- Xcode 16.2 compiler/SDK was verified for the local REA setup without changing the machine-wide developer directory.
- Rust tooling is absent from the current shell (`rustc: command not found`, `cargo: command not found`). No Rust project has been initialized yet.
- Coursework `.vpp`/`.vpd` artifacts exist outside this workspace; only file-type metadata was checked. Names, locations, and contents are intentionally omitted from this public repo; nothing was copied.
- Local Visual Paradigm support data was excluded from the workspace inventory; preferences, logs, license data, and caches were not read.
- GitHub repo `https://github.com/ipoyyyiii/ParadigmCraft` is public. The sanitized initial workspace was pushed to `main` as commit `47dea57`; local `main` tracks `origin/main`.

## Decisions and boundaries

- Clean-room implementation only: do not copy proprietary code/assets, reuse bundled artwork/templates, or bypass licensing/access controls.
- Coursework files remain read-only and unopened unless the user explicitly approves content inspection.
- Keep app inventory and analysis notes in this workspace; do not copy the installed app bundle.
- Avoid macOS major upgrades.
- Use project-level isolation (Git, ignore rules, pinned tooling); no VM/Docker for the initial native macOS work.

## Completed

- Created `~/ParadigmCraft`, `goals.md`, project `AGENTS.md`, this memory file, and metadata-only Visual Paradigm 18.1 file/JAR manifests.
- Added a scoped continuation rule to `~/.config/opencode/AGENTS.md` so future ParadigmCraft chats load project goals/memory and keep them current.
- Added a README and `.gitignore`, initialized local Git on `main`, and configured the provided GitHub URL as `origin`.
- Removed host-specific coursework names/paths from the public project memory before the first push.
- Published the initial project files and metadata-only inventory to the public GitHub repo; no app contents or coursework files were included.

## Next

1. Confirm edition/modules and map visible features/workflows without opening coursework files.
2. Set up Rust via the official rustup workflow, then verify `rustc`/`cargo` and start the project.
3. Build the parity matrix and choose a testable first vertical slice.

## Session log

- 2026-11-06: Initial workspace and inventory created. Recorded app bundle metadata and JAR archive metadata only; no proprietary files copied, no support/license contents read, and no coursework project contents inspected.
- 2026-11-06: Set up local Git and origin. User confirmed the GitHub repo should remain public; reviewed the initial files and removed local coursework names/paths before publishing.
- 2026-11-06: Published the initial sanitized workspace to `main`; verified the remote commit and file listing.
