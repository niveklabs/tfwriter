# azurerm_logic_app_action_http

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
module "azurerm_logic_app_action_http" {
  source = "./modules/azurerm/r/azurerm_logic_app_action_http"

  # body - (optional) is a type of string
  body = null
  # headers - (optional) is a type of map of string
  headers = {}
  # logic_app_id - (required) is a type of string
  logic_app_id = null
  # method - (required) is a type of string
  method = null
  # name - (required) is a type of string
  name = null
  # uri - (required) is a type of string
  uri = null

  run_after = [{
    action_name   = null
    action_result = null
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
variable "body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "logic_app_id" {
  description = "(required)"
  type        = string
}

variable "method" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "uri" {
  description = "(required)"
  type        = string
}

variable "run_after" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action_name   = string
      action_result = string
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
resource "azurerm_logic_app_action_http" "this" {
  body         = var.body
  headers      = var.headers
  logic_app_id = var.logic_app_id
  method       = var.method
  name         = var.name
  uri          = var.uri

  dynamic "run_after" {
    for_each = var.run_after
    content {
      action_name   = run_after.value["action_name"]
      action_result = run_after.value["action_result"]
    }
  }

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
  value       = azurerm_logic_app_action_http.this.id
}

output "this" {
  value = azurerm_logic_app_action_http.this
}
```

[top](#index)