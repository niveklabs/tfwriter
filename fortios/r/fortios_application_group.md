# fortios_application_group

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
module "fortios_application_group" {
  source = "./modules/fortios/r/fortios_application_group"

  # behavior - (optional) is a type of string
  behavior = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # popularity - (optional) is a type of string
  popularity = null
  # protocols - (optional) is a type of string
  protocols = null
  # technology - (optional) is a type of string
  technology = null
  # type - (optional) is a type of string
  type = null
  # vendor - (optional) is a type of string
  vendor = null

  application = [{
    id = null
  }]

  category = [{
    id = null
  }]

  risk = [{
    level = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "behavior" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "popularity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocols" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "technology" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "risk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      level = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_application_group" "this" {
  behavior              = var.behavior
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name
  popularity            = var.popularity
  protocols             = var.protocols
  technology            = var.technology
  type                  = var.type
  vendor                = var.vendor

  dynamic "application" {
    for_each = var.application
    content {
      id = application.value["id"]
    }
  }

  dynamic "category" {
    for_each = var.category
    content {
      id = category.value["id"]
    }
  }

  dynamic "risk" {
    for_each = var.risk
    content {
      level = risk.value["level"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "behavior" {
  description = "returns a string"
  value       = fortios_application_group.this.behavior
}

output "id" {
  description = "returns a string"
  value       = fortios_application_group.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_application_group.this.name
}

output "popularity" {
  description = "returns a string"
  value       = fortios_application_group.this.popularity
}

output "protocols" {
  description = "returns a string"
  value       = fortios_application_group.this.protocols
}

output "technology" {
  description = "returns a string"
  value       = fortios_application_group.this.technology
}

output "type" {
  description = "returns a string"
  value       = fortios_application_group.this.type
}

output "vendor" {
  description = "returns a string"
  value       = fortios_application_group.this.vendor
}

output "this" {
  value = fortios_application_group.this
}
```

[top](#index)