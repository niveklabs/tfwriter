# azurerm_api_management_product_policy

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
module "azurerm_api_management_product_policy" {
  source = "./modules/azurerm/r/azurerm_api_management_product_policy"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # product_id - (required) is a type of string
  product_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # xml_content - (optional) is a type of string
  xml_content = null
  # xml_link - (optional) is a type of string
  xml_link = null

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "product_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "xml_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "xml_link" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_api_management_product_policy" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # product_id - (required) is a type of string
  product_id = var.product_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # xml_content - (optional) is a type of string
  xml_content = var.xml_content
  # xml_link - (optional) is a type of string
  xml_link = var.xml_link

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
  value       = azurerm_api_management_product_policy.this.id
}

output "xml_content" {
  description = "returns a string"
  value       = azurerm_api_management_product_policy.this.xml_content
}

output "this" {
  value = azurerm_api_management_product_policy.this
}
```

[top](#index)