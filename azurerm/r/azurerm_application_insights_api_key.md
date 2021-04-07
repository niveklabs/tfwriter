# azurerm_application_insights_api_key

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
module "azurerm_application_insights_api_key" {
  source = "./modules/azurerm/r/azurerm_application_insights_api_key"

  # application_insights_id - (required) is a type of string
  application_insights_id = null
  # name - (required) is a type of string
  name = null
  # read_permissions - (optional) is a type of set of string
  read_permissions = []
  # write_permissions - (optional) is a type of set of string
  write_permissions = []

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
variable "application_insights_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "read_permissions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "write_permissions" {
  description = "(optional)"
  type        = set(string)
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
resource "azurerm_application_insights_api_key" "this" {
  # application_insights_id - (required) is a type of string
  application_insights_id = var.application_insights_id
  # name - (required) is a type of string
  name = var.name
  # read_permissions - (optional) is a type of set of string
  read_permissions = var.read_permissions
  # write_permissions - (optional) is a type of set of string
  write_permissions = var.write_permissions

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
output "api_key" {
  description = "returns a string"
  value       = azurerm_application_insights_api_key.this.api_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = azurerm_application_insights_api_key.this.id
}

output "this" {
  value = azurerm_application_insights_api_key.this
}
```

[top](#index)