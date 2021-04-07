# aci_access_port_selector

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
module "aci_access_port_selector" {
  source = "./modules/aci/d/aci_access_port_selector"

  # access_port_selector_type - (required) is a type of string
  access_port_selector_type = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # leaf_interface_profile_dn - (required) is a type of string
  leaf_interface_profile_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
}
```

[top](#index)

### Variables

```terraform
variable "access_port_selector_type" {
  description = "(required)"
  type        = string
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

variable "leaf_interface_profile_dn" {
  description = "(required)"
  type        = string
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
data "aci_access_port_selector" "this" {
  # access_port_selector_type - (required) is a type of string
  access_port_selector_type = var.access_port_selector_type
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # description - (optional) is a type of string
  description = var.description
  # leaf_interface_profile_dn - (required) is a type of string
  leaf_interface_profile_dn = var.leaf_interface_profile_dn
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
  value       = data.aci_access_port_selector.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_access_port_selector.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_access_port_selector.this.name_alias
}

output "this" {
  value = aci_access_port_selector.this
}
```

[top](#index)