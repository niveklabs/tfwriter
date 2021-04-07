# fortios_system_federatedupgrade

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
module "fortios_system_federatedupgrade" {
  source = "./modules/fortios/r/fortios_system_federatedupgrade"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # status - (optional) is a type of string
  status = null

  node_list = [{
    serial       = null
    setup_time   = null
    time         = null
    timing       = null
    upgrade_path = null
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      serial       = string
      setup_time   = string
      time         = string
      timing       = string
      upgrade_path = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_federatedupgrade" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # status - (optional) is a type of string
  status = var.status

  dynamic "node_list" {
    for_each = var.node_list
    content {
      # serial - (optional) is a type of string
      serial = node_list.value["serial"]
      # setup_time - (optional) is a type of string
      setup_time = node_list.value["setup_time"]
      # time - (optional) is a type of string
      time = node_list.value["time"]
      # timing - (optional) is a type of string
      timing = node_list.value["timing"]
      # upgrade_path - (optional) is a type of string
      upgrade_path = node_list.value["upgrade_path"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_federatedupgrade.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_system_federatedupgrade.this.status
}

output "this" {
  value = fortios_system_federatedupgrade.this
}
```

[top](#index)