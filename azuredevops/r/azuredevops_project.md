# azuredevops_project

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_project" {
  source = "./modules/azuredevops/r/azuredevops_project"

  # description - (optional) is a type of string
  description = null
  # features - (optional) is a type of map of string
  features = {}
  # name - (required) is a type of string
  name = null
  # version_control - (optional) is a type of string
  version_control = null
  # visibility - (optional) is a type of string
  visibility = null
  # work_item_template - (optional) is a type of string
  work_item_template = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "features" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "version_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "work_item_template" {
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
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_project" "this" {
  # description - (optional) is a type of string
  description = var.description
  # features - (optional) is a type of map of string
  features = var.features
  # name - (required) is a type of string
  name = var.name
  # version_control - (optional) is a type of string
  version_control = var.version_control
  # visibility - (optional) is a type of string
  visibility = var.visibility
  # work_item_template - (optional) is a type of string
  work_item_template = var.work_item_template

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
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
  value       = azuredevops_project.this.id
}

output "process_template_id" {
  description = "returns a string"
  value       = azuredevops_project.this.process_template_id
}

output "this" {
  value = azuredevops_project.this
}
```

[top](#index)