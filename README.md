# American Cloud Go SDK

Typed Go client for the [American Cloud](https://americancloud.com) public API.

This SDK is auto-generated from the OpenAPI specification using [Fern](https://buildwithfern.com). It targets American Cloud API **`v1`** — see [`VERSIONING.md`](./VERSIONING.md) for how SDK releases track the API.

## Installation

```sh
go get github.com/American-Cloud/americancloud-sdk-go@latest
```

To pin a specific release:

```sh
go get github.com/American-Cloud/americancloud-sdk-go@v1.2.2
```

## Authentication

Every request requires **both** parts of an American Cloud API key, sent as headers:

| Header | SDK option |
|---|---|
| `X-API-Client-ID` | `option.WithAPIKey(...)` |
| `X-API-Client-Secret` | `option.WithAPIClientSecret(...)` |

Create and manage keys at **[console.americancloud.com/api-keys](https://console.americancloud.com/api-keys)**. The client secret is shown once at creation — store it securely. If lost, revoke the key and create a new one.

Each key is scoped at creation:

- **`read-only`** — `GET` endpoints only
- **`read-write`** — full access to all resource management endpoints

## Quick start

```go
package main

import (
	"context"
	"fmt"
	"log"
	"os"

	americancloud "github.com/American-Cloud/americancloud-sdk-go/client"
	"github.com/American-Cloud/americancloud-sdk-go/option"
)

func main() {
	client := americancloud.NewClient(
		option.WithAPIKey(os.Getenv("AMERICANCLOUD_API_CLIENT_ID")),
		option.WithAPIClientSecret(os.Getenv("AMERICANCLOUD_API_CLIENT_SECRET")),
	)

	vms, err := client.Vms.ListVms(context.Background(), nil)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("%+v\n", vms)
}
```

The client is namespaced by resource — `client.Vms`, `client.BlockStorage`, `client.Kubernetes`, `client.DnsZones`, etc.

## API endpoint

The SDK targets the American Cloud production API at **`https://api.americancloud.com`** by default. To override (e.g. for a self-hosted or internal environment), pass `option.WithBaseURL`:

```go
client := americancloud.NewClient(
    option.WithAPIKey("..."),
    option.WithAPIClientSecret("..."),
    option.WithBaseURL("https://your-custom-endpoint.example.com"),
)
```

## API reference

- **Full reference + code samples**: [americancloud.docs.buildwithfern.com](https://americancloud.docs.buildwithfern.com)
- **Interactive Swagger UI**: [api.americancloud.com/api-v1](https://api.americancloud.com/api-v1)

## Versioning

The SDK version **matches the API platform version it was generated from** — SDK `x.y.z` is generated from OpenAPI document `x.y.z`, so the SDK↔API mapping is one-to-one by construction:

- **Patch / minor** releases are backward-compatible — safe to upgrade.
- **Major** releases track a new API URL version (`/api/v2`) and may require code changes; check the [`CHANGELOG`](./CHANGELOG.md) first.
- The `1.x` line targets API `v1`, which remains available for at least six months after a `v2` release.
- Additive API changes (new endpoints, optional fields, enum values) ship within a version — tolerate unknown fields and new enum values gracefully.

See [`VERSIONING.md`](./VERSIONING.md) for the full policy.

## Reporting issues

Open an issue against this repository, or contact American Cloud support.

## Contributing

This SDK is generated — do not edit the source by hand. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the generation workflow.
