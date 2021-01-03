# azurerm_storage_blob

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_storage_blob" {
  source = null

  # access_tier - (optional) is a type of string
  access_tier = null
  # content_md5 - (optional) is a type of string
  content_md5 = null
  # content_type - (optional) is a type of string
  content_type = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # parallelism - (optional) is a type of number
  parallelism = null
  # size - (optional) is a type of number
  size = null
  # source - (optional) is a type of string
  # source_content - (optional) is a type of string
  source_content = null
  # source_uri - (optional) is a type of string
  source_uri = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # storage_container_name - (required) is a type of string
  storage_container_name = null
  # type - (required) is a type of string
  type = null

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
variable "access_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_md5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parallelism" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "storage_container_name" {
  description = "(required)"
  type        = string
}

variable "type" {
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
resource "azurerm_storage_blob" "this" {
  access_tier            = var.access_tier
  content_md5            = var.content_md5
  content_type           = var.content_type
  metadata               = var.metadata
  name                   = var.name
  parallelism            = var.parallelism
  size                   = var.size
  source                 = var.source
  source_content         = var.source_content
  source_uri             = var.source_uri
  storage_account_name   = var.storage_account_name
  storage_container_name = var.storage_container_name
  type                   = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_tier" {
  description = "returns a string"
  value       = azurerm_storage_blob.this.access_tier
}

output "id" {
  description = "returns a string"
  value       = azurerm_storage_blob.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = azurerm_storage_blob.this.metadata
}

output "url" {
  description = "returns a string"
  value       = azurerm_storage_blob.this.url
}

output "this" {
  value = azurerm_storage_blob.this
}
```

[top](#index)