# aci_logical_node_to_fabric_node

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
module "aci_logical_node_to_fabric_node" {
  source = "./modules/aci/r/aci_logical_node_to_fabric_node"

  # annotation - (optional) is a type of string
  annotation = null
  # config_issues - (optional) is a type of string
  config_issues = null
  # description - (optional) is a type of string
  description = null
  # logical_node_profile_dn - (required) is a type of string
  logical_node_profile_dn = null
  # rtr_id - (optional) is a type of string
  rtr_id = null
  # rtr_id_loop_back - (optional) is a type of string
  rtr_id_loop_back = null
  # tdn - (required) is a type of string
  tdn = null
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

variable "logical_node_profile_dn" {
  description = "(required)"
  type        = string
}

variable "rtr_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rtr_id_loop_back" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tdn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_logical_node_to_fabric_node" "this" {
  annotation              = var.annotation
  config_issues           = var.config_issues
  description             = var.description
  logical_node_profile_dn = var.logical_node_profile_dn
  rtr_id                  = var.rtr_id
  rtr_id_loop_back        = var.rtr_id_loop_back
  tdn                     = var.tdn
}
```

[top](#index)

### Outputs

```terraform
output "config_issues" {
  description = "returns a string"
  value       = aci_logical_node_to_fabric_node.this.config_issues
}

output "description" {
  description = "returns a string"
  value       = aci_logical_node_to_fabric_node.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_logical_node_to_fabric_node.this.id
}

output "rtr_id" {
  description = "returns a string"
  value       = aci_logical_node_to_fabric_node.this.rtr_id
}

output "rtr_id_loop_back" {
  description = "returns a string"
  value       = aci_logical_node_to_fabric_node.this.rtr_id_loop_back
}

output "this" {
  value = aci_logical_node_to_fabric_node.this
}
```

[top](#index)