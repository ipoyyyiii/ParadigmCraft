# Installed Visual Paradigm inventory

Target: `/Applications/Visual Paradigm.app` (version 18.1, macOS bundle).

- `visual-paradigm-18.1-manifest.tsv` lists each bundle directory, regular file, and symlink with a path relative to the app bundle. Regular-file sizes are recorded; symlink targets are listed but not followed.
- A `-` in the manifest means the field is not applicable.
- `visual-paradigm-18.1-jars.tsv` records regular JAR path, size, archive-entry count, class-entry count, and top-level class package roots, read from ZIP central-directory metadata only.
- No app files were copied, extracted, decompiled, or modified for this inventory. It is an index of the installed copy, not permission to reuse proprietary code or assets.
- User support data, license material, caches, and coursework project contents are deliberately excluded.

Major app areas:

| Path | Observed contents / likely analysis value |
|---|---|
| `Contents/Resources/app/lib` | Main Java archives, including `vpplatform.jar`, `vpserver.jar`, and `vpserverres.jar` |
| `Contents/Resources/app/resources` | Resource/data directories such as `dict`, `instantgenerator`, `process-canvas`, and `webdiagram` |
| `Contents/Resources/app/shapes` | Packaged shape resources; inventory only, do not reuse assets |
| `Contents/Resources/app/sde` | IDE integration files and version-specific subtrees |
| `Contents/Resources/app/ormlib` | ORM and related Java libraries |
| `Contents/Resources/app/bundled` | Bundled dependencies |
| `Contents/Resources/app/bin` | Native/helper executables for supported platforms |
| `Contents/Resources/app/scripts`, `integration`, `UserLanguage` | Launch/support scripts, integration files, and language resources |
| `Contents/Resources/jre.bundle` | Bundled Java runtime |

The package is Java-based, so Ghidra is useful only for native components. Use an appropriate Java inspection route for JAR behavior; first separate third-party dependencies from Visual Paradigm-owned packages and keep all analysis local.
