# Reference
## vms
<details><summary><code>client.Vms.ListVms() -> *americancloudsdkgo.ListVmsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListVmsRequest{}
client.Vms.ListVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.CreateVms(request) -> *americancloudsdkgo.CreateVMResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new VM and returns it. To preview pricing without creating anything, use `POST /compute/vms/cost-estimate` instead.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVMDto{
        Name: "my-new-vm",
        Region: "us-west-0",
        VMPackage: "standard-custom",
        VMSpecs: &americancloudsdkgo.VMSpecsDto{
            Vcpu: 2,
            MemoryMb: 2048,
            RootDiskGb: 50,
        },
        Image: "ubuntu-22.04",
        SubscriptionPeriod: americancloudsdkgo.CreateVMDtoSubscriptionPeriodHourly,
    }
client.Vms.CreateVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVMDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.GetMetricsVms(ID) -> []*americancloudsdkgo.VMMetricSampleDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetMetricsVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Hours: 24,
        SamplePeriod: americancloudsdkgo.Float64(
            10,
        ),
    }
client.Vms.GetMetricsVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**hours:** `float64` — Number of hours to look back (1-16)
    
</dd>
</dl>

<dl>
<dd>

**samplePeriod:** `*float64` — Sampling step — return every Nth data point from the raw dataset. Higher values return fewer, more spread-out points. When omitted, up to 150 points are returned.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.ResetPasswordVms(ID, request) -> *americancloudsdkgo.VMPasswordResetResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resets the VM password. You can optionally provide a custom password, or let the system generate one. The VM must be stopped for this operation. IMPORTANT: The password is only returned once - save it immediately.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ResetPasswordDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Vms.ResetPasswordVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**password:** `*string` — Custom password to set for the VM. If not provided, a random password will be generated. May contain letters, digits, and symbols only (printable ASCII, no spaces).
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.GetVms(ID) -> *americancloudsdkgo.VMResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Vms.GetVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.DeleteVms(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Vms.DeleteVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.GetCostEstimateVms(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a VM with the given specs without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVMDto{
        Name: "my-new-vm",
        Region: "us-west-0",
        VMPackage: "standard-custom",
        VMSpecs: &americancloudsdkgo.VMSpecsDto{
            Vcpu: 2,
            MemoryMb: 2048,
            RootDiskGb: 50,
        },
        Image: "ubuntu-22.04",
        SubscriptionPeriod: americancloudsdkgo.CreateVMDtoSubscriptionPeriodHourly,
    }
client.Vms.GetCostEstimateVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVMDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.PowerVms(ID) -> *americancloudsdkgo.VMPowerActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start, stop, or reboot a virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.PowerVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Action: americancloudsdkgo.PowerVmsRequestActionStart,
        Force: americancloudsdkgo.Bool(
            false,
        ),
    }
client.Vms.PowerVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**action:** `*americancloudsdkgo.PowerVmsRequestAction` — Power action to perform
    
</dd>
</dl>

<dl>
<dd>

**force:** `*bool` — Whether to force the action (applicable for stop and reboot actions)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.ScaleVms(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Scale a virtual machine to new CPU and/or memory specifications. When the VM is stopped, both scale-up and scale-down are allowed. When running, only scale-up is permitted.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ScaleVMDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Vms.ScaleVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**cpu:** `*int` — Number of virtual CPUs. Optional, but at least one of CPU or memory must be provided.
    
</dd>
</dl>

<dl>
<dd>

**memoryMb:** `*int` — Memory in MB. Optional, but at least one of CPU or memory must be provided.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.ResizeDiskVms(ID, request) -> *americancloudsdkgo.VMDiskResizeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resizes the root disk of a virtual machine. The new size must be larger than the current root disk size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ResizeVMDiskDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        SizeGb: 200,
    }
client.Vms.ResizeDiskVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**sizeGb:** `int` — The new size of the root disk in GB. Must be larger than the current root disk size.
    
</dd>
</dl>

<dl>
<dd>

**reboot:** `*bool` — Whether to automatically reboot the VM after the resize completes. Only applies when the VM is running. A reboot is required for the OS to recognize the new disk size.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.CreateConsoleVms(ID) -> *americancloudsdkgo.VMConsoleResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a console endpoint URL for accessing the VM console. Returns the console URL and optional websocket URL.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateConsoleVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Vms.CreateConsoleVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.UpdateHostnameVms(ID) -> *americancloudsdkgo.VMHostnameUpdateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the hostname of a virtual machine. The VM must be stopped and started for the change to take effect.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateHostnameVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Hostname: "my-web-server",
    }
client.Vms.UpdateHostnameVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**hostname:** `string` — The new hostname for the virtual machine
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vms.ReinstallVms(ID) -> *americancloudsdkgo.VMReinstallResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reinstalls a virtual machine from its current template or a new template. This will erase all data on the root disk.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ReinstallVmsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Image: americancloudsdkgo.String(
            "ubuntu-22.04",
        ),
    }
