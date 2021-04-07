# fortios_wirelesscontroller_bonjourprofile

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
module "fortios_wirelesscontroller_bonjourprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_bonjourprofile"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  policy_list = [{
    description = null
    from_vlan   = null
    policy_id   = null
    services    = null
    to_vlan     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      from_vlan   = string
      policy_id   = number
      services    = string
      to_vlan     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_bonjourprofile" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "policy_list" {
    for_each = var.policy_list
    content {
      # description - (optional) is a type of string
      description = policy_list.value["description"]
      # from_vlan - (optional) is a type of string
      from_vlan = policy_list.value["from_vlan"]
      # policy_id - (optional) is a type of number
      policy_id = policy_list.value["policy_id"]
      # services - (optional) is a type of string
      services = policy_list.value["services"]
      # to_vlan - (optional) is a type of string
      to_vlan = policy_list.value["to_vlan"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bonjourprofile.this.comment
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bonjourprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bonjourprofile.this.name
}

output "this" {
  value = fortios_wirelesscontroller_bonjourprofile.this
}
```

[top](#index)