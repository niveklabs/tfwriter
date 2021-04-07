# azurerm_shared_image

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
module "azurerm_shared_image" {
  source = "./modules/azurerm/r/azurerm_shared_image"

  # description - (optional) is a type of string
  description = null
  # eula - (optional) is a type of string
  eula = null
  # gallery_name - (required) is a type of string
  gallery_name = null
  # hyper_v_generation - (optional) is a type of string
  hyper_v_generation = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # os_type - (required) is a type of string
  os_type = null
  # privacy_statement_uri - (optional) is a type of string
  privacy_statement_uri = null
  # release_note_uri - (optional) is a type of string
  release_note_uri = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # specialized - (optional) is a type of bool
  specialized = null
  # tags - (optional) is a type of map of string
  tags = {}

  identifier = [{
    offer     = null
    publisher = null
    sku       = null
  }]

  purchase_plan = [{
    name      = null
    product   = null
    publisher = null
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

variable "eula" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gallery_name" {
  description = "(required)"
  type        = string
}

variable "hyper_v_generation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "os_type" {
  description = "(required)"
  type        = string
}

variable "privacy_statement_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "release_note_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "specialized" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "identifier" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      offer     = string
      publisher = string
      sku       = string
    }
  ))
}

variable "purchase_plan" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name      = string
      product   = string
      publisher = string
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
resource "azurerm_shared_image" "this" {
  # description - (optional) is a type of string
  description = var.description
  # eula - (optional) is a type of string
  eula = var.eula
  # gallery_name - (required) is a type of string
  gallery_name = var.gallery_name
  # hyper_v_generation - (optional) is a type of string
  hyper_v_generation = var.hyper_v_generation
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # os_type - (required) is a type of string
  os_type = var.os_type
  # privacy_statement_uri - (optional) is a type of string
  privacy_statement_uri = var.privacy_statement_uri
  # release_note_uri - (optional) is a type of string
  release_note_uri = var.release_note_uri
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # specialized - (optional) is a type of bool
  specialized = var.specialized
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "identifier" {
    for_each = var.identifier
    content {
      # offer - (required) is a type of string
      offer = identifier.value["offer"]
      # publisher - (required) is a type of string
      publisher = identifier.value["publisher"]
      # sku - (required) is a type of string
      sku = identifier.value["sku"]
    }
  }

  dynamic "purchase_plan" {
    for_each = var.purchase_plan
    content {
      # name - (required) is a type of string
      name = purchase_plan.value["name"]
      # product - (optional) is a type of string
      product = purchase_plan.value["product"]
      # publisher - (optional) is a type of string
      publisher = purchase_plan.value["publisher"]
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
  value       = azurerm_shared_image.this.id
}

output "this" {
  value = azurerm_shared_image.this
}
```

[top](#index)