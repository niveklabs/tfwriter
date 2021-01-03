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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_application_group" {
  source = "./modules/fortios/r/fortios_application_group"

  # comment - (optional) is a type of string
  comment = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  application = [{
    id = null
  }]

  category = [{
    id = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
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
```

[top](#index)

### Resource

```terraform
resource "fortios_application_group" "this" {
  comment = var.comment
  name    = var.name
  type    = var.type

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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_application_group.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_application_group.this.name
}

output "type" {
  description = "returns a string"
  value       = fortios_application_group.this.type
}

output "this" {
  value = fortios_application_group.this
}
```

[top](#index)