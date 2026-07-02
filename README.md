# setup-grimoire

GitHub Action that installs the [grim](https://grimoire.rs) CLI —
Grimoire, the OCI-backed package manager for AI skills and rules — on
the runner and adds it to `PATH`. Linux, macOS, and Windows runners on
`x86_64` and `aarch64`; archives are checksum-verified.

## Usage

```yaml
steps:
  - uses: grimoire-rs/setup-grimoire@v1
  - run: grim install ghcr.io/grimoire-rs/skills/grim-usage --global
```

Pin a specific grim release:

```yaml
  - uses: grimoire-rs/setup-grimoire@v1
    with:
      version: v0.7.0
```

## Inputs

| Input | Default | Description |
|---|---|---|
| `version` | `latest` | grim release to install (`latest` or an exact `vX.Y.Z` tag) |

## Outputs

| Output | Description |
|---|---|
| `version` | The installed version as reported by `grim --version` |

## Shell installers

The same binaries install outside CI via <https://setup.grimoire.rs>:

```sh
curl --proto '=https' --tlsv1.2 -LsSf https://setup.grimoire.rs/sh | sh
```

```powershell
irm https://setup.grimoire.rs/ps1 | iex
```

## License

Apache-2.0
