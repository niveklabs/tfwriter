# azurerm_template_spec_version

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_template_spec_version" {
  source = "./modules/azurerm/d/azurerm_template_spec_version"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # version - (required) is a type of string
  version = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_template_spec_version" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  version             = var.version

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_template_spec_version.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_template_spec_version.this.tags
}

output "template_body" {
  description = "returns a string"
  value       = data.azurerm_template_spec_version.this.template_body
}

output "this" {
  value = azurerm_template_spec_version.this
}
```

[top](#index)