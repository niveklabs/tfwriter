# azurerm_blueprint_published_version

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_blueprint_published_version" {
  source = "./modules/azurerm/d/azurerm_blueprint_published_version"

  # blueprint_name - (required) is a type of string
  blueprint_name = null
  # scope_id - (required) is a type of string
  scope_id = null
  # version - (required) is a type of string
  version = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "blueprint_name" {
  description = "(required)"
  type        = string
}

variable "scope_id" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_blueprint_published_version" "this" {
  blueprint_name = var.blueprint_name
  scope_id       = var.scope_id
  version        = var.version

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.id
}

output "last_modified" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.last_modified
}

output "target_scope" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.target_scope
}

output "time_created" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.time_created
}

output "type" {
  description = "returns a string"
  value       = data.azurerm_blueprint_published_version.this.type
}

output "this" {
  value = azurerm_blueprint_published_version.this
}
```

[top](#index)