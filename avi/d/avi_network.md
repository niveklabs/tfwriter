# avi_network

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_network" {
  source = "./modules/avi/d/avi_network"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_network" "this" {
  cloud_ref  = var.cloud_ref
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_network.this.cloud_ref
}

output "configured_subnets" {
  description = "returns a list of object"
  value       = data.avi_network.this.configured_subnets
}

output "dhcp_enabled" {
  description = "returns a bool"
  value       = data.avi_network.this.dhcp_enabled
}

output "exclude_discovered_subnets" {
  description = "returns a bool"
  value       = data.avi_network.this.exclude_discovered_subnets
}

output "id" {
  description = "returns a string"
  value       = data.avi_network.this.id
}

output "ip6_autocfg_enabled" {
  description = "returns a bool"
  value       = data.avi_network.this.ip6_autocfg_enabled
}

output "labels" {
  description = "returns a list of object"
  value       = data.avi_network.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.avi_network.this.name
}

output "synced_from_se" {
  description = "returns a bool"
  value       = data.avi_network.this.synced_from_se
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_network.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_network.this.uuid
}

output "vcenter_dvs" {
  description = "returns a bool"
  value       = data.avi_network.this.vcenter_dvs
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = data.avi_network.this.vrf_context_ref
}

output "this" {
  value = avi_network.this
}
```

[top](#index)