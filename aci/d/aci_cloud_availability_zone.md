# aci_cloud_availability_zone

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
module "aci_cloud_availability_zone" {
  source = "./modules/aci/d/aci_cloud_availability_zone"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_providers_region_dn - (required) is a type of string
  cloud_providers_region_dn = null
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
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_providers_region_dn" {
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

### Datasource

```terraform
data "aci_cloud_availability_zone" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # cloud_providers_region_dn - (required) is a type of string
  cloud_providers_region_dn = var.cloud_providers_region_dn
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
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_availability_zone.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_availability_zone.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_availability_zone.this.name_alias
}

output "this" {
  value = aci_cloud_availability_zone.this
}
```

[top](#index)