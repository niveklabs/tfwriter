# skytap_project

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_project" {
  source = "./modules/skytap/r/skytap_project"

  # auto_add_role_name - (optional) is a type of string
  auto_add_role_name = null
  # name - (required) is a type of string
  name = null
  # show_project_members - (optional) is a type of bool
  show_project_members = null
  # summary - (optional) is a type of string
  summary = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_add_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "show_project_members" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "summary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "skytap_project" "this" {
  # auto_add_role_name - (optional) is a type of string
  auto_add_role_name = var.auto_add_role_name
  # name - (required) is a type of string
  name = var.name
  # show_project_members - (optional) is a type of bool
  show_project_members = var.show_project_members
  # summary - (optional) is a type of string
  summary = var.summary

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = skytap_project.this.id
}

output "this" {
  value = skytap_project.this
}
```

[top](#index)