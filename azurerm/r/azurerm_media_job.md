# azurerm_media_job

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
module "azurerm_media_job" {
  source = "./modules/azurerm/r/azurerm_media_job"

  # description - (optional) is a type of string
  description = null
  # media_services_account_name - (required) is a type of string
  media_services_account_name = null
  # name - (required) is a type of string
  name = null
  # priority - (optional) is a type of string
  priority = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # transform_name - (required) is a type of string
  transform_name = null

  input_asset = [{
    label = null
    name  = null
  }]

  output_asset = [{
    label = null
    name  = null
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
variable "description" {
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

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "transform_name" {
  description = "(required)"
  type        = string
}

variable "input_asset" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      label = string
      name  = string
    }
  ))
}

variable "output_asset" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      label = string
      name  = string
    }
  ))
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
resource "azurerm_media_job" "this" {
  # description - (optional) is a type of string
  description = var.description
  # media_services_account_name - (required) is a type of string
  media_services_account_name = var.media_services_account_name
  # name - (required) is a type of string
  name = var.name
  # priority - (optional) is a type of string
  priority = var.priority
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # transform_name - (required) is a type of string
  transform_name = var.transform_name

  dynamic "input_asset" {
    for_each = var.input_asset
    content {
      # label - (optional) is a type of string
      label = input_asset.value["label"]
      # name - (required) is a type of string
      name = input_asset.value["name"]
    }
  }

  dynamic "output_asset" {
    for_each = var.output_asset
    content {
      # label - (optional) is a type of string
      label = output_asset.value["label"]
      # name - (required) is a type of string
      name = output_asset.value["name"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_media_job.this.id
}

output "this" {
  value = azurerm_media_job.this
}
```

[top](#index)