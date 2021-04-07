# azurerm_spring_cloud_custom_domain

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
module "azurerm_spring_cloud_custom_domain" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_custom_domain"

  # certificate_name - (optional) is a type of string
  certificate_name = null
  # name - (required) is a type of string
  name = null
  # spring_cloud_app_id - (required) is a type of string
  spring_cloud_app_id = null
  # thumbprint - (optional) is a type of string
  thumbprint = null

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
variable "certificate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "spring_cloud_app_id" {
  description = "(required)"
  type        = string
}

variable "thumbprint" {
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
resource "azurerm_spring_cloud_custom_domain" "this" {
  # certificate_name - (optional) is a type of string
  certificate_name = var.certificate_name
  # name - (required) is a type of string
  name = var.name
  # spring_cloud_app_id - (required) is a type of string
  spring_cloud_app_id = var.spring_cloud_app_id
  # thumbprint - (optional) is a type of string
  thumbprint = var.thumbprint

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
  value       = azurerm_spring_cloud_custom_domain.this.id
}

output "this" {
  value = azurerm_spring_cloud_custom_domain.this
}
```

[top](#index)