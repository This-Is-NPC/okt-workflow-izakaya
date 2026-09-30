# Izakaya workflow for Omakiten

A self-contained Omakiten workflow package for lightweight experiments with
hypothesis, development, and done checkpoints. The package includes its
settings, guards, command bindings, personas, skills, laws, templates, theme,
and notifications.

## Install

From the target project, install this checkout. A published repository can also
be installed by its catalog name or Git URL:

```sh
okt preset catalog
okt preset add /path/to/okt-workflow-izakaya
okt preset use izakaya
okt config validate
okt init --name "My project" --slug my-project
```

Add `--scope global` to `add` and `use` for a user-wide installation. Installation
captures a complete snapshot; the checkout is not needed afterward. Installing
and selecting do not execute hooks.

Omakiten stores application language preferences in its user configuration root's
`preferences.yaml`. Use `okt config language` to inspect or change them across
all projects.

## Customize

`preset.yaml` identifies this package. `config/preset.yaml` links its modules:

| File in `config/` | Contents |
| --- | --- |
| `settings.yaml` | Output, runtime options and display settings |
| `views.yaml` | Columns and visible fields |
| `events.yaml` | Event definitions and delivery |
| `hooks.yaml` | Hook bindings |
| `workflows.yaml` | Buckets, transitions and guards |
| `surfaces.yaml` | CLI, TUI, and HTTP API operation availability |
| `catalog.yaml` | Active skill and law references |
| `personas.yaml` | Persona roles and entity bindings |
| `bindings.yaml` | CLI command bindings |

Simple records use compact YAML rows; nested rules use indented blocks. Entity
bodies and the color theme live in sibling directories. Omakiten edits the
module that owns each changed value and preserves the imports.

Each workflow command is a skill in `skills/<command-name>.md`. Its `command`
frontmatter names the command, declares optional parameters, and lists immediate
related commands with `context: full` or `context: bare`. The body is the
command instruction. `config/bindings.yaml` selects its persona and supporting
context; `okt command list` and `okt command resolve <name>` read this package.

Editing the active package through Omakiten creates an independent
`izakaya-local` preset on the first change. Further edits retain that name.
`okt preset list` reports active and modified snapshots; use a full id when a
name has several revisions. The original Izakaya snapshot remains available.

## Share

```sh
okt preset export --output izakaya.md
okt preset import --file izakaya.md
okt preset use izakaya
```

The Markdown contains the whole package. Imports install without activation.
Use `okt preset --help` and each subcommand's help for scope and output flags.

## Validation

Omakiten validates the manifest, configuration schema, required references,
relative file paths, and content identity. Hook scripts are user-provided code;
installation does not inspect their implementation.
