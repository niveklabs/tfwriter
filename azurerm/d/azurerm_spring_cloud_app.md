# azurerm_spring_cloud_app

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
module "azurerm_spring_cloud_app" {
  source = "./modules/azurerm/d/azurerm_spring_cloud_app"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_name - (required) is a type of string
  service_name = null

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

variable "service_name" {
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
data "azurerm_spring_cloud_app" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # service_name - (required) is a type of string
  service_name = var.service_name

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
output "fqdn" {
  description = "returns a string"
  value       = data.azurerm_spring_cloud_app.this.fqdn
}

output "https_only" {
  description = "returns a bool"
  value       = data.azurerm_spring_cloud_app.this.https_only
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_spring_cloud_app.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_spring_cloud_app.this.identity
}

output "is_public" {
  description = "returns a bool"
  value       = data.azurerm_spring_cloud_app.this.is_public
}

output "persistent_disk" {
  description = "returns a list of object"
  value       = data.azurerm_spring_cloud_app.this.persistent_disk
}

output "tls_enabled" {
  description = "returns a bool"
  value       = data.azurerm_spring_cloud_app.this.tls_enabled
}

output "url" {
  description = "returns a string"
  value       = data.azurerm_spring_cloud_app.this.url
}

output "this" {
  value = azurerm_spring_cloud_app.this
}
```

[top](#index)