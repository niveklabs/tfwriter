# azurerm_template_deployment

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
module "azurerm_template_deployment" {
  source = "./modules/azurerm/r/azurerm_template_deployment"

  # deployment_mode - (required) is a type of string
  deployment_mode = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # parameters_body - (optional) is a type of string
  parameters_body = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # template_body - (optional) is a type of string
  template_body = null

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
variable "deployment_mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "parameters_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "template_body" {
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
resource "azurerm_template_deployment" "this" {
  deployment_mode     = var.deployment_mode
  name                = var.name
  parameters          = var.parameters
  parameters_body     = var.parameters_body
  resource_group_name = var.resource_group_name
  template_body       = var.template_body

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
  value       = azurerm_template_deployment.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = azurerm_template_deployment.this.outputs
}

output "template_body" {
  description = "returns a string"
  value       = azurerm_template_deployment.this.template_body
}

output "this" {
  value = azurerm_template_deployment.this
}
```

[top](#index)