# azurerm_api_management_api_version_set

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/azurerm/r/azurerm_api_management_api_version_set"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # version_header_name - (optional) is a type of string
  version_header_name = null
  # version_query_name - (optional) is a type of string
  version_query_name = null
  # versioning_scheme - (required) is a type of string
  versioning_scheme = null

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
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

variable "version_header_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_query_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "versioning_scheme" {
  description = "(required)"
  type        = string
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
resource "azurerm_api_management_api_version_set" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # version_header_name - (optional) is a type of string
  version_header_name = var.version_header_name
  # version_query_name - (optional) is a type of string
  version_query_name = var.version_query_name
  # versioning_scheme - (required) is a type of string
  versioning_scheme = var.versioning_scheme

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
  value       = azurerm_api_management_api_version_set.this.id
}

output "this" {
  value = azurerm_api_management_api_version_set.this
}
```

[top](#index)