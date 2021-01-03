# aci_logical_node_profile

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_logical_node_profile" {
  source = "./modules/aci/r/aci_logical_node_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # config_issues - (optional) is a type of string
  config_issues = null
  # description - (optional) is a type of string
  description = null
  # l3_outside_dn - (required) is a type of string
  l3_outside_dn = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # tag - (optional) is a type of string
  tag = null
  # target_dscp - (optional) is a type of string
  target_dscp = null
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

variable "config_issues" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l3_outside_dn" {
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

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_dscp" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_logical_node_profile" "this" {
  annotation    = var.annotation
  config_issues = var.config_issues
  description   = var.description
  l3_outside_dn = var.l3_outside_dn
  name          = var.name
  name_alias    = var.name_alias
  tag           = var.tag
  target_dscp   = var.target_dscp
}
```

[top](#index)

### Outputs

```terraform
output "config_issues" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.config_issues
}

output "description" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.name_alias
}

output "tag" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.tag
}

output "target_dscp" {
  description = "returns a string"
  value       = aci_logical_node_profile.this.target_dscp
}

output "this" {
  value = aci_logical_node_profile.this
}
```

[top](#index)