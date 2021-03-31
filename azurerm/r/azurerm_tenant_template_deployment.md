# azurerm_tenant_template_deployment

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
module "azurerm_tenant_template_deployment" {
  source = "./modules/azurerm/r/azurerm_tenant_template_deployment"

  # debug_level - (optional) is a type of string
  debug_level = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # parameters_content - (optional) is a type of string
  parameters_content = null
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

variable "location" {
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
resource "azurerm_tenant_template_deployment" "this" {
  debug_level              = var.debug_level
  location                 = var.location
  name                     = var.name
  parameters_content       = var.parameters_content
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
  value       = azurerm_tenant_template_deployment.this.id
}

output "output_content" {
  description = "returns a string"
  value       = azurerm_tenant_template_deployment.this.output_content
}

output "parameters_content" {
  description = "returns a string"
  value       = azurerm_tenant_template_deployment.this.parameters_content
}

output "template_content" {
  description = "returns a string"
  value       = azurerm_tenant_template_deployment.this.template_content
}

output "this" {
  value = azurerm_tenant_template_deployment.this
}
```

[top](#index)