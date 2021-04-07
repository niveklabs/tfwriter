# aci_cloud_providers_region

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_providers_region" {
  source = "./modules/aci/r/aci_cloud_providers_region"

  # admin_st - (optional) is a type of string
  admin_st = null
  # annotation - (optional) is a type of string
  annotation = null
  # cloud_provider_profile_dn - (required) is a type of string
  cloud_provider_profile_dn = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_st" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_provider_profile_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_cloud_providers_region" "this" {
  # admin_st - (optional) is a type of string
  admin_st = var.admin_st
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # cloud_provider_profile_dn - (required) is a type of string
  cloud_provider_profile_dn = var.cloud_provider_profile_dn
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "admin_st" {
  description = "returns a string"
  value       = aci_cloud_providers_region.this.admin_st
}

output "description" {
  description = "returns a string"
  value       = aci_cloud_providers_region.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_cloud_providers_region.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_cloud_providers_region.this.name_alias
}

output "this" {
  value = aci_cloud_providers_region.this
}
```

[top](#index)