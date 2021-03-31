# fortios_system_ndproxy

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
module "fortios_system_ndproxy" {
  source = "./modules/fortios/r/fortios_system_ndproxy"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # status - (optional) is a type of string
  status = null

  member = [{
    interface_name = null
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

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ndproxy" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  status                = var.status

  dynamic "member" {
    for_each = var.member
    content {
      interface_name = member.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_ndproxy.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_system_ndproxy.this.status
}

output "this" {
  value = fortios_system_ndproxy.this
}
```

[top](#index)