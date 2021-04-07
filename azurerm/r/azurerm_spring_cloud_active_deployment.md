# azurerm_spring_cloud_active_deployment

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
module "azurerm_spring_cloud_active_deployment" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_active_deployment"

  # deployment_name - (required) is a type of string
  deployment_name = null
  # spring_cloud_app_id - (required) is a type of string
  spring_cloud_app_id = null

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
variable "deployment_name" {
  description = "(required)"
  type        = string
}

variable "spring_cloud_app_id" {
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
resource "azurerm_spring_cloud_active_deployment" "this" {
  # deployment_name - (required) is a type of string
  deployment_name = var.deployment_name
  # spring_cloud_app_id - (required) is a type of string
  spring_cloud_app_id = var.spring_cloud_app_id

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
  value       = azurerm_spring_cloud_active_deployment.this.id
}

output "this" {
  value = azurerm_spring_cloud_active_deployment.this
}
```

[top](#index)