# avi_vsvip

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
module "avi_vsvip" {
  source = "./modules/avi/d/avi_vsvip"

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
data "avi_vsvip" "this" {
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
  value       = data.avi_vsvip.this.cloud_ref
}

output "dns_info" {
  description = "returns a list of object"
  value       = data.avi_vsvip.this.dns_info
}

output "east_west_placement" {
  description = "returns a bool"
  value       = data.avi_vsvip.this.east_west_placement
}

output "id" {
  description = "returns a string"
  value       = data.avi_vsvip.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_vsvip.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_vsvip.this.tenant_ref
}

output "use_standard_alb" {
  description = "returns a bool"
  value       = data.avi_vsvip.this.use_standard_alb
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_vsvip.this.uuid
}

output "vip" {
  description = "returns a list of object"
  value       = data.avi_vsvip.this.vip
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = data.avi_vsvip.this.vrf_context_ref
}

output "vsvip_cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_vsvip.this.vsvip_cloud_config_cksum
}

output "this" {
  value = avi_vsvip.this
}
```

[top](#index)