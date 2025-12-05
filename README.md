# Setup cuenv

GitHub Action to set up [cuenv](https://github.com/cuenv/cuenv) in your workflow.

## Usage

```yaml
steps:
  - uses: actions/checkout@v4
  
  - name: Setup cuenv
    uses: cuenv/setup-cuenv@v1
    with:
      # Optional: version to install (default: latest)
      version: '0.8.3' 
      # Optional: GitHub token for API rate limits (default: ${{ github.token }})
      github-token: ${{ secrets.GITHUB_TOKEN }}

  - name: Run cuenv task
    run: cuenv task build
```

## Inputs

| Input | Description | Default |
| --- | --- | --- |
| `version` | The version of cuenv to install (e.g., `0.8.3`). Use `latest` to install the latest release. | `latest` |
| `github-token` | The GitHub token used to fetch release information. | `${{ github.token }}` |

## Platform Support

- **Linux**: x86_64
- **macOS**: x86_64 (and arm64 via Rosetta)
