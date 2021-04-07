# azurerm_healthcare_service

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
module "azurerm_healthcare_service" {
  source = "./modules/azurerm/d/azurerm_healthcare_service"

  # location - (required) is a type of string
  location = null
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
variable "location" {
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
data "azurerm_healthcare_service" "this" {
  # location - (required) is a type of string
  location = var.location
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
output "access_policy_object_ids" {
  description = "returns a set of string"
  value       = data.azurerm_healthcare_service.this.access_policy_object_ids
}

output "authentication_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_healthcare_service.this.authentication_configuration
}

output "cors_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_healthcare_service.this.cors_configuration
}

output "cosmosdb_throughput" {
  description = "returns a number"
  value       = data.azurerm_healthcare_service.this.cosmosdb_throughput
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_healthcare_service.this.id
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_healthcare_service.this.kind
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_healthcare_service.this.tags
}

output "this" {
  value = azurerm_healthcare_service.this
}
```

[top](#index)