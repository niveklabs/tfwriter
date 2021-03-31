# azurerm_storage_account_blob_container_sas

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_storage_account_blob_container_sas" {
  source = "./modules/azurerm/d/azurerm_storage_account_blob_container_sas"

  # cache_control - (optional) is a type of string
  cache_control = null
  # connection_string - (required) is a type of string
  connection_string = null
  # container_name - (required) is a type of string
  container_name = null
  # content_disposition - (optional) is a type of string
  content_disposition = null
  # content_encoding - (optional) is a type of string
  content_encoding = null
  # content_language - (optional) is a type of string
  content_language = null
  # content_type - (optional) is a type of string
  content_type = null
  # expiry - (required) is a type of string
  expiry = null
  # https_only - (optional) is a type of bool
  https_only = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # start - (required) is a type of string
  start = null

  permissions = [{
    add    = null
    create = null
    delete = null
    list   = null
    read   = null
    write  = null
  }]

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cache_control" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_string" {
  description = "(required)"
  type        = string
}

variable "container_name" {
  description = "(required)"
  type        = string
}

variable "content_disposition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiry" {
  description = "(required)"
  type        = string
}

variable "https_only" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      add    = bool
      create = bool
      delete = bool
      list   = bool
      read   = bool
      write  = bool
    }
  ))
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
data "azurerm_storage_account_blob_container_sas" "this" {
  cache_control       = var.cache_control
  connection_string   = var.connection_string
  container_name      = var.container_name
  content_disposition = var.content_disposition
  content_encoding    = var.content_encoding
  content_language    = var.content_language
  content_type        = var.content_type
  expiry              = var.expiry
  https_only          = var.https_only
  ip_address          = var.ip_address
  start               = var.start

  dynamic "permissions" {
    for_each = var.permissions
    content {
      add    = permissions.value["add"]
      create = permissions.value["create"]
      delete = permissions.value["delete"]
      list   = permissions.value["list"]
      read   = permissions.value["read"]
      write  = permissions.value["write"]
    }
  }

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
output "id" {
  description = "returns a string"
  value       = data.azurerm_storage_account_blob_container_sas.this.id
}

output "sas" {
  description = "returns a string"
  value       = data.azurerm_storage_account_blob_container_sas.this.sas
  sensitive   = true
}

output "this" {
  value = azurerm_storage_account_blob_container_sas.this
}
```

[top](#index)