# PURL Registry Mappings

Registry mappings and URL patterns for all 38 official [Package URL (PURL)](https://github.com/package-url/purl-spec) types.

This dataset is published as a [Frictionless Data](https://frictionlessdata.io/) datapackage.

## Contents

### `registries.csv`

Base registry information for each PURL type.

| Field | Description |
|---|---|
| `type` | PURL type identifier (primary key) |
| `registryName` | Human-readable name of the registry |
| `baseUrl` | Base URL of the registry website |
| `hasRegistry` | Whether a central browsable registry exists |
| `requiresQualifier` | Whether PURL qualifiers are needed to resolve a URL |
| `category` | `central`, `qualifier-based`, or `no-registry` |

### `url-patterns.csv`

URL templates for generating registry links from parsed PURL components.

| Field | Description |
|---|---|
| `type` | PURL type identifier |
| `pattern` | Pattern variant (`default`, `withVersion`, `withNamespace`, ...) |
| `urlTemplate` | URL template with placeholders: `{name}`, `{namespace}`, `{version}`, `{qualifiers.*}` |
| `requiredFields` | Comma-separated list of required PURL fields |
| `note` | Implementation notes |

## Validation

The datapackage is validated on every push and pull request using the [frictionless](https://framework.frictionlessdata.io/) framework.

```sh
pip install frictionless
frictionless validate datapackage.json
```

## License

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) - Public Domain.
