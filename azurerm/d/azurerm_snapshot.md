# azurerm_snapshot

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
module "azurerm_snapshot" {
  source = "./modules/azurerm/d/azurerm_snapshot"

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
data "azurerm_snapshot" "this" {
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
output "creation_option" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.creation_option
}

output "disk_size_gb" {
  description = "returns a number"
  value       = data.azurerm_snapshot.this.disk_size_gb
}

output "encryption_settings" {
  description = "returns a list of object"
  value       = data.azurerm_snapshot.this.encryption_settings
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.id
}

output "os_type" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.os_type
}

output "source_resource_id" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.source_resource_id
}

output "source_uri" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.source_uri
}

output "storage_account_id" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.storage_account_id
}

output "time_created" {
  description = "returns a string"
  value       = data.azurerm_snapshot.this.time_created
}

output "this" {
  value = azurerm_snapshot.this
}
```

[top](#index)