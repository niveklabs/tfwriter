# fortios_system_zone

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_zone" {
  source = "./modules/fortios/r/fortios_system_zone"

  # intrazone - (optional) is a type of string
  intrazone = null
  # name - (optional) is a type of string
  name = null

  interface = [{
    interface_name = null
  }]

  tagging = [{
    category = null
    name     = null
    tags = [{
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "intrazone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
  default = []
}

variable "tagging" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      tags = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_zone" "this" {
  intrazone = var.intrazone
  name      = var.name

  dynamic "interface" {
    for_each = var.interface
    content {
      interface_name = interface.value["interface_name"]
    }
  }

  dynamic "tagging" {
    for_each = var.tagging
    content {
      category = tagging.value["category"]
      name     = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          name = tags.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_zone.this.id
}

output "intrazone" {
  description = "returns a string"
  value       = fortios_system_zone.this.intrazone
}

output "name" {
  description = "returns a string"
  value       = fortios_system_zone.this.name
}

output "this" {
  value = fortios_system_zone.this
}
```

[top](#index)