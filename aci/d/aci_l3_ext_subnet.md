# aci_l3_ext_subnet

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
module "aci_l3_ext_subnet" {
  source = "./modules/aci/d/aci_l3_ext_subnet"

  # aggregate - (optional) is a type of string
  aggregate = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # external_network_instance_profile_dn - (required) is a type of string
  external_network_instance_profile_dn = null
  # ip - (required) is a type of string
  ip = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # scope - (optional) is a type of list of string
  scope = []
}
```

[top](#index)

### Variables

```terraform
variable "aggregate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_network_instance_profile_dn" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_l3_ext_subnet" "this" {
  aggregate                            = var.aggregate
  annotation                           = var.annotation
  description                          = var.description
  external_network_instance_profile_dn = var.external_network_instance_profile_dn
  ip                                   = var.ip
  name_alias                           = var.name_alias
  scope                                = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "aggregate" {
  description = "returns a string"
  value       = data.aci_l3_ext_subnet.this.aggregate
}

output "description" {
  description = "returns a string"
  value       = data.aci_l3_ext_subnet.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_l3_ext_subnet.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_l3_ext_subnet.this.name_alias
}

output "scope" {
  description = "returns a list of string"
  value       = data.aci_l3_ext_subnet.this.scope
}

output "this" {
  value = aci_l3_ext_subnet.this
}
```

[top](#index)