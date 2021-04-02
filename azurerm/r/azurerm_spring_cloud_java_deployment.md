# azurerm_spring_cloud_java_deployment

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
module "azurerm_spring_cloud_java_deployment" {
  source = "./modules/azurerm/r/azurerm_spring_cloud_java_deployment"

  # cpu - (optional) is a type of number
  cpu = null
  # environment_variables - (optional) is a type of map of string
  environment_variables = {}
  # instance_count - (optional) is a type of number
  instance_count = null
  # jvm_options - (optional) is a type of string
  jvm_options = null
  # memory_in_gb - (optional) is a type of number
  memory_in_gb = null
  # name - (required) is a type of string
  name = null
  # runtime_version - (optional) is a type of string
  runtime_version = null
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
variable "cpu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "environment_variables" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "instance_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "jvm_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_in_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "runtime_version" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_spring_cloud_java_deployment" "this" {
  cpu                   = var.cpu
  environment_variables = var.environment_variables
  instance_count        = var.instance_count
  jvm_options           = var.jvm_options
  memory_in_gb          = var.memory_in_gb
  name                  = var.name
  runtime_version       = var.runtime_version
  spring_cloud_app_id   = var.spring_cloud_app_id

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
  value       = azurerm_spring_cloud_java_deployment.this.id
}

output "this" {
  value = azurerm_spring_cloud_java_deployment.this
}
```

[top](#index)