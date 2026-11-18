# kubara-action

GitHub Action to install and run the [Kubara](https://github.com/kubara-io/kubara) CLI (also compatible with Forgejo Actions).

## Usage

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: kubara-io/kubara-action@v0.1
    with:
      version: latest
      args: '["generate"]'
      working-directory: .
```

### Install Only

To install `kubara` and use it in later steps:

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: kubara-io/kubara-action@v0.1
    with:
      version: latest
      args: '[]'

  - name: Run CLI directly
    run: kubara --version
```

## Inputs

| Input | Default | Description |
| --- | --- | --- |
| `version` | `latest` | Kubara release version (for example `v0.18.0`) or `latest`. |
| `args` | `["generate"]` | CLI arguments as a JSON array of strings. Pass `[]` to install only. |
| `working-directory` | `.` | Directory in which to run the CLI. |

## License

Apache License 2.0
