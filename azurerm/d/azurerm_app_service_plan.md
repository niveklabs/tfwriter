# azurerm_app_service_plan

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
module "azurerm_app_service_plan" {
  source = "./modules/azurerm/d/azurerm_app_service_plan"

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
data "azurerm_app_service_plan" "this" {
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
output "app_service_environment_id" {
  description = "returns a string"
  value       = data.azurerm_app_service_plan.this.app_service_environment_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_service_plan.this.id
}

output "is_xenon" {
  description = "returns a bool"
  value       = data.azurerm_app_service_plan.this.is_xenon
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_app_service_plan.this.kind
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_service_plan.this.location
}

output "maximum_elastic_worker_count" {
  description = "returns a number"
  value       = data.azurerm_app_service_plan.this.maximum_elastic_worker_count
}

output "maximum_number_of_workers" {
  description = "returns a number"
  value       = data.azurerm_app_service_plan.this.maximum_number_of_workers
}

output "per_site_scaling" {
  description = "returns a bool"
  value       = data.azurerm_app_service_plan.this.per_site_scaling
}

output "reserved" {
  description = "returns a bool"
  value       = data.azurerm_app_service_plan.this.reserved
}

output "sku" {
  description = "returns a list of object"
  value       = data.azurerm_app_service_plan.this.sku
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_app_service_plan.this.tags
}

output "this" {
  value = azurerm_app_service_plan.this
}
```

[top](#index)