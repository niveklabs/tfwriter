# fortios_switchcontroller_vlanpolicy

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_vlanpolicy" {
  source = "./modules/fortios/r/fortios_switchcontroller_vlanpolicy"

  # allowed_vlans_all - (optional) is a type of string
  allowed_vlans_all = null
  # description - (optional) is a type of string
  description = null
  # discard_mode - (optional) is a type of string
  discard_mode = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fortilink - (optional) is a type of string
  fortilink = null
  # name - (optional) is a type of string
  name = null
  # vlan - (optional) is a type of string
  vlan = null

  allowed_vlans = [{
    vlan_name = null
  }]

  untagged_vlans = [{
    vlan_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowed_vlans_all" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discard_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortilink" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_vlans" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      vlan_name = string
    }
  ))
  default = []
}

variable "untagged_vlans" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      vlan_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_vlanpolicy" "this" {
  # allowed_vlans_all - (optional) is a type of string
  allowed_vlans_all = var.allowed_vlans_all
  # description - (optional) is a type of string
  description = var.description
  # discard_mode - (optional) is a type of string
  discard_mode = var.discard_mode
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fortilink - (optional) is a type of string
  fortilink = var.fortilink
  # name - (optional) is a type of string
  name = var.name
  # vlan - (optional) is a type of string
  vlan = var.vlan

  dynamic "allowed_vlans" {
    for_each = var.allowed_vlans
    content {
      # vlan_name - (optional) is a type of string
      vlan_name = allowed_vlans.value["vlan_name"]
    }
  }

  dynamic "untagged_vlans" {
    for_each = var.untagged_vlans
    content {
      # vlan_name - (optional) is a type of string
      vlan_name = untagged_vlans.value["vlan_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allowed_vlans_all" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.allowed_vlans_all
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.description
}

output "discard_mode" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.discard_mode
}

output "fortilink" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.fortilink
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.name
}

output "vlan" {
  description = "returns a string"
  value       = fortios_switchcontroller_vlanpolicy.this.vlan
}

output "this" {
  value = fortios_switchcontroller_vlanpolicy.this
}
```

[top](#index)