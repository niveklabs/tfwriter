# azurerm_spring_cloud_app

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
module "azurerm_spring_cloud_app" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_app"

  # https_only - (optional) is a type of bool
  https_only = null
  # is_public - (optional) is a type of bool
  is_public = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_name - (required) is a type of string
  service_name = null
  # tls_enabled - (optional) is a type of bool
  tls_enabled = null

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  persistent_disk = [{
    mount_path = null
    size_in_gb = null
  }]

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
variable "https_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "tls_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "persistent_disk" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      mount_path = string
      size_in_gb = number
    }
  ))
  default = []
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
resource "azurerm_spring_cloud_app" "this" {
  # https_only - (optional) is a type of bool
  https_only = var.https_only
  # is_public - (optional) is a type of bool
  is_public = var.is_public
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # service_name - (required) is a type of string
  service_name = var.service_name
  # tls_enabled - (optional) is a type of bool
  tls_enabled = var.tls_enabled

  dynamic "identity" {
    for_each = var.identity
    content {
      # type - (optional) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "persistent_disk" {
    for_each = var.persistent_disk
    content {
      # mount_path - (optional) is a type of string
      mount_path = persistent_disk.value["mount_path"]
      # size_in_gb - (required) is a type of number
      size_in_gb = persistent_disk.value["size_in_gb"]
    }
  }

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
output "fqdn" {
  description = "returns a string"
  value       = azurerm_spring_cloud_app.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = azurerm_spring_cloud_app.this.id
}

output "url" {
  description = "returns a string"
  value       = azurerm_spring_cloud_app.this.url
}

output "this" {
  value = azurerm_spring_cloud_app.this
}
```

[top](#index)