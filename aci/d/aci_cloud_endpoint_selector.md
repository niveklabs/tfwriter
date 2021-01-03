# aci_cloud_endpoint_selector

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_endpoint_selector" {
  source = "./modules/aci/d/aci_cloud_endpoint_selector"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_epg_dn - (required) is a type of string
  cloud_epg_dn = null
  # description - (optional) is a type of string
  description = null
  # match_expression - (optional) is a type of string
  match_expression = null
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

variable "cloud_epg_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_expression" {
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
data "aci_cloud_endpoint_selector" "this" {
  annotation       = var.annotation
  cloud_epg_dn     = var.cloud_epg_dn
  description      = var.description
  match_expression = var.match_expression
  name             = var.name
  name_alias       = var.name_alias
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selector.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selector.this.id
}

output "match_expression" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selector.this.match_expression
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selector.this.name_alias
}

output "this" {
  value = aci_cloud_endpoint_selector.this
}
```

[top](#index)