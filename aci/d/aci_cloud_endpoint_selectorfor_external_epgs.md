# aci_cloud_endpoint_selectorfor_external_epgs

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
module "aci_cloud_endpoint_selectorfor_external_epgs" {
  source = "./modules/aci/d/aci_cloud_endpoint_selectorfor_external_epgs"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_external_epg_dn - (required) is a type of string
  cloud_external_epg_dn = null
  # description - (optional) is a type of string
  description = null
  # is_shared - (optional) is a type of string
  is_shared = null
  # match_expression - (optional) is a type of string
  match_expression = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # subnet - (optional) is a type of string
  subnet = null
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

variable "cloud_external_epg_dn" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_shared" {
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

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_endpoint_selectorfor_external_epgs" "this" {
  annotation            = var.annotation
  cloud_external_epg_dn = var.cloud_external_epg_dn
  description           = var.description
  is_shared             = var.is_shared
  match_expression      = var.match_expression
  name                  = var.name
  name_alias            = var.name_alias
  subnet                = var.subnet
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.id
}

output "is_shared" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.is_shared
}

output "match_expression" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.match_expression
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.name_alias
}

output "subnet" {
  description = "returns a string"
  value       = data.aci_cloud_endpoint_selectorfor_external_epgs.this.subnet
}

output "this" {
  value = aci_cloud_endpoint_selectorfor_external_epgs.this
}
```

[top](#index)