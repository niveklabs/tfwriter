# aci_cloud_cidr_pool

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aci_cloud_cidr_pool" {
  source = "./modules/aci/d/aci_cloud_cidr_pool"

  # addr - (required) is a type of string
  addr = null
  # annotation - (optional) is a type of string
  annotation = null
  # cloud_context_profile_dn - (required) is a type of string
  cloud_context_profile_dn = null
  # description - (optional) is a type of string
  description = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # primary - (optional) is a type of string
  primary = null
}
```

[top](#index)

### Variables

```terraform
variable "addr" {
  description = "(required)"
  type        = string
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_context_profile_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_cidr_pool" "this" {
  addr                     = var.addr
  annotation               = var.annotation
  cloud_context_profile_dn = var.cloud_context_profile_dn
  description              = var.description
  name_alias               = var.name_alias
  primary                  = var.primary
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_cidr_pool.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_cidr_pool.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_cidr_pool.this.name_alias
}

output "primary" {
  description = "returns a string"
  value       = data.aci_cloud_cidr_pool.this.primary
}

output "this" {
  value = aci_cloud_cidr_pool.this
}
```

[top](#index)