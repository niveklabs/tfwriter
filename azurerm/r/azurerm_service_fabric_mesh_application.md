# azurerm_service_fabric_mesh_application

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
module "azurerm_service_fabric_mesh_application" {
  source = "./modules/azurerm/r/azurerm_service_fabric_mesh_application"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  service = [{
    code_package = [{
      image_name = null
      name       = null
      resources = [{
        limits = [{
          cpu    = null
          memory = null
        }]
        requests = [{
          cpu    = null
          memory = null
        }]
      }]
    }]
    name    = null
    os_type = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
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

variable "service" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      code_package = set(object(
        {
          image_name = string
          name       = string
          resources = list(object(
            {
              limits = list(object(
                {
                  cpu    = number
                  memory = number
                }
              ))
              requests = list(object(
                {
                  cpu    = number
                  memory = number
                }
              ))
            }
          ))
        }
      ))
      name    = string
      os_type = string
    }
  ))
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
resource "azurerm_service_fabric_mesh_application" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "service" {
    for_each = var.service
    content {
      # name - (required) is a type of string
      name = service.value["name"]
      # os_type - (required) is a type of string
      os_type = service.value["os_type"]

      dynamic "code_package" {
        for_each = service.value.code_package
        content {
          # image_name - (required) is a type of string
          image_name = code_package.value["image_name"]
          # name - (required) is a type of string
          name = code_package.value["name"]

          dynamic "resources" {
            for_each = code_package.value.resources
            content {

              dynamic "limits" {
                for_each = resources.value.limits
                content {
                  # cpu - (required) is a type of number
                  cpu = limits.value["cpu"]
                  # memory - (required) is a type of number
                  memory = limits.value["memory"]
                }
              }

              dynamic "requests" {
                for_each = resources.value.requests
                content {
                  # cpu - (required) is a type of number
                  cpu = requests.value["cpu"]
                  # memory - (required) is a type of number
                  memory = requests.value["memory"]
                }
              }

            }
          }

        }
      }

    }
  }

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
  value       = azurerm_service_fabric_mesh_application.this.id
}

output "this" {
  value = azurerm_service_fabric_mesh_application.this
}
```

[top](#index)