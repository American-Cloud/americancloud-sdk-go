# American Cloud Go SDK

Typed Go client for the [American Cloud](https://americancloud.com) public API.

This SDK is auto-generated from the OpenAPI specification using [Fern](https://buildwithfern.com). It targets American Cloud API **`v1`** — see [`VERSIONING.md`](./VERSIONING.md) for how SDK releases track the API.

![Listing regions and VMs with the American Cloud Go SDK](https://raw.githubusercontent.com/American-Cloud/americancloud-sdk-go/master/.demo/sdk-firstcall-go.gif)

## Installation

```sh
go get github.com/American-Cloud/americancloud-sdk-go@latest
```

To pin a specific release:

```sh
go get github.com/American-Cloud/americancloud-sdk-go@v1.3.0
```

## Authentication

Every request carries an American Cloud **API token** in the `Authorization: Bearer` header. Create one at **[console.americancloud.com/api-tokens](https://console.americancloud.com/api-tokens)**. The token is shown once at creation — store it securely. If lost, revoke it and create a new one.

Pass the token with `option.WithToken`, or set `AMERICANCLOUD_API_TOKEN` and omit it. A token has the permissions you chose when you created it: start with the **Read-only** preset, or choose **Full access** to create, change and delete resources. `client.Whoami.GetWhoami` returns the permissions the token has now.

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
		option.WithToken(os.Getenv("AMERICANCLOUD_API_TOKEN")),
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
    option.WithToken("..."),
    option.WithBaseURL("https://your-custom-endpoint.example.com"),
)
```

## API reference

- **Full reference + code samples**: [americancloud.com/docs/api](https://americancloud.com/docs/api)
- **Interactive Swagger UI**: [api.americancloud.com/api-v1](https://api.americancloud.com/api-v1)

## Guides

Narrative walkthroughs on the American Cloud docs site:

- [Go SDK quickstart](https://americancloud.com/docs/sdks/go) — install, authenticate, estimate cost, then create a VM, with typed errors and pagination
- [SDKs & Terraform overview](https://americancloud.com/docs/sdks/overview) — when to reach for an SDK, Terraform, or the MCP server
- [Deploy with AI](https://americancloud.com/docs/deploy-with-ai/overview) — let an AI assistant build and ship to American Cloud

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
