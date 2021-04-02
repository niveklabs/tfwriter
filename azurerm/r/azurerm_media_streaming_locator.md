# azurerm_media_streaming_locator

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
module "azurerm_media_streaming_locator" {
  source = "./modules/azurerm/r/azurerm_media_streaming_locator"

  # alternative_media_id - (optional) is a type of string
  alternative_media_id = null
  # asset_name - (required) is a type of string
  asset_name = null
  # default_content_key_policy_name - (optional) is a type of string
  default_content_key_policy_name = null
  # end_time - (optional) is a type of string
  end_time = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # start_time - (optional) is a type of string
  start_time = null
  # streaming_locator_id - (optional) is a type of string
  streaming_locator_id = null
  # streaming_policy_name - (required) is a type of string
  streaming_policy_name = null

  content_key = [{
    content_key_id                      = null
    label_reference_in_streaming_policy = null
    policy_name                         = null
    type                                = null
    value                               = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alternative_media_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asset_name" {
  description = "(required)"
  type        = string
}

variable "default_content_key_policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_services_account_name" {
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

variable "start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "streaming_locator_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "streaming_policy_name" {
  description = "(required)"
  type        = string
}

variable "content_key" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      content_key_id                      = string
      label_reference_in_streaming_policy = string
      policy_name                         = string
      type                                = string
      value                               = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_media_streaming_locator" "this" {
  alternative_media_id            = var.alternative_media_id
  asset_name                      = var.asset_name
  default_content_key_policy_name = var.default_content_key_policy_name
  end_time                        = var.end_time
  media_services_account_name     = var.media_services_account_name
  name                            = var.name
  resource_group_name             = var.resource_group_name
  start_time                      = var.start_time
  streaming_locator_id            = var.streaming_locator_id
  streaming_policy_name           = var.streaming_policy_name

  dynamic "content_key" {
    for_each = var.content_key
    content {
      content_key_id                      = content_key.value["content_key_id"]
      label_reference_in_streaming_policy = content_key.value["label_reference_in_streaming_policy"]
      policy_name                         = content_key.value["policy_name"]
      type                                = content_key.value["type"]
      value                               = content_key.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "end_time" {
  description = "returns a string"
  value       = azurerm_media_streaming_locator.this.end_time
}

output "id" {
  description = "returns a string"
  value       = azurerm_media_streaming_locator.this.id
}

output "streaming_locator_id" {
  description = "returns a string"
  value       = azurerm_media_streaming_locator.this.streaming_locator_id
}

output "this" {
  value = azurerm_media_streaming_locator.this
}
```

[top](#index)