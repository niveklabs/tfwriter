# azurerm_resource_group_template_deployment

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
module "azurerm_resource_group_template_deployment" {
  source = "./modules/azurerm/r/azurerm_resource_group_template_deployment"

  # debug_level - (optional) is a type of string
  debug_level = null
  # deployment_mode - (required) is a type of string
  deployment_mode = null
  # name - (required) is a type of string
  name = null
  # parameters_content - (optional) is a type of string
  parameters_content = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_content - (optional) is a type of string
  template_content = null
  # template_spec_version_id - (optional) is a type of string
  template_spec_version_id = null

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
variable "debug_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_spec_version_id" {
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
resource "azurerm_resource_group_template_deployment" "this" {
  debug_level              = var.debug_level
  deployment_mode          = var.deployment_mode
  name                     = var.name
  parameters_content       = var.parameters_content
  resource_group_name      = var.resource_group_name
  tags                     = var.tags
  template_content         = var.template_content
  template_spec_version_id = var.template_spec_version_id

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
  value       = azurerm_resource_group_template_deployment.this.id
}

output "output_content" {
  description = "returns a string"
  value       = azurerm_resource_group_template_deployment.this.output_content
}

output "parameters_content" {
  description = "returns a string"
  value       = azurerm_resource_group_template_deployment.this.parameters_content
}

output "template_content" {
  description = "returns a string"
  value       = azurerm_resource_group_template_deployment.this.template_content
}

output "this" {
  value = azurerm_resource_group_template_deployment.this
}
```

[top](#index)