# azurerm_kubernetes_service_versions

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_kubernetes_service_versions" {
  source = "./modules/azurerm/d/azurerm_kubernetes_service_versions"

  # include_preview - (optional) is a type of bool
  include_preview = null
  # location - (required) is a type of string
  location = null
  # version_prefix - (optional) is a type of string
  version_prefix = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "include_preview" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "version_prefix" {
  description = "(optional)"
  type        = string
  default     = null
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
data "azurerm_kubernetes_service_versions" "this" {
  include_preview = var.include_preview
  location        = var.location
  version_prefix  = var.version_prefix

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
  value       = data.azurerm_kubernetes_service_versions.this.id
}

output "latest_version" {
  description = "returns a string"
  value       = data.azurerm_kubernetes_service_versions.this.latest_version
}

output "versions" {
  description = "returns a list of string"
  value       = data.azurerm_kubernetes_service_versions.this.versions
}

output "this" {
  value = azurerm_kubernetes_service_versions.this
}
```

[top](#index)