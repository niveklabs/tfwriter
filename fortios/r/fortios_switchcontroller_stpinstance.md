# fortios_switchcontroller_stpinstance

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
module "fortios_switchcontroller_stpinstance" {
  source = "./modules/fortios/r/fortios_switchcontroller_stpinstance"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (optional) is a type of string
  fosid = null

  vlan_range = [{
    vlan_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_range" {
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
resource "fortios_switchcontroller_stpinstance" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  fosid                 = var.fosid

  dynamic "vlan_range" {
    for_each = var.vlan_range
    content {
      vlan_name = vlan_range.value["vlan_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a string"
  value       = fortios_switchcontroller_stpinstance.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_stpinstance.this.id
}

output "this" {
  value = fortios_switchcontroller_stpinstance.this
}
```

[top](#index)