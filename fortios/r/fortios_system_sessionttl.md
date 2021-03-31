# fortios_system_sessionttl

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
module "fortios_system_sessionttl" {
  source = "./modules/fortios/r/fortios_system_sessionttl"

  # default - (optional) is a type of string
  default = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null

  port = [{
    end_port   = null
    id         = null
    protocol   = null
    start_port = null
    timeout    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_port   = number
      id         = number
      protocol   = number
      start_port = number
      timeout    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_sessionttl" "this" {
  default               = var.default
  dynamic_sort_subtable = var.dynamic_sort_subtable

  dynamic "port" {
    for_each = var.port
    content {
      end_port   = port.value["end_port"]
      id         = port.value["id"]
      protocol   = port.value["protocol"]
      start_port = port.value["start_port"]
      timeout    = port.value["timeout"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a string"
  value       = fortios_system_sessionttl.this.default
}

output "id" {
  description = "returns a string"
  value       = fortios_system_sessionttl.this.id
}

output "this" {
  value = fortios_system_sessionttl.this
}
```

[top](#index)