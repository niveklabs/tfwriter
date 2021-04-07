# azurerm_api_management_api_version_set

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
module "azurerm_api_management_api_version_set" {
  source = "./modules/azurerm/d/azurerm_api_management_api_version_set"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
data "azurerm_api_management_api_version_set" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
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
  value       = data.azurerm_api_management_api_version_set.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_api_version_set.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_api_management_api_version_set.this.id
}

output "version_header_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_api_version_set.this.version_header_name
}

output "version_query_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_api_version_set.this.version_query_name
}

output "versioning_scheme" {
  description = "returns a string"
  value       = data.azurerm_api_management_api_version_set.this.versioning_scheme
}

output "this" {
  value = azurerm_api_management_api_version_set.this
}
```

[top](#index)