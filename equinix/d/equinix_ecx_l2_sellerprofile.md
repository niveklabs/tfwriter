# equinix_ecx_l2_sellerprofile

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.0.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_sellerprofile" {
  source = "./modules/equinix/d/equinix_ecx_l2_sellerprofile"

  # name - (optional) is a type of string
  name = null
  # organization_global_name - (optional) is a type of string
  organization_global_name = null
  # organization_name - (optional) is a type of string
  organization_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization_global_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_ecx_l2_sellerprofile" "this" {
  name                     = var.name
  organization_global_name = var.organization_global_name
  organization_name        = var.organization_name
}
```

[top](#index)

### Outputs

```terraform
output "additional_info" {
  description = "returns a set of object"
  value       = data.equinix_ecx_l2_sellerprofile.this.additional_info
}

output "description" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.description
}

output "encapsulation" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.encapsulation
}

output "id" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.id
}

output "metro" {
  description = "returns a set of object"
  value       = data.equinix_ecx_l2_sellerprofile.this.metro
}

output "name" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.name
}

output "organization_global_name" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.organization_global_name
}

output "organization_name" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.organization_name
}

output "redundancy_required" {
  description = "returns a bool"
  value       = data.equinix_ecx_l2_sellerprofile.this.redundancy_required
}

output "speed_band" {
  description = "returns a set of object"
  value       = data.equinix_ecx_l2_sellerprofile.this.speed_band
}

output "speed_customization_allowed" {
  description = "returns a bool"
  value       = data.equinix_ecx_l2_sellerprofile.this.speed_customization_allowed
}

output "speed_from_api" {
  description = "returns a bool"
  value       = data.equinix_ecx_l2_sellerprofile.this.speed_from_api
}

output "uuid" {
  description = "returns a string"
  value       = data.equinix_ecx_l2_sellerprofile.this.uuid
}

output "this" {
  value = equinix_ecx_l2_sellerprofile.this
}
```

[top](#index)