client.Vms.ReinstallVms(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the virtual machine
    
</dd>
</dl>

<dl>
<dd>

**image:** `*string` — Optional image label to reinstall from (uses current template if not provided)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## vm-packages
<details><summary><code>client.VMPackages.ListVMPackages() -> *americancloudsdkgo.ListVMPackagesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListVMPackagesRequest{}
client.VMPackages.ListVMPackages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VMPackages.GetVMPackages(ID) -> *americancloudsdkgo.VMPackageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetVMPackagesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VMPackages.GetVMPackages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VM package to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VMPackages.GetByLabelVMPackages(Label) -> *americancloudsdkgo.VMPackageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetByLabelVMPackagesRequest{
        Label: "standard-2-4",
    }
client.VMPackages.GetByLabelVMPackages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `string` — Label of the VM package to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## regions
<details><summary><code>client.Regions.ListRegions() -> *americancloudsdkgo.ListRegionsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListRegionsRequest{}
client.Regions.ListRegions(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Regions.GetRegions(ID) -> *americancloudsdkgo.RegionDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetRegionsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Regions.GetRegions(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the region to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Regions.GetByLabelRegions(Label) -> *americancloudsdkgo.RegionDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetByLabelRegionsRequest{
        Label: "sjc0",
    }
client.Regions.GetByLabelRegions(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `string` — Label of the region to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## images
<details><summary><code>client.Images.ListImages() -> *americancloudsdkgo.ListImagesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListImagesRequest{}
client.Images.ListImages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**os:** `*string` — Filter images by operating system
    
</dd>
</dl>

<dl>
<dd>

**version:** `*string` — Filter images by OS version (used together with os)
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Images.GetImages(ID) -> *americancloudsdkgo.ImageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetImagesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Images.GetImages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the image to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Images.GetByLabelImages(Label) -> *americancloudsdkgo.ImageDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetByLabelImagesRequest{
        Label: "ubuntu-22.04",
    }
client.Images.GetByLabelImages(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**label:** `string` — Label of the image to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## isolated-networks
<details><summary><code>client.IsolatedNetworks.ListIsolatedNetworks() -> *americancloudsdkgo.ListIsolatedNetworksResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListIsolatedNetworksRequest{}
client.IsolatedNetworks.ListIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.IsolatedNetworks.CreateIsolatedNetworks(request) -> *americancloudsdkgo.IsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateIsolatedNetworkDto{
        Name: "production-network",
        Region: "sjc0",
    }
client.IsolatedNetworks.CreateIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Human-readable name for the network.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — Free-form description of the network.
    
</dd>
</dl>

<dl>
<dd>

**region:** `string` — Region the network will be created in. References a region label from /v1/compute/regions.
    
</dd>
</dl>

<dl>
<dd>

**netmask:** `*string` — Network netmask.
    
</dd>
</dl>

<dl>
<dd>

**gateway:** `*string` — Network gateway IP.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.IsolatedNetworks.GetIsolatedNetworks(ID) -> *americancloudsdkgo.DetailedIsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetIsolatedNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.IsolatedNetworks.GetIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the isolated network
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.IsolatedNetworks.UpdateIsolatedNetworks(ID, request) -> *americancloudsdkgo.IsolatedNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateIsolatedNetworkDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.IsolatedNetworks.UpdateIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the isolated network to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — New name for the network.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — New description for the network.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.IsolatedNetworks.DeleteIsolatedNetworks(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteIsolatedNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.IsolatedNetworks.DeleteIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the isolated network to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.IsolatedNetworks.RestartIsolatedNetworks(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.RestartIsolatedNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.IsolatedNetworks.RestartIsolatedNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the isolated network to restart
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## vpc-networks
<details><summary><code>client.VpcNetworks.ListVpcNetworks() -> *americancloudsdkgo.ListVpcNetworksResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListVpcNetworksRequest{}
client.VpcNetworks.ListVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.CreateVpcNetworks(request) -> *americancloudsdkgo.DetailedVpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new VPC. To preview pricing without creating anything, use POST /networks/vpc/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVpcNetworkDto{
        Name: "production-vpc",
        Region: "sjc0",
        Cidr: "10.0.0.0/16",
    }
client.VpcNetworks.CreateVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVpcNetworkDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.GetVpcNetworks(ID) -> *americancloudsdkgo.DetailedVpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.GetVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC to get
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.UpdateVpcNetworks(ID, request) -> *americancloudsdkgo.VpcNetworkResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateVpcNetworkDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.UpdateVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — New name for the VPC.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — New description for the VPC.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.DeleteVpcNetworks(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.DeleteVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.GetCostEstimateVpcNetworks(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a VPC with the given configuration without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVpcNetworkDto{
        Name: "production-vpc",
        Region: "sjc0",
        Cidr: "10.0.0.0/16",
    }
client.VpcNetworks.GetCostEstimateVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVpcNetworkDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.CreateTierVpcNetworks(request) -> *americancloudsdkgo.VpcTierResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVpcTierDto{
        Name: "web-tier",
        VpcID: "123e4567-e89b-12d3-a456-426614174000",
        Gateway: "10.0.0.1",
        Netmask: "255.255.255.0",
    }
client.VpcNetworks.CreateTierVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Human-readable name for the network tier.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — Free-form description of the tier.
    
</dd>
</dl>

<dl>
<dd>

**vpcID:** `string` — Identifier of the parent VPC the tier belongs to.
    
</dd>
</dl>

<dl>
<dd>

**gateway:** `string` — Network gateway IP for the tier.
    
</dd>
</dl>

<dl>
<dd>

**netmask:** `string` — Network netmask for the tier.
    
</dd>
</dl>

<dl>
<dd>

**aclId:** `*string` — Identifier of the ACL to apply to the tier.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.GetTierVpcNetworks(ID, TierID) -> *americancloudsdkgo.VpcTierDetailResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single network tier of a VPC.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetTierVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        TierID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.GetTierVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tierID:** `string` — ID of the network tier
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.UpdateTierVpcNetworks(ID, TierID, request) -> *americancloudsdkgo.VpcTierDetailResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the name and/or description of a network tier.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateVpcTierDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        TierID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.UpdateTierVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tierID:** `string` — ID of the network tier to update
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — New name for the tier.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — New description for the tier.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.DeleteTierVpcNetworks(ID, TierID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a single network tier from a VPC, leaving the rest of the VPC intact.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteTierVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        TierID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.DeleteTierVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tierID:** `string` — ID of the network tier to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.RestartTierVpcNetworks(ID, TierID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Restarts a single network tier of a VPC.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.RestartTierVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        TierID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.RestartTierVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC that contains the tier
    
</dd>
</dl>

<dl>
<dd>

**tierID:** `string` — ID of the network tier to restart
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.VpcNetworks.RestartVpcNetworks(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.RestartVpcNetworksRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.VpcNetworks.RestartVpcNetworks(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the VPC to restart
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## public-ips
<details><summary><code>client.PublicIps.ListPublicIps() -> *americancloudsdkgo.ListPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListPublicIpsRequest{}
client.PublicIps.ListPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.ReservePublicIps(request) -> *americancloudsdkgo.PublicIPResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reserves a public IP address and associates it with the specified virtual machine. The region is automatically inferred from the virtual machine. To preview pricing without reserving anything, use POST /networks/public-ip/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ReservePublicIPDto{
        Region: "us-west-0",
    }
client.PublicIps.ReservePublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**networkID:** `*string` — Identifier of the isolated network the public IP should attach to.
    
</dd>
</dl>

<dl>
<dd>

**vpcID:** `*string` — Identifier of the VPC the public IP should attach to.
    
</dd>
</dl>

<dl>
<dd>

**region:** `string` — Label of the region where the IP address should be allocated
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.ListByIsolatedNetworkPublicIps(IsolatedNetworkID) -> *americancloudsdkgo.ListByIsolatedNetworkPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListByIsolatedNetworkPublicIpsRequest{
        IsolatedNetworkID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.ListByIsolatedNetworkPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**isolatedNetworkID:** `string` — ID of the isolated network
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.ListByVpcPublicIps(VpcID) -> *americancloudsdkgo.ListByVpcPublicIpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListByVpcPublicIpsRequest{
        VpcID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.ListByVpcPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vpcID:** `string` — ID of the VPC
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.GetPublicIps(ID) -> *americancloudsdkgo.PublicIPResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetPublicIpsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.GetPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the public IP address
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.ReleasePublicIps(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ReleasePublicIpsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.ReleasePublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the public IP address to release
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.GetCostEstimatePublicIps() -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost of reserving a public IP address without reserving one.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.PublicIps.GetCostEstimatePublicIps(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.ChangeSourceNatIPPublicIps(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Changes the source NAT IP for the specified public IP address
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ChangeSourceNatIPDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        NetworkID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.ChangeSourceNatIPPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the public IP address to change
    
</dd>
</dl>

<dl>
<dd>

**networkID:** `string` — Identifier of the network whose source NAT IP should be replaced.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.EnableStaticNatPublicIps(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Enables static NAT for the specified public IP by associating it with a virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.EnableStaticNatDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        VirtualMachineID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.EnableStaticNatPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**virtualMachineID:** `string` — Identifier of the virtual machine to associate with this public IP.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PublicIps.DisableStaticNatPublicIps(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Disables static NAT for the specified public IP address
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DisableStaticNatPublicIpsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PublicIps.DisableStaticNatPublicIps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the public IP address
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## firewall-rules
<details><summary><code>client.FirewallRules.ListFirewallRules(IpId) -> *americancloudsdkgo.ListFirewallRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListFirewallRulesRequest{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
    }
client.FirewallRules.ListFirewallRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.FirewallRules.CreateFirewallRules(IpId, request) -> *americancloudsdkgo.FirewallRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateFirewallRuleDto{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
        Protocol: americancloudsdkgo.CreateFirewallRuleDtoProtocolTCP,
        SourceCidrList: "10.0.0.0/24",
    }
client.FirewallRules.CreateFirewallRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `*americancloudsdkgo.CreateFirewallRuleDtoProtocol` — Protocol the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**startPort:** `*int` — Start of the port range (1-65535). Required for TCP and UDP.
    
</dd>
</dl>

<dl>
<dd>

**endPort:** `*int` — End of the port range (1-65535). Must be greater than or equal to `startPort`.
    
</dd>
</dl>

<dl>
<dd>

**sourceCidrList:** `string` — Source CIDR allowed to reach the rule target.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.CreateFirewallRuleDtoType` — Direction of traffic this rule applies to.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.FirewallRules.DeleteFirewallRules(RuleID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteFirewallRulesRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.FirewallRules.DeleteFirewallRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the firewall rule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## port-forwarding
<details><summary><code>client.PortForwarding.ListPortForwarding(IpId) -> *americancloudsdkgo.ListPortForwardingResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListPortForwardingRequest{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PortForwarding.ListPortForwarding(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PortForwarding.CreatePortForwarding(IpId, request) -> *americancloudsdkgo.PortForwardingRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreatePortForwardingRuleDto{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
        PrivatePort: "80",
        PublicPort: "8080",
        Protocol: americancloudsdkgo.CreatePortForwardingRuleDtoProtocolTCP,
        VmId: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PortForwarding.CreatePortForwarding(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**privatePort:** `string` — Port on the VM that traffic is forwarded to. Must be 1-65535.
    
</dd>
</dl>

<dl>
<dd>

**publicPort:** `string` — Port on the public IP that receives the inbound traffic. Must be 1-65535.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `*americancloudsdkgo.CreatePortForwardingRuleDtoProtocol` — Protocol the forwarding rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**vmId:** `string` — Identifier of the VM the forwarded traffic is delivered to.
    
</dd>
</dl>

<dl>
<dd>

**openFirewall:** `*string` — When `true`, automatically creates a matching firewall rule alongside the port forwarding rule.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.PortForwarding.DeletePortForwarding(RuleID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeletePortForwardingRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.PortForwarding.DeletePortForwarding(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the port forwarding rule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## load-balancer-rules
<details><summary><code>client.LoadBalancerRules.ListLoadBalancerRules(IpId) -> *americancloudsdkgo.ListLoadBalancerRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListLoadBalancerRulesRequest{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
    }
client.LoadBalancerRules.ListLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.CreateLoadBalancerRules(IpId, request) -> *americancloudsdkgo.LoadBalancerRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateLoadBalancerRuleDto{
        IpId: "123e4567-e89b-12d3-a456-426614174000",
        Name: "web-lb",
        Algorithm: americancloudsdkgo.CreateLoadBalancerRuleDtoAlgorithmRoundrobin,
        PublicPort: "80",
        PrivatePort: "8080",
    }
client.LoadBalancerRules.CreateLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ipId:** `string` — ID of the public IP address
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` — Name of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**algorithm:** `*americancloudsdkgo.CreateLoadBalancerRuleDtoAlgorithm` — Algorithm used to distribute traffic across the backend VMs.
    
</dd>
</dl>

<dl>
<dd>

**publicPort:** `string` — Public port the load balancer listens on.
    
</dd>
</dl>

<dl>
<dd>

**privatePort:** `string` — Port on the backend VMs that traffic is forwarded to.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `*americancloudsdkgo.CreateLoadBalancerRuleDtoProtocol` — Protocol the load balancer accepts.
    
</dd>
</dl>

<dl>
<dd>

**sourceCidrList:** `*string` — Source CIDR allowed to reach the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — Free-form description of the rule.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.UpdateLoadBalancerRules(RuleID, request) -> *americancloudsdkgo.LoadBalancerRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateLoadBalancerRuleDto{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.LoadBalancerRules.UpdateLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — New name for the rule.
    
</dd>
</dl>

<dl>
<dd>

**algorithm:** `*americancloudsdkgo.UpdateLoadBalancerRuleDtoAlgorithm` — New algorithm used to distribute traffic.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — New description for the rule.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `*string` — New protocol the load balancer accepts.
    
</dd>
</dl>

<dl>
<dd>

**sourceCidrList:** `*string` — New source CIDR allowed to reach the load balancer.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.DeleteLoadBalancerRules(RuleID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteLoadBalancerRulesRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.LoadBalancerRules.DeleteLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the load balancer rule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.ListInstancesLoadBalancerRules(RuleID) -> *americancloudsdkgo.ListInstancesLoadBalancerRulesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns assigned VMs by default. Set applied=false to list VMs available for assignment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListInstancesLoadBalancerRulesRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.LoadBalancerRules.ListInstancesLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**applied:** `*bool` — If true (default), returns assigned VMs. If false, returns VMs available for assignment.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.AssignVmsLoadBalancerRules(RuleID, request) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.AssignVmsLoadBalancerRulesRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
        Body: &americancloudsdkgo.AssignVmsToLoadBalancerRuleDto{
            VmIds: []string{
                "123e4567-e89b-12d3-a456-426614174000",
            },
        },
    }
client.LoadBalancerRules.AssignVmsLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**request:** `*americancloudsdkgo.AssignVmsToLoadBalancerRuleDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LoadBalancerRules.RemoveVmsLoadBalancerRules(RuleID, request) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.RemoveVmsLoadBalancerRulesRequest{
        RuleID: "123e4567-e89b-12d3-a456-426614174000",
        Body: &americancloudsdkgo.AssignVmsToLoadBalancerRuleDto{
            VmIds: []string{
                "123e4567-e89b-12d3-a456-426614174000",
            },
        },
    }
client.LoadBalancerRules.RemoveVmsLoadBalancerRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ruleID:** `string` — ID of the load balancer rule
    
</dd>
</dl>

<dl>
<dd>

**request:** `*americancloudsdkgo.AssignVmsToLoadBalancerRuleDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## egress-rules
<details><summary><code>client.EgressRules.ListEgressRules() -> *americancloudsdkgo.ListEgressRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListEgressRulesRequest{}
client.EgressRules.ListEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.EgressRules.CreateEgressRules(request) -> *americancloudsdkgo.EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateEgressRuleDto{
        Protocol: "TCP",
    }
client.EgressRules.CreateEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**protocol:** `string` — Protocol the rule applies to. One of `TCP`, `UDP`, `ICMP`, or `ALL`.
    
</dd>
</dl>

<dl>
<dd>

**startPort:** `*int` — Start of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**endPort:** `*int` — End of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**sourceCidrList:** `*string` — Source CIDR within the guest network CIDR. Omit to allow the entire network.
    
</dd>
</dl>

<dl>
<dd>

**destCidrList:** `*string` — Destination CIDR the traffic is allowed to reach. Defaults to `0.0.0.0/0`.
    
</dd>
</dl>

<dl>
<dd>

**networkID:** `*string` — Identifier of the network the egress rule applies to.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.EgressRules.ListByNetworkEgressRules(NetworkID) -> *americancloudsdkgo.ListByNetworkEgressRulesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListByNetworkEgressRulesRequest{
        NetworkID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.EgressRules.ListByNetworkEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**networkID:** `string` — ID of the network
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.EgressRules.GetEgressRules(ID) -> *americancloudsdkgo.EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetEgressRulesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.EgressRules.GetEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the egress rule
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.EgressRules.UpdateEgressRules(ID, request) -> *americancloudsdkgo.EgressRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateEgressRuleDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.EgressRules.UpdateEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the egress rule
    
</dd>
</dl>

<dl>
<dd>

**sourceCidrList:** `*string` — Source CIDR within the guest network CIDR.
    
</dd>
</dl>

<dl>
<dd>

**destCidrList:** `*string` — Destination CIDR the traffic is allowed to reach.
    
</dd>
</dl>

<dl>
<dd>

**startPort:** `*int` — Start of the port range the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**endPort:** `*int` — End of the port range the rule applies to.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.EgressRules.DeleteEgressRules(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteEgressRulesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.EgressRules.DeleteEgressRules(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the egress rule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## network-acls
<details><summary><code>client.NetworkACLs.ListListsNetworkACLs() -> *americancloudsdkgo.ListListsNetworkACLsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListListsNetworkACLsRequest{}
client.NetworkACLs.ListListsNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.CreateListNetworkACLs(request) -> *americancloudsdkgo.NetworkACLListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateNetworkACLListDto{
        Name: "web-tier-acl",
        VpcID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.CreateListNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Human-readable name for the ACL list.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` — Free-form description of the ACL list.
    
</dd>
</dl>

<dl>
<dd>

**vpcID:** `string` — Identifier of the parent VPC the ACL list belongs to.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.ListListsByVpcNetworkACLs(VpcID) -> *americancloudsdkgo.ListListsByVpcNetworkACLsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListListsByVpcNetworkACLsRequest{
        VpcID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.ListListsByVpcNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vpcID:** `string` — ID of the VPC
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.GetListNetworkACLs(ID) -> *americancloudsdkgo.NetworkACLListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetListNetworkACLsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.GetListNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Network ACL List
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.DeleteListNetworkACLs(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteListNetworkACLsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.DeleteListNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Network ACL List to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.ListRulesNetworkACLs(ListID) -> *americancloudsdkgo.ListRulesNetworkACLsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListRulesNetworkACLsRequest{
        ListID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.ListRulesNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listID:** `string` — ID of the Network ACL List
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.CreateRuleNetworkACLs(ListID, request) -> *americancloudsdkgo.NetworkACLRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateNetworkACLRuleDto{
        ListID: "123e4567-e89b-12d3-a456-426614174000",
        CidrList: "0.0.0.0/0",
        Protocol: "TCP",
        Action: "Allow",
        TrafficType: "Ingress",
    }
client.NetworkACLs.CreateRuleNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listID:** `string` — ID of the Network ACL List
    
</dd>
</dl>

<dl>
<dd>

**cidrList:** `string` — Remote CIDR — source CIDR for `Ingress` rules, destination CIDR for `Egress` rules.
    
</dd>
</dl>

<dl>
<dd>

**protocol:** `string` — Protocol the rule applies to. One of `TCP`, `UDP`, `ICMP`, or `ALL`.
    
</dd>
</dl>

<dl>
<dd>

**action:** `string` — Whether to allow or deny matching traffic.
    
</dd>
</dl>

<dl>
<dd>

**trafficType:** `string` — Direction of traffic the rule applies to.
    
</dd>
</dl>

<dl>
<dd>

**number:** `*string` — Rule number (1-1000). Unique within the ACL list and determines evaluation order.
    
</dd>
</dl>

<dl>
<dd>

**startPort:** `*int` — Start of the port range. Used for `TCP` and `UDP` protocols.
    
</dd>
</dl>

<dl>
<dd>

**endPort:** `*int` — End of the port range. Used for `TCP` and `UDP` protocols.
    
</dd>
</dl>

<dl>
<dd>

**icmpType:** `*string` — ICMP message type. Used for the `ICMP` protocol.
    
</dd>
</dl>

<dl>
<dd>

**icmpCode:** `*string` — ICMP message code. Used for the `ICMP` protocol.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.GetRuleNetworkACLs(ID) -> *americancloudsdkgo.NetworkACLRuleResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetRuleNetworkACLsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.GetRuleNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Network ACL Rule
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.DeleteRuleNetworkACLs(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteRuleNetworkACLsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.DeleteRuleNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Network ACL Rule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.NetworkACLs.ReplaceListNetworkACLs(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Replaces the ACL List for a network with the specified ACL List
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ReplaceNetworkACLListDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        NetworkID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.NetworkACLs.ReplaceListNetworkACLs(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Network ACL List to apply
    
</dd>
</dl>

<dl>
<dd>

**networkID:** `string` — Identifier of the network the ACL list should be applied to.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## databases
<details><summary><code>client.Databases.ListDatabases() -> *americancloudsdkgo.ListDatabasesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all database clusters for the authenticated account.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDatabasesRequest{}
client.Databases.ListDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `*string` — Filter by infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.CreateDatabases(request) -> *americancloudsdkgo.CreateClusterResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new managed database cluster for the authenticated account.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateDatabaseClusterDto{
        DbClusterName: "production-db",
        RegionID: "123e4567-e89b-12d3-a456-426614174000",
        Tier: "standard",
        AvailabilityType: americancloudsdkgo.CreateDatabaseClusterDtoAvailabilityTypeSingleNode,
    }
client.Databases.CreateDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `*string` — Identifier of an existing infrastructure cluster to deploy the database on. Omit to provision new infrastructure.
    
</dd>
</dl>

<dl>
<dd>

**dbClusterName:** `string` — Database cluster name. Must comply with Kubernetes naming rules.
    
</dd>
</dl>

<dl>
<dd>

**sshKey:** `*string` — SSH key authorized for access to the cluster. Required when creating a new cluster; omit only when deploying onto an existing `userClusterId`.
    
</dd>
</dl>

<dl>
<dd>

**offeringID:** `*string` — Identifier of the database offering to use.
    
</dd>
</dl>

<dl>
<dd>

**offeringName:** `*string` — Name of the database offering. Alternative to `offeringId` for selecting an offering.
    
</dd>
</dl>

<dl>
<dd>

**regionID:** `string` — Identifier of the region the cluster will run in.
    
</dd>
</dl>

<dl>
<dd>

**tier:** `string` — Infrastructure tier that determines per-node CPU and memory.
    
</dd>
</dl>

<dl>
<dd>

**availabilityType:** `*americancloudsdkgo.CreateDatabaseClusterDtoAvailabilityType` — Availability mode for the cluster.
    
</dd>
</dl>

<dl>
<dd>

**storageGb:** `*int` — Storage capacity allocated to the cluster, in gigabytes.
    
</dd>
</dl>

<dl>
<dd>

**networkConfig:** `*americancloudsdkgo.CreateDatabaseClusterDtoNetworkConfig` — Network the cluster will attach to. Required when creating a new cluster; omit only when deploying onto an existing `userClusterId`.
    
</dd>
</dl>

<dl>
<dd>

**restore:** `*americancloudsdkgo.CreateClusterRestoreDto` — Restore-from-backup configuration. Provide to bootstrap the new cluster from an existing backup.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.GetCostEstimateDatabases(OfferingID) -> *americancloudsdkgo.DbsCostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated monthly cost for deploying a database. If user_cluster_id is provided, calculates the marginal cost on an existing cluster.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetCostEstimateDatabasesRequest{
        OfferingID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.GetCostEstimateDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offeringID:** `string` — Database offering ID
    
</dd>
</dl>

<dl>
<dd>

**userClusterID:** `*string` — Existing infrastructure cluster ID for marginal cost calculation
    
</dd>
</dl>

<dl>
<dd>

**availabilityType:** `*string` — Availability type: "single-node" or "data-redundancy"
    
</dd>
</dl>

<dl>
<dd>

**storageGb:** `*string` — Custom storage size in GB
    
</dd>
</dl>

<dl>
<dd>

**tier:** `*string` — Infrastructure tier: "standard" or "premium"
    
</dd>
</dl>

<dl>
<dd>

**dbClusterID:** `*string` — Database cluster ID for resize cost estimates (replaces workload instead of adding)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.GetDatabases(ClusterID) -> *americancloudsdkgo.ClusterDetailResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.GetDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.DeleteDatabases(ClusterID) -> *americancloudsdkgo.ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a database cluster. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.DeleteDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.GetStatusDatabases(ClusterID) -> *americancloudsdkgo.ClusterStatusResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetStatusDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.GetStatusDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.GetConnectionDatabases(ClusterID) -> *americancloudsdkgo.ConnectionInfoResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns connection details for the database cluster.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetConnectionDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        IncludePassword: "includePassword",
    }
client.Databases.GetConnectionDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**includePassword:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.GetOperationsDatabases(ClusterID) -> *americancloudsdkgo.RecentOperationsResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetOperationsDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.GetOperationsDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.StartDatabases(ClusterID) -> *americancloudsdkgo.ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.StartDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.StartDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.StopDatabases(ClusterID) -> *americancloudsdkgo.ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.StopDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.StopDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.ResizeDatabases(ClusterID, request) -> *americancloudsdkgo.ClusterActionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Changes the database cluster to a different offering or storage size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ResizeDatabaseClusterDto{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        OfferingID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Databases.ResizeDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**offeringID:** `string` — Identifier of the target database offering to resize to.
    
</dd>
</dl>

<dl>
<dd>

**storageGb:** `*int` — New storage capacity for the cluster, in gigabytes.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.ModifyLoadBalancerDatabases(ClusterID, Type, request) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ModifyLoadBalancerRequestDto{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        Type: americancloudsdkgo.ModifyLoadBalancerDatabasesRequestTypePublic,
    }
client.Databases.ModifyLoadBalancerDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.ModifyLoadBalancerDatabasesRequestType` — Load balancer type
    
</dd>
</dl>

<dl>
<dd>

**cidr:** `*string` — CIDR range allowed to reach the load balancer.
    
</dd>
</dl>

<dl>
<dd>

**loadBalancerIP:** `*string` — Pre-allocated private IP address for the load balancer.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Databases.DeleteLoadBalancerDatabases(ClusterID, Type) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteLoadBalancerDatabasesRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        Type: americancloudsdkgo.DeleteLoadBalancerDatabasesRequestTypePublic,
    }
client.Databases.DeleteLoadBalancerDatabases(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.DeleteLoadBalancerDatabasesRequestType` — Load balancer type
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-backups
<details><summary><code>client.DatabaseBackups.SetActiveRepoDatabaseBackups(ClusterID, request) -> *americancloudsdkgo.BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.SetActiveBackupRepoRequestDto{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        RepoName: "primary-backup-repo",
    }
client.DatabaseBackups.SetActiveRepoDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repoName:** `string` — Name of the backup repository to set as active.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.ListDatabaseBackups(ClusterID) -> *americancloudsdkgo.BackupListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseBackups.ListDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.TriggerDatabaseBackups(ClusterID, request) -> *americancloudsdkgo.BackupTriggerResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.TriggerBackupRequestDto{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        BackupMethod: americancloudsdkgo.TriggerBackupRequestDtoBackupMethodXtrabackup,
        BackupPolicyName: "default-backup-policy",
        BackupName: "manual-2026-05-29",
        RetentionPeriod: "30d",
        DeletionPolicy: americancloudsdkgo.TriggerBackupRequestDtoDeletionPolicyDelete,
    }
client.DatabaseBackups.TriggerDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backupMethod:** `*americancloudsdkgo.TriggerBackupRequestDtoBackupMethod` — Backup method to use for this run.
    
</dd>
</dl>

<dl>
<dd>

**backupPolicyName:** `string` — Backup policy that governs this run.
    
</dd>
</dl>

<dl>
<dd>

**backupName:** `string` — Name to assign to the resulting backup artifact.
    
</dd>
</dl>

<dl>
<dd>

**retentionPeriod:** `string` — How long to keep the backup. Number followed by `d` (days), `h` (hours), or `m` (minutes).
    
</dd>
</dl>

<dl>
<dd>

**deletionPolicy:** `*americancloudsdkgo.TriggerBackupRequestDtoDeletionPolicy` — Action to take on the backup artifact when the policy is removed.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.GetConfigDatabaseBackups(ClusterID) -> *americancloudsdkgo.BackupClusterConfigResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetConfigDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseBackups.GetConfigDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.UpdateConfigDatabaseBackups(ClusterID, request) -> *americancloudsdkgo.BackupConfigUpdateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Enable or disable encryption of this cluster’s backups. When enabling, provide a passphrase; keep it safe, as it is required to restore the resulting backups.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateBackupConfigRequestDto{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        EncryptionEnabled: true,
    }
client.DatabaseBackups.UpdateConfigDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**encryptionEnabled:** `bool` — Whether backups for this cluster should be encrypted at rest. When enabled, backups are encrypted with AES-256-CFB.
    
</dd>
</dl>

<dl>
<dd>

**passphrase:** `*string` — Passphrase used to encrypt backups. Required when enabling encryption. Must be 12–256 printable ASCII characters (letters, digits, symbols) with no spaces. Store it securely — it is required to restore encrypted backups and cannot be recovered if lost.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.GetScheduleDatabaseBackups(ClusterID) -> *americancloudsdkgo.BackupScheduleListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetScheduleDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseBackups.GetScheduleDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**scheduleName:** `*string` — Filter by schedule name
    
</dd>
</dl>

<dl>
<dd>

**backupPolicyName:** `*string` — Filter by backup policy name
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.CreateScheduleDatabaseBackups(ClusterID, request) -> *americancloudsdkgo.BackupRepoSetupResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateScheduleDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        Body: &americancloudsdkgo.ModifyBackupScheduleRequestDto{
            ScheduleName: "production-backups",
            BackupPolicyName: "default-backup-policy",
            Schedules: []*americancloudsdkgo.BackupScheduleItemDto{
                &americancloudsdkgo.BackupScheduleItemDto{
                    Name: "nightly-full",
                    BackupMethod: americancloudsdkgo.BackupScheduleItemDtoBackupMethodXtrabackup,
                    CronExpression: "0 3 * * *",
                },
            },
            PitrEnabled: false,
        },
    }
client.DatabaseBackups.CreateScheduleDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*americancloudsdkgo.ModifyBackupScheduleRequestDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.UpdateScheduleDatabaseBackups(ClusterID, request) -> *americancloudsdkgo.BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateScheduleDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        Body: &americancloudsdkgo.ModifyBackupScheduleRequestDto{
            ScheduleName: "production-backups",
            BackupPolicyName: "default-backup-policy",
            Schedules: []*americancloudsdkgo.BackupScheduleItemDto{
                &americancloudsdkgo.BackupScheduleItemDto{
                    Name: "nightly-full",
                    BackupMethod: americancloudsdkgo.BackupScheduleItemDtoBackupMethodXtrabackup,
                    CronExpression: "0 3 * * *",
                },
            },
            PitrEnabled: false,
        },
    }
client.DatabaseBackups.UpdateScheduleDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**request:** `*americancloudsdkgo.ModifyBackupScheduleRequestDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.DeleteScheduleDatabaseBackups(ClusterID) -> *americancloudsdkgo.BackupRepoDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteScheduleDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        ScheduleName: "schedule_name",
    }
client.DatabaseBackups.DeleteScheduleDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**scheduleName:** `string` — Name of the backup schedule to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.GetPolicyDatabaseBackups(ClusterID) -> *americancloudsdkgo.BackupPolicyListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetPolicyDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseBackups.GetPolicyDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**policyName:** `*string` — Filter by policy name
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.GetDatabaseBackups(ClusterID, BackupName) -> *americancloudsdkgo.BackupDetailsResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        BackupName: "nightly-2026-05-28",
    }
client.DatabaseBackups.GetDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backupName:** `string` — Backup name
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseBackups.DeleteDatabaseBackups(ClusterID, BackupName) -> *americancloudsdkgo.BackupDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteDatabaseBackupsRequest{
        ClusterID: "123e4567-e89b-12d3-a456-426614174000",
        BackupName: "nightly-2026-05-28",
    }
client.DatabaseBackups.DeleteDatabaseBackups(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clusterID:** `string` — Database cluster ID
    
</dd>
</dl>

<dl>
<dd>

**backupName:** `string` — Backup name
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-offerings
<details><summary><code>client.DatabaseOfferings.ListDatabaseOfferings() -> *americancloudsdkgo.ListDatabaseOfferingsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all active database offerings. Optionally filter by database type.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDatabaseOfferingsRequest{}
client.DatabaseOfferings.ListDatabaseOfferings(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.ListDatabaseOfferingsRequestType` — Filter by database type
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseOfferings.GetDatabaseOfferings(OfferingID) -> *americancloudsdkgo.DatabaseOfferingResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetDatabaseOfferingsRequest{
        OfferingID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseOfferings.GetDatabaseOfferings(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offeringID:** `string` — Database offering ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-regions
<details><summary><code>client.DatabaseRegions.ListDatabaseRegions() -> *americancloudsdkgo.DbaasRegionsResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all regions with their available infrastructure tiers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.DatabaseRegions.ListDatabaseRegions(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-infrastructure
<details><summary><code>client.DatabaseInfrastructure.ListDatabaseInfrastructure() -> *americancloudsdkgo.ListDatabaseInfrastructureResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all infrastructure clusters for the authenticated account with their associated database clusters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDatabaseInfrastructureRequest{}
client.DatabaseInfrastructure.ListDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.GetDatabaseInfrastructure(UserClusterID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetDatabaseInfrastructureRequest{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseInfrastructure.GetDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.ListBackupReposDatabaseInfrastructure(UserClusterID) -> *americancloudsdkgo.BackupRepoListResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListBackupReposDatabaseInfrastructureRequest{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseInfrastructure.ListBackupReposDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.CreateBackupRepoDatabaseInfrastructure(UserClusterID, request) -> *americancloudsdkgo.BackupRepoSetupResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.SetupBackupRepoRequestDto{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
        RepoName: "primary-backup-repo",
        Bucket: "my-storage-bucket",
        Endpoint: "s3.example.com",
        AccessKeyID: "AKIAIOSFODNN7EXAMPLE",
        AccessKeySecret: "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
    }
client.DatabaseInfrastructure.CreateBackupRepoDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repoName:** `string` — Name for the backup repository.
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `string` — Name of the S3 bucket backups are stored in. Provide the bucket name only — no path or account/tenant prefix.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `string` — Hostname of your S3-compatible endpoint (for example, "s3.example.com"), optionally with a port. Provide the host only — connections always use HTTPS.
    
</dd>
</dl>

<dl>
<dd>

**accessKeyID:** `string` — S3 access key identifier with access to the bucket.
    
</dd>
</dl>

<dl>
<dd>

**accessKeySecret:** `string` — S3 secret key paired with the access key.
    
</dd>
</dl>

<dl>
<dd>

**pathPrefix:** `*string` — Optional key prefix to store backups under, inside the bucket.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.UpdateBackupRepoDatabaseInfrastructure(UserClusterID, request) -> *americancloudsdkgo.BackupRepoUpdateResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateBackupRepoRequestDto{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
        RepoName: "primary-backup-repo",
        Bucket: "my-storage-bucket",
        Endpoint: "s3.example.com",
        AccessKeyID: "AKIAIOSFODNN7EXAMPLE",
        AccessKeySecret: "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
    }
client.DatabaseInfrastructure.UpdateBackupRepoDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repoName:** `string` — Name for the backup repository.
    
</dd>
</dl>

<dl>
<dd>

**bucket:** `string` — Name of the S3 bucket backups are stored in. Provide the bucket name only — no path or account/tenant prefix.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `string` — Hostname of your S3-compatible endpoint (for example, "s3.example.com"), optionally with a port. Provide the host only — connections always use HTTPS.
    
</dd>
</dl>

<dl>
<dd>

**accessKeyID:** `string` — S3 access key identifier with access to the bucket.
    
</dd>
</dl>

<dl>
<dd>

**accessKeySecret:** `string` — S3 secret key paired with the access key.
    
</dd>
</dl>

<dl>
<dd>

**pathPrefix:** `*string` — Optional key prefix to store backups under, inside the bucket.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.GetBackupRepoDatabaseInfrastructure(UserClusterID, RepoName) -> *americancloudsdkgo.BackupRepoStatusResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetBackupRepoDatabaseInfrastructureRequest{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
        RepoName: "primary-backup-repo",
    }
client.DatabaseInfrastructure.GetBackupRepoDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repoName:** `string` — Backup repository name
    
</dd>
</dl>

<dl>
<dd>

**includeCredentials:** `*string` — Include repository credentials in response (default: false)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DatabaseInfrastructure.DeleteBackupRepoDatabaseInfrastructure(UserClusterID, RepoName) -> *americancloudsdkgo.BackupRepoDeleteResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteBackupRepoDatabaseInfrastructureRequest{
        UserClusterID: "123e4567-e89b-12d3-a456-426614174000",
        RepoName: "primary-backup-repo",
    }
client.DatabaseInfrastructure.DeleteBackupRepoDatabaseInfrastructure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userClusterID:** `string` — Infrastructure cluster ID
    
</dd>
</dl>

<dl>
<dd>

**repoName:** `string` — Backup repository name
    
</dd>
</dl>

<dl>
<dd>

**mode:** `*americancloudsdkgo.DeleteBackupRepoDatabaseInfrastructureRequestMode` — Deletion mode: retire (default) or destroy
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## database-operations
<details><summary><code>client.DatabaseOperations.GetStatusDatabaseOperations(CorrelationID) -> *americancloudsdkgo.OperationStatusResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed status for a database operation including progress of child commands.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetStatusDatabaseOperationsRequest{
        CorrelationID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DatabaseOperations.GetStatusDatabaseOperations(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**correlationID:** `string` — Operation correlation ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## dns-zones
<details><summary><code>client.DNSZones.ListDNSZones() -> *americancloudsdkgo.ListDNSZonesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDNSZonesRequest{}
client.DNSZones.ListDNSZones(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DNSZones.CreateDNSZones(request) -> *americancloudsdkgo.ZoneResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateZoneDto{
        Name: "example.com",
    }
client.DNSZones.CreateDNSZones(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — The domain name for the DNS zone (e.g. example.com)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DNSZones.DeleteDNSZones(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteDNSZonesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DNSZones.DeleteDNSZones(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the DNS zone to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## dns-records
<details><summary><code>client.DNSRecords.ListDNSRecords(ZoneID) -> *americancloudsdkgo.ListDNSRecordsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListDNSRecordsRequest{
        ZoneID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.DNSRecords.ListDNSRecords(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zoneID:** `string` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DNSRecords.CreateDNSRecords(ZoneID, request) -> *americancloudsdkgo.RecordResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateRecordDto{
        ZoneID: "123e4567-e89b-12d3-a456-426614174000",
        Name: "www",
        Type: americancloudsdkgo.CreateRecordDtoTypeA,
        Content: "93.184.216.34",
    }
client.DNSRecords.CreateDNSRecords(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zoneID:** `string` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` — Hostname for the record. Use @ for the zone apex.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.CreateRecordDtoType` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `string` — Record value (IP address, hostname, text, etc.)
    
</dd>
</dl>

<dl>
<dd>

**ttl:** `*float64` — Time to live in seconds (60–86400)
    
</dd>
</dl>

<dl>
<dd>

**priority:** `*int` — Priority (required for MX and SRV records)
    
</dd>
</dl>

<dl>
<dd>

**weight:** `*int` — Weight (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**port:** `*int` — Port (required for SRV records)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DNSRecords.UpdateDNSRecords(ZoneID, CurrentName, CurrentType, request) -> *americancloudsdkgo.RecordResponseDto</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdateRecordDto{
        ZoneID: "123e4567-e89b-12d3-a456-426614174000",
        CurrentName: "www",
        CurrentType: "A",
        Name: "www",
        Type: americancloudsdkgo.UpdateRecordDtoTypeA,
        Content: "93.184.216.34",
    }
client.DNSRecords.UpdateDNSRecords(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zoneID:** `string` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**currentName:** `string` — Current record hostname identifying the record to update (use @ for apex)
    
</dd>
</dl>

<dl>
<dd>

**currentType:** `string` — Current record type identifying the record to update (A, AAAA, CNAME, MX, NS, SRV, TXT)
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` — Hostname for the record. Use @ for the zone apex.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*americancloudsdkgo.UpdateRecordDtoType` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `string` — Record value (IP address, hostname, text, etc.)
    
</dd>
</dl>

<dl>
<dd>

**ttl:** `*float64` — Time to live in seconds (60–86400)
    
</dd>
</dl>

<dl>
<dd>

**priority:** `*int` — Priority (required for MX and SRV records)
    
</dd>
</dl>

<dl>
<dd>

**weight:** `*int` — Weight (required for SRV records)
    
</dd>
</dl>

<dl>
<dd>

**port:** `*int` — Port (required for SRV records)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.DNSRecords.DeleteDNSRecords(ZoneID, Name, Type, request) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteRecordBody{
        ZoneID: "123e4567-e89b-12d3-a456-426614174000",
        Name: "www",
        Type: "A",
    }
client.DNSRecords.DeleteDNSRecords(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zoneID:** `string` — DNS zone identifier
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` — Record hostname (use @ for apex)
    
</dd>
</dl>

<dl>
<dd>

**type_:** `string` — Record type
    
</dd>
</dl>

<dl>
<dd>

**content:** `*string` — Specific record value to remove. Used for multi-value MX/NS/TXT record sets to target a single entry.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## kubernetes
<details><summary><code>client.Kubernetes.ListVersionsKubernetes() -> *americancloudsdkgo.ListVersionsKubernetesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all available versions. If current_version is provided, returns only versions that are valid upgrade targets (higher version, max one minor version jump).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListVersionsKubernetesRequest{
        CurrentVersion: americancloudsdkgo.String(
            "1.28.4",
        ),
    }
client.Kubernetes.ListVersionsKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**currentVersion:** `*string` — Current cluster version to filter upgradeable versions from
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.ListPackagesKubernetes() -> *americancloudsdkgo.ListPackagesKubernetesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListPackagesKubernetesRequest{}
client.Kubernetes.ListPackagesKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.ListClustersKubernetes() -> *americancloudsdkgo.ListClustersKubernetesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListClustersKubernetesRequest{}
client.Kubernetes.ListClustersKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.GetClusterKubernetes(ID) -> *americancloudsdkgo.KubernetesClusterResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns cluster details. Set details=true to include node instances and attached storage volumes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetClusterKubernetesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Details: americancloudsdkgo.Bool(
            false,
        ),
    }
client.Kubernetes.GetClusterKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**details:** `*bool` — Include node instances and storage volumes in the response
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.DeleteClusterKubernetes(ID) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteClusterKubernetesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Kubernetes.DeleteClusterKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.CreateClusterKubernetes(request) -> *americancloudsdkgo.KubernetesClusterResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new Kubernetes cluster for the authenticated account. To preview pricing without creating anything, use POST /kubernetes/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateKubernetesClusterRequest{
        Name: "my-cluster",
        Package: "my-package",
        Region: "us-west-0",
        Version: "1.28.4",
        ControlNodes: 1,
        WorkerNodes: 3,
    }
client.Kubernetes.CreateClusterKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateKubernetesClusterRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.GetCostEstimateKubernetes(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a cluster with the given configuration without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateKubernetesClusterRequest{
        Name: "my-cluster",
        Package: "my-package",
        Region: "us-west-0",
        Version: "1.28.4",
        ControlNodes: 1,
        WorkerNodes: 3,
    }
client.Kubernetes.GetCostEstimateKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateKubernetesClusterRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.ClusterPowerKubernetes(ID) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start or stop a Kubernetes cluster
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ClusterPowerKubernetesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Action: americancloudsdkgo.ClusterPowerKubernetesRequestActionStart,
    }
client.Kubernetes.ClusterPowerKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**action:** `*americancloudsdkgo.ClusterPowerKubernetesRequestAction` — Power action to perform
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.GetClusterConfigKubernetes(ID) -> *americancloudsdkgo.KubernetesConfigResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the kubeconfig file content for connecting to the cluster
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetClusterConfigKubernetesRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Kubernetes.GetClusterConfigKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.ScaleClusterKubernetes(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Scale worker nodes, or enable/disable autoscaling with min/max bounds. At least one parameter must be provided.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ScaleKubernetesClusterRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Kubernetes.ScaleClusterKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**workerNodes:** `*float64` — Number of worker nodes
    
</dd>
</dl>

<dl>
<dd>

**autoscalingEnabled:** `*bool` — Enable or disable autoscaling
    
</dd>
</dl>

<dl>
<dd>

**minWorkers:** `*float64` — Minimum number of worker nodes when autoscaling is enabled
    
</dd>
</dl>

<dl>
<dd>

**maxWorkers:** `*float64` — Maximum number of worker nodes when autoscaling is enabled
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Kubernetes.UpgradeClusterKubernetes(ID, request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upgrade to a newer Kubernetes version. Use GET /versions to list available versions.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpgradeKubernetesClusterRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        Version: "1.29.0",
    }
client.Kubernetes.UpgradeClusterKubernetes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — ID of the Kubernetes cluster
    
</dd>
</dl>

<dl>
<dd>

**version:** `string` — Kubernetes version to upgrade to (semantic version)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## object-storage
<details><summary><code>client.ObjectStorage.ListUnitsObjectStorage() -> *americancloudsdkgo.ListUnitsObjectStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all non-deleted object storage units (UIDs) for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListUnitsObjectStorageRequest{
        Usage: americancloudsdkgo.Bool(
            false,
        ),
    }
client.ObjectStorage.ListUnitsObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**usage:** `*bool` — Include latest usage report for each storage unit
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.CreateUnitObjectStorage(request) -> *americancloudsdkgo.ObjectStorageUnitDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new object storage unit for the authenticated account and returns it. The returned storageUnitId identifies the unit in all other object storage requests. To preview pricing without creating anything, use POST /object-storage/units/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateStorageUnitRequestDto{
        Name: "storageunit01",
    }
client.ObjectStorage.CreateUnitObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Storage unit name. Alphanumeric characters only.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.ListBucketsObjectStorage(StorageUnitID) -> *americancloudsdkgo.ListBucketsObjectStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all buckets and their statistics for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListBucketsObjectStorageRequest{
        StorageUnitID: "tenant$user",
    }
client.ObjectStorage.ListBucketsObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.CreateBucketObjectStorage(StorageUnitID, request) -> *americancloudsdkgo.ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new bucket for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateBucketRequestDto{
        StorageUnitID: "tenant$user",
        Name: "my-storage-bucket",
    }
client.ObjectStorage.CreateBucketObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` — Bucket name. Lowercase letters, numbers, dots, and hyphens only; must start and end with a letter or number.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.GetKeysObjectStorage(StorageUnitID) -> *americancloudsdkgo.AccessKeyDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all access keys (access key and secret key pairs) for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetKeysObjectStorageRequest{
        StorageUnitID: "tenant$user",
    }
client.ObjectStorage.GetKeysObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.GetCostEstimateObjectStorage() -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost of an object storage unit without creating one.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.ObjectStorage.GetCostEstimateObjectStorage(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.SetUserQuotaObjectStorage(StorageUnitID, request) -> *americancloudsdkgo.ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets the user quota limit for the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.SetUserQuotaRequestDto{
        StorageUnitID: "tenant$user",
    }
client.ObjectStorage.SetUserQuotaObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**maxSizeGb:** `*float64` — Maximum total size for the storage unit, in gigabytes.
    
</dd>
</dl>

<dl>
<dd>

**removeLimit:** `*bool` — When true, removes any existing storage limit instead of setting a value.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.DeleteUnitObjectStorage(StorageUnitID) -> *americancloudsdkgo.ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes an object storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteUnitObjectStorageRequest{
        StorageUnitID: "tenant$user",
    }
client.ObjectStorage.DeleteUnitObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.ObjectStorage.DeleteBucketObjectStorage(StorageUnitID, BucketName) -> *americancloudsdkgo.ObjectStorageSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a bucket from the specified storage unit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteBucketObjectStorageRequest{
        StorageUnitID: "tenant$user",
        BucketName: "my-bucket",
        PurgeObjects: americancloudsdkgo.Bool(
            true,
        ),
    }
client.ObjectStorage.DeleteBucketObjectStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**storageUnitID:** `string` — Storage unit ID (UID)
    
</dd>
</dl>

<dl>
<dd>

**bucketName:** `string` — Bucket name
    
</dd>
</dl>

<dl>
<dd>

**purgeObjects:** `*bool` — Whether to purge objects in the bucket (default: true)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## ssh-keys
<details><summary><code>client.SSHKeys.ListSSHKeys() -> *americancloudsdkgo.ListSSHKeysResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListSSHKeysRequest{}
client.SSHKeys.ListSSHKeys(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.SSHKeys.CreateSSHKeys(request) -> *americancloudsdkgo.CreateSSHKeyResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

If publicKey is provided, registers your existing public key. If omitted, generates a new key pair and returns the private key (shown only once).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateSSHKeyDto{
        Name: "my-ssh-key",
    }
client.SSHKeys.CreateSSHKeys(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Name of the SSH key pair
    
</dd>
</dl>

<dl>
<dd>

**publicKey:** `*string` — Public key to register. If provided, the key pair is registered using your existing key. If omitted, a new key pair is generated and the private key is returned.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.SSHKeys.DeleteSSHKeys(Name) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteSSHKeysRequest{
        Name: "my-ssh-key",
    }
client.SSHKeys.DeleteSSHKeys(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` — Name of the SSH key pair to delete
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## block-storage
<details><summary><code>client.BlockStorage.ListBlockStorage() -> *americancloudsdkgo.ListBlockStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns block storage volumes for the authenticated account. Optionally filter by virtual machine.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListBlockStorageRequest{}
client.BlockStorage.ListBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vmId:** `*string` — Filter volumes attached to a specific virtual machine
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.CreateBlockStorage(request) -> *americancloudsdkgo.VolumeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new block storage volume. To preview pricing without creating anything, use POST /storage/block-storage/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVolumeDto{
        Name: "my-block-storage",
        SizeGb: 100,
        Region: "us-west-0",
    }
client.BlockStorage.CreateBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVolumeDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.GetBlockStorage(ID) -> *americancloudsdkgo.VolumeResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns details of a specific block storage volume
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetBlockStorageRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.BlockStorage.GetBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.DeleteBlockStorage(ID) -> *americancloudsdkgo.VolumeDeletionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a block storage volume. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteBlockStorageRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.BlockStorage.DeleteBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.GetCostEstimateBlockStorage(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a volume with the given specs without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateVolumeDto{
        Name: "my-block-storage",
        SizeGb: 100,
        Region: "us-west-0",
    }
client.BlockStorage.GetCostEstimateBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateVolumeDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.AttachBlockStorage(ID, request) -> *americancloudsdkgo.VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Attaches a volume to a specified virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.AttachVolumeDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        VmId: "f8d7e91c-f24d-4c21-b75e-4c7c5389c305",
    }
client.BlockStorage.AttachBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**vmId:** `string` — The ID of the virtual machine to attach the volume to
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.DetachBlockStorage(ID) -> *americancloudsdkgo.VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Detaches a volume from its currently attached virtual machine
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DetachBlockStorageRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.BlockStorage.DetachBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.ResizeBlockStorage(ID, request) -> *americancloudsdkgo.VolumeOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Increases the size of a block storage volume. The new size must be larger than the current size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ResizeVolumeDto{
        ID: "123e4567-e89b-12d3-a456-426614174000",
        SizeGb: 200,
    }
client.BlockStorage.ResizeBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**sizeGb:** `int` — The new size of the volume in GB. Must be larger than the current size.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.BlockStorage.ListSnapshotsBlockStorage(ID) -> *americancloudsdkgo.ListSnapshotsBlockStorageResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all snapshots for the specified volume.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListSnapshotsBlockStorageRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.BlockStorage.ListSnapshotsBlockStorage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Volume ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## snapshots
<details><summary><code>client.Snapshots.ListSnapshots() -> *americancloudsdkgo.ListSnapshotsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all snapshots for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListSnapshotsRequest{}
client.Snapshots.ListSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Snapshots.CreateSnapshots(request) -> *americancloudsdkgo.SnapshotResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new snapshot from a block storage volume. To preview pricing without creating anything, use POST /storage/snapshots/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateSnapshotDto{
        VolumeID: "vol-123456",
        Name: "my-data-snapshot",
        Type: americancloudsdkgo.CreateSnapshotDtoTypeDataDisk,
    }
client.Snapshots.CreateSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateSnapshotDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Snapshots.GetSnapshots(ID) -> *americancloudsdkgo.SnapshotResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns details of a specific snapshot
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.GetSnapshotsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Snapshots.GetSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Snapshot ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Snapshots.DeleteSnapshots(ID) -> *americancloudsdkgo.SnapshotOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes a snapshot. This operation cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.DeleteSnapshotsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Snapshots.DeleteSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Snapshot ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Snapshots.GetCostEstimateSnapshots(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a snapshot of the given volume without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateSnapshotDto{
        VolumeID: "vol-123456",
        Name: "my-data-snapshot",
        Type: americancloudsdkgo.CreateSnapshotDtoTypeDataDisk,
    }
client.Snapshots.GetCostEstimateSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateSnapshotDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Snapshots.RevertSnapshots(ID) -> *americancloudsdkgo.SnapshotOperationResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reverts the volume associated with this snapshot to its point-in-time state.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.RevertSnapshotsRequest{
        ID: "123e4567-e89b-12d3-a456-426614174000",
    }
client.Snapshots.RevertSnapshots(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` — Snapshot ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## wordpress
<details><summary><code>client.Wordpress.GetWordpress() -> *americancloudsdkgo.WordPressInstanceDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the active WordPress instance for the account. Returns 404 if the account has no WordPress instance.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.CreateWordpress(request) -> *americancloudsdkgo.WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new WordPress hosting instance for the authenticated account. To preview pricing without creating anything, use POST /wordpress/cost-estimate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateWordPressDto{
        PackageLabel: "wordpress-10",
    }
client.Wordpress.CreateWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateWordPressDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.CancelWordpress() -> *americancloudsdkgo.WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancels and removes the WordPress instance for the authenticated account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.CancelWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetCostEstimateWordpress(request) -> *americancloudsdkgo.CostEstimateResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the estimated cost for a WordPress instance on the given package without creating it. Accepts the same body as create.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.CreateWordPressDto{
        PackageLabel: "wordpress-10",
    }
client.Wordpress.GetCostEstimateWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*americancloudsdkgo.CreateWordPressDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.UpdatePasswordWordpress(request) -> *americancloudsdkgo.WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the password for the WordPress hosting account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.UpdatePasswordDto{
        NewPassword: "newPassword",
    }
client.Wordpress.UpdatePasswordWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**newPassword:** `string` — New password for the WordPress hosting account
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.CreateSessionWordpress() -> *americancloudsdkgo.SessionResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a login session URL for managing your WordPress hosting
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.CreateSessionWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetQuotaWordpress() -> *americancloudsdkgo.QuotaInfoDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns disk and resource quota information for the WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetQuotaWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetMaxInstancesWordpress() -> *americancloudsdkgo.MaxInstancesDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the maximum number of WordPress sites allowed for the current package
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetMaxInstancesWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.ListWebsitesWordpress() -> *americancloudsdkgo.WebsitesDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a list of all WordPress websites/sites for the account
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.ListWebsitesWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetBandwidthWordpress() -> *americancloudsdkgo.BandwidthDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns bandwidth usage statistics for the WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetBandwidthWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetNameserversWordpress() -> *americancloudsdkgo.NameserversDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the nameserver addresses for the WordPress hosting server
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetNameserversWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.ChangePackageWordpress(request) -> *americancloudsdkgo.WordPressSuccessResponseDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upgrades the WordPress instance to a higher tier package/plan
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ChangePackageDto{
        PackageLabel: "wordpress-25",
    }
client.Wordpress.ChangePackageWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**packageLabel:** `string` — New package label to upgrade to
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.ListPackagesWordpress() -> *americancloudsdkgo.ListPackagesWordpressResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all available WordPress hosting packages/plans
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListPackagesWordpressRequest{}
client.Wordpress.ListPackagesWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.GetCurrentPackageWordpress() -> *americancloudsdkgo.WordPressPackageDto</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the current package for the account's WordPress instance
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Wordpress.GetCurrentPackageWordpress(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Wordpress.ListUpgradePackagesWordpress() -> *americancloudsdkgo.ListUpgradePackagesWordpressResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns packages available for upgrade (higher tier than current)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &americancloudsdkgo.ListUpgradePackagesWordpressRequest{}
client.Wordpress.ListUpgradePackagesWordpress(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` — Page number, 1-indexed. Defaults to 1 when omitted.
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` — Items per page. Defaults to 100 when omitted; server cap 500.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

