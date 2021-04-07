# fortios_system_speedtestserver

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
module "fortios_system_speedtestserver" {
  source = "./modules/fortios/r/fortios_system_speedtestserver"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # timestamp - (optional) is a type of number
  timestamp = null

  host = [{
    id       = null
    ip       = null
    password = null
    port     = null
    user     = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timestamp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "host" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id       = number
      ip       = string
      password = string
      port     = number
      user     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_speedtestserver" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # timestamp - (optional) is a type of number
  timestamp = var.timestamp

  dynamic "host" {
    for_each = var.host
    content {
      # id - (optional) is a type of number
      id = host.value["id"]
      # ip - (optional) is a type of string
      ip = host.value["ip"]
      # password - (optional) is a type of string
      password = host.value["password"]
      # port - (optional) is a type of number
      port = host.value["port"]
      # user - (optional) is a type of string
      user = host.value["user"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_speedtestserver.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_speedtestserver.this.name
}

output "timestamp" {
  description = "returns a number"
  value       = fortios_system_speedtestserver.this.timestamp
}

output "this" {
  value = fortios_system_speedtestserver.this
}
```

[top](#index)