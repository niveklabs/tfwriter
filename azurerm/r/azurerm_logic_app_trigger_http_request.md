# azurerm_logic_app_trigger_http_request

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_logic_app_trigger_http_request" {
  source = "./modules/azurerm/r/azurerm_logic_app_trigger_http_request"

  # logic_app_id - (required) is a type of string
  logic_app_id = null
  # method - (optional) is a type of string
  method = null
  # name - (required) is a type of string
  name = null
  # relative_path - (optional) is a type of string
  relative_path = null
  # schema - (required) is a type of string
  schema = null

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
variable "logic_app_id" {
  description = "(required)"
  type        = string
}

variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "relative_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema" {
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
resource "azurerm_logic_app_trigger_http_request" "this" {
  logic_app_id  = var.logic_app_id
  method        = var.method
  name          = var.name
  relative_path = var.relative_path
  schema        = var.schema

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
output "id" {
  description = "returns a string"
  value       = azurerm_logic_app_trigger_http_request.this.id
}

output "this" {
  value = azurerm_logic_app_trigger_http_request.this
}
```

[top](#index